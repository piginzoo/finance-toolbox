# 投资学

## 前言

这其实是我学习博迪《投资学》和财大刘志东老师的“投资学课程”的笔记。

学投资学的初衷，是由于自己确实有让自己资产保值增值的需求，毕竟每年6%的通胀率，你不让你的钱保值增值，就会被这个社会收割6%的通胀税。可是，你要把你的资产做到6%的收益率，可不是件容易的事啊，你看现在的银行的各类理财产品，也就是4%左右的收益率。你要是看到5%、6%的产品，都被贴上了高收益、高风险的标签了，可是，6%是起码要达到的收益率呀。基于此，至少为了让自己的资产可以不缩水，必须、有必要认真学习一下投资学的内容。

我是带着问题来学习的，我其实对投资这块，脑子里是有一大堆问题的：
- 我是个风险厌恶型的人，那么我多少钱应该买无风险的资产，多少钱买有风险的资产？
- 那么，到底什么是无风险资产？他们的收益率能到多少？
- 啥是风险？到底怎么来衡量风险？
- 组合就好么？无风险+有风险资产如何组合？有风险资产内部如何组合（比如多少股票，多少基金）？基金应该挑选那些？
- 如何择时？也就是何时入场、何时立场？
- 有没有什么对冲手段么？比如保险、期货对冲，没想赚啥杠杆的钱，就想对冲，这种工具有么，有哪些？
- 系统性风险究竟能不能对冲掉？如果来了，如何甄别和规避？

如果是6%的收益率，也就是抵御通胀的收益率的话，100万，10年，可以变成180万，赚80%的收益率；10%的话，7年就可以翻倍，复利的力量：

![](/images/20210502/1619940365914.jpg)

但是，前提是，你真的可以保证你有能力做到持续的6%+的正收益，所以，我想通过自己的学习和研究，想找个目标迈进。




## d

夏普指数：
$$ S_a = \frac{E[R_a-R_b]}{\sigma_a} = $$ 

夏普指数，就是刻画，你单位风险下的的收益率。有点抽象，其实很简单，举个例子，比如无风险收益是3%，产品A是23%年化收益率，产品B是13%的年化收益率，但是A的风险是4%（风险就是方差），而B的风险是1%，那么，产品A的夏普指数是 $\frac{23%-3%}{4%}=5$，而产品B的夏普指数是 $\frac{13%-3%}{1%}=10$，那么产品B其实是更好的投资标的，大白话，就是，我不能光看收益率高就买它，我还得看风险大不大，两个的比值大的那个，最好！

$R_m$是市场的平均收益率，可以用股指近似，但是还有很多诸如分红等各种因素需要考虑，专业的计算，可以参考：

**$R_m$数据库**

- 国泰安CSMar数据库
- 万德数据库

各公司的$\beta$值，其实数据库也是提供的，那么，基金也是可以提供了？

# 数据库

- [https://uqer.datayes.com/](https://uqer.datayes.com/) 优矿
- [http://tushare.org/](http://tushare.org/)
- [http://quantapi.eastmoney.com/?from=web](http://quantapi.eastmoney.com/?from=web) 天天基金
- [https://www.wind.com.cn/NewSite/data.html](https://www.wind.com.cn/NewSite/data.html) 万德wind
- [http://quantapi.10jqka.com.cn/?page=home](http://quantapi.10jqka.com.cn/?page=home)  同花顺
- [http://baostock.com/baostock/index.php/首页](http://baostock.com/baostock/index.php/%E9%A6%96%E9%A1%B5)  证券宝www.baostock.com是一个免费、开源的证券数据平台
- [https://www.akshare.xyz/zh_CN/latest/index.html](https://www.akshare.xyz/zh_CN/latest/index.html) 这个最实用
- [https://github.com/jindaxiang/akshare](https://github.com/jindaxiang/akshare) ，开源代码
- [https://datacenter.jin10.com/](https://datacenter.jin10.com/)
- [https://ycjq.95358.com/](https://ycjq.95358.com/)
- [https://www.joinquant.com/user/login/index](https://www.joinquant.com/user/login/index)  这个也免费


# 参考
- [回形针：基金经理对你的钱做了什么?](https://weibo.com/6414205745/KczNjyVZK?type=comment&layerid=4629975338326088)，帮助你解了基金的一些知识。
- [中央财经大学-投资学（国家级精品课）](https://www.bilibili.com/video/BV1C4411X7zU?p=78&t=41)，刘志东老师讲的部分最有用。
- [清华大学 - 投资学](https://www.xuetangx.com/learn/thu02011003130/thu02011003130/5894332/video/9307292)，清华大学的王茵田教授的投资客讲解，也非常通俗易懂。
- [柴知道：如何科学投资你的辛苦钱？科学理财为什么这么难？](https://www.bilibili.com/video/av844339890/)，通俗易懂的给你讲了最优风险组合理论。
- [博迪 -《投资学（原书第10版）》](https://book.douban.com/subject/27159606/)，最经典的投资学教材，没有之一。
- [李锦堂 - 我如何分配我的收入](https://www.bilibili.com/video/BV17b41187PA)，我很喜欢的马来清华小哥，他对标普S&P500的讲解通俗易懂。