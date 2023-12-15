# 概述

之前一直用国信的QMT（又叫iquant），但是有几个问题：
- 费用太高，死活不给我免五，费率还是万2.5
- 不支持miniqmt，也就是必须等着他来每一个tick（3秒）来回调，没法主动发起交易
- 没发主动去服务器拉取数据

而国金的qmt，完美解决了上述的问题，在热心网友的推荐下，我申请了国金的QMT，万一免5，真香！

但是在使用过程中，还是遇到这样那样的问题，我把他们一一记录下来。

# 配置ssh环境

这个和QMT无关，只是记录一下。

我的mac不想每次都远程桌面到我的window中，想直接通过ssh连接到windows服务器上。

1、先安装了windows上的openssh服务，不需要额外安装包，只需要在服务中追加即可。

2、然后修改，C:\ProgramData\ssh\sshd_config：
```
PermitRootLogin yes
PermitRootLogin yes
```

3、重启ssh服务： net stop sshd；net start sshd。

4、然后ssh Administrator@<IP>既可以。

# 国金miniQMT环境

先吐槽，感觉这些国内厂家，做事情总是做不到完美，一堆的问题。

我首先安装了国金的QMT，是个安装包，装上即可。

安装后的国金QMT，在登录的时候，勾选“极简模式”，就可以进入到传说中的miniqmt界面（极简模式）。
我看了下，确实简洁多了，没法看行情、没法做回测，只能交易和查看持仓，确实是“极简模式”！

这个miniqmt（也就是极简模式），是无法写回测的，只能做交易，如果你想回测，那么去掉极简模式，进入QMT；或者用backtrader这类回测框架、也可以用聚宽、大宽之类的在线回测平台。

# xtquant

xtquant是啥？

xtquant是一个python的包，通过这个这个python包，就可以调用miniqmt完成交易、数据查询了。
你可以理解为miniqmt的python api。

那么这个xtquant在哪里的？

刚开始安装完，是没有的，你必须要去下载，也就是要去QMT的设置中，去下载：

到设置>模型设置>Python库下载中，去官网下最新的package，经过大概10分钟的下载，就会发现在国金的安装目录的bin.x64中多出了Lib目录（之前是没有的），在Lib/site-pckages/里面，就可以找到xtquant包。

# 使用xtquant

如何使用xtquant呢？很简单，import xtquant，然后就可以通过xtquant和miniquant通讯，做交易、拉数据了。

具体可以参考[官网的demo代码](http://docs.thinktrader.net/vip/pages/5e493a/#_1-%E4%BD%BF%E7%94%A8xtquant%E5%BA%93order-stock-async%E4%B8%8B%E5%8D%95%E6%8E%A5%E5%8F%A3%E8%BF%9B%E8%A1%8C%E4%B8%8B%E5%8D%95demo):


```
from xtquant.xttrader import XtQuantTrader
from xtquant.xttrader import XtQuantTraderCallback
from xtquant.xttype import StockAccount
acc = StockAccount('800068', 'STOCK')
callback = MyXtQuantTraderCallback()
xt_trader.register_callback(callback)
xt_trader.start()
connect_result = xt_trader.connect() 
```

*代码仅演示说明，完整代码请参考官网代码*

如果你需要第三方包，该如何安装呢？

那么，你需要先安装一个python3.6.8（必须是这个版本，才和QMT的默认python是同一版本），然后用你安装的python3.6.8目录中pip，去安装包，但是需要用target参数指定安装的目标路径，即把目标目录指向国金的QMT的python目录。

例如：

```shell
C:\software\python3.6.8\Scripts\pip install pyYAML 
--target C:\software\guojinqmt\bin.x64\Lib\site-packages
```


# 如何使用外部python

上面的演示，是要运行国信QMT自带的python，在安装目录/bin.x64/pythonw.exe。
但是，这个版本是python3.6.8，如果我想用更高版本的python咋办？

答案是，自己装!

是的，你可以自己单独装一个python，比如python3.8，然后，你需要把xtquant包，手工拷贝到你安装到python的package目录（一般是在python目录的Lib/site-pckages里）。对，你没看错，就是这么土，要手工拷贝。从国信的qmt的bin.x64/Lib/site-packages，拷贝到你的python的目录下的Lib/site-package中）。实际上就是手工安装了一个package。我又禁不住想吐槽，去pip源上搞个xtquant包，有那么难么？为何就不搞一个呢？！

**遇到问题**

当我按照上面的做法，把xtquant从国金的目录，拷贝新安装的python3.8后，运行我的测试程序时候，发生了以下错误：

```python
File "C:\software\python3.8\lib\site-packages\xtquant\xtdata.py", line 14, in <module>
    from .IPythonApiClient import IPythonApiClient as RPCClient
ImportError: DLL load failed while importing IPythonApiClient: 找不到指定的模块。
```

网上说这个是因为pip包安装的问题，可是我pyhthon3.8的目录下看了，IPythonApiClient.cp38.dll是存在的！不应该报错啊。

没办法，我只好又去官网，重新下了最新的[xtquant](http://dict.thinktrader.net/nativeApi/download_xtquant.html?id=e2M5nZ)，这次是官网提供的，之前是从QMT里拷贝出来的。

下载下来是一个rar包，再次吐槽，就不能做个pip包么？而且，为何要用rar，不用zip。

解压缩后，放置到python3.8的site-packages中，比如我的就是C:\software\python3.8\lib\site-packages\，然后再跑程序。就ok了。

# xttrader的连接问题

接下来，我又遇到一个诡异问题，详细的场景是这样的：

- 我先启动xtminiquant，然后运行python程序，xttrader.connect()没问题，可以链接上
- 然后我退出这个python程序，然后我再运行它，xttrader.connect()就不行了，返回-1
- 如果我关掉xtminiquant，再重新打开，然后再运行python程序，就又ok了

```python
.....
connect_result = xt_trader.connect()
# 阻塞线程，接收交易推送
xt_trader.run_forever()
```

也就是说，我不能开着xtminiquant，第二次运行python程序，就connect()不上了。

后来，在热心群友的建议下，我直接运行了2遍ptyhon程序，第二个运行的python程序就没有出现connect的问题。对比上面的场景，区别是，我并没有关掉第一个python程序。也就是，我的连接没有被异常中断。

我怀疑可能是异常中断导致的，因为run_forever()函数会阻塞，我每次为了退出，都直接ctrl+C，粗暴关闭。

然后我改成了xt_trader.stop()来优雅的关闭他后，这个问题就消失了。

我无论几次运行，都不会再出现connect()失败的问题了。

# xtminiqmt自动登录

国信的iquant（也就是qmt）支持记住密码（自动登录），你只需要在登录的时候勾选了“自动登录”，下次就不用再输入密码，直接进入了。

但是，国金的这个qmt不支持自动登录，很讨厌（勾选上自动登录也记不住）。每次，你都要输入密码。你勾选了自动登录，也无效，总是每一次都让你重新输入。

万能的网友找到了一个办法：

在登陆进去qmt的瞬间，会在bin.x64目录生成一个叫linkMini的文件，登录成功后，这个文件又会被删除掉。但是如果你能得到这个文件，你就可以通过运行以下命令，不用输密码，自动登录进miniqmt了 :

```shell
xtminiqmt.exe linkMini
```

这个linkMini其实是一个密码文件，里面存放了加密的密码，这样就不用再输入密码就可以进入了。

那么问题来了，如何得到这个linkMini？得手得足够快，在它被删除前，复制出来。但是，这太难了，所以万能的网友写了一个批处理，帮助你截获copy这个文件：

```shell
:loop
if exist linkmini (
    copy linkmini linkmini_copy 
    echo finish
    goto end
)
echo continue
timeout /t 0.1 >nul
goto loop
:end
```

你只需要先运行上这个batch，然后去登录QMT，勾选极简模式，登录成功的瞬间，linkMini文件就被拷贝下来了，酷！

这里还有个坑，就是你运行*xtminiqmt.exe linkMini*的时候，linkMini的M必须大写，不能小写，而且，这个文件名必须叫这个名字，否则无效。


# 参考

以下是一些参考文章和摘要，当然，还可以去泡泡网上的qmt微信群，获得更多的网友帮助！

- https://blog.csdn.net/u010214511/article/details/131734432
- https://mp.weixin.qq.com/s/IhvAZUtaebGPCD2LRTMIGA 
- https://mp.weixin.qq.com/s/IhvAZUtaebGPCD2LRTMIGA 

> miniQMT属于QMT的一个子功能，一个精简功能的自动交易框架，默认安装了QMT之后就可以使用miniQMT，只支持实盘交易，不支持回测。
在miniQMT模式下，你的策略代码将不再禁锢自带的QMT软件下的内置编辑器编写，而是可以自由地选择pycharm,vscode等编辑器，运行的时候直接使用 python [xxxx.py](http://xxxx.py/) 这样的形式启动。且有多个python版本可选。
miniQMT的核心是XtQuant，XtQuant又是什么呢？
XtQuant是基于迅投MiniQMT衍生出来的一套完善的Python策略运行框架，对外以Python库的形式提供策略交易所需要的行情和交易相关的API接口。
XtQuant目前提供的库包括Python3.6、3.7、3.8版本，不同版本的python导入时会自动切换。
运行使用XtQuant的程序前需要先启动MiniQMT客户端。
把你的QMT目录下的\bin.x64\Lib\site-packages\xtquant复制到你系统python目录下的site-packages。
从xtquant的帮助文档来看，它是一套和QMT接口函数完全不一样的交易框架。
> 
> 
> 所以QMT的代码，无法直接拷贝到miniQMT中使用。虽然名字叫miniQMT，但感觉它提供的很多函数功能，要比QMT更为丰富，用户可以掌控的流程更多，更灵活。
> 
> 另外还有一个与之配套的xtdata库，是专门用来获取行情数据的，而上面的xttrade是专门用来交易下单的。
> xtdata可以获取很多股票，可转债，ETF等等历史数据，所以即使你不用miniQMT做交易，你也可以白嫖它的数据，这比用积分的tushare简直不要太爽。比如可以获取到股票或可转债的日线，分钟线，甚至tick数据。
> 