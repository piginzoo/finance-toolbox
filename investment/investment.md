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

另外，这个笔记其实很简单的，只记录了我觉得最需要的一些**“干货”**，没有详细和冗余的解释，但是，如果要全面和深刻掌握，还是得去认真深入学习，
比如夏普的《投资学》、博迪的《投资学》、徐高的《徐高 - 金融经济学二十五讲》、中央财经大学的“投资学”课程、王蓁老师的量化投资课程等。
请参考我最后一章的附录，可以获得更多细节。


## 如何衡量风险收益



## 无差异曲线

你冒险就希望多收益，对吧？你降低风险，对收益预期也降低。所以，你的投资的好恶就可以用一个平滑曲线表示。

而我冒同样的险，跟你的收益不一样，所以我的好恶曲线，和你的不一样。

所谓**无差异**，是说，你对预期的感受是一致的，风险大了你就觉得收益就大点，风险小收益就小，你**“认”**这个感受，你觉得这个风险低，收益只能是这些，你接受。
在我理解，其实一个无差异曲线，往往对应着一个或者一类投资产品。

用数学表达就是：$$U=E(r)-0.005 A \sigma^{2}$$，这里面变量是$$E(r),\sigma^2$$，不变的是这个人的好恶$$A$$。

![](/images/20211013/1634112392892.jpg)

这里的$$I_1,I_2,I_3$$，都是一个人的，你可以理解成对不同的投资标的的风险接受程度。而对同一个投资产品，他的收益预期和风险偏好就是一条曲线。
且，这个人的这些偏好曲线都是不相交的。

![](/images/20211013/1634112524127.jpg)

不同人的无差异曲线，他们的**“陡峭”**程度不一样，越陡，越厌恶风险。

为何是**下凸**的呢？

是因为，风险越大，人们对收益的期待就约**“偏大”**，曲线就偏陡；而风险小，预期收益就小，曲线就平缓，所以，就是一个下凸的曲线。


## 夏普指数

夏普指数：
$$ S_a = \frac{E[R_a-R_b]}{\sigma_a} = $$ 

夏普指数，就是刻画，你单位风险下的的收益率。有点抽象，其实很简单，举个例子，比如无风险收益是3%，产品A是23%年化收益率，产品B是13%的年化收益率，但是A的风险是4%（风险就是方差），而B的风险是1%，那么，产品A的夏普指数是 $\frac{23%-3%}{4%}=5$，而产品B的夏普指数是 $\frac{13%-3%}{1%}=10$，那么产品B其实是更好的投资标的，大白话，就是，我不能光看收益率高就买它，我还得看风险大不大，两个的比值大的那个，最好！

$R_m$是市场的平均收益率，可以用股指近似，但是还有很多诸如分红等各种因素需要考虑，专业的计算，可以参考：

**$R_m$数据库**

- 国泰安CSMar数据库
- 万德数据库

各公司的$\beta$值，其实数据库也是提供的，那么，基金也是可以提供了？

## 均值方差分析

几个基本公式先列一下，

均值：$$\bar{r}=\frac{1}{N} \sum_{i=1}^{N} r_{i}$$

方差：$$\sigma_{r}^{2}=\frac{1}{N} \sum_{i=1}^{N}\left(r_{i}-\bar{r}\right)^{2}$$

标准差：$$\sigma_{r}=\sqrt{\frac{1}{N} \sum_{i=1}^{N}\left(r_{i}-\bar{r}\right)^{2}}$$

协方差：$$\sigma_{x y}=\frac{1}{N} \sum_{i=1}^{N}\left(x_{i}-\bar{x}\right)\left(y_{i}-\bar{y}\right)$$

相关系数：$$\rho_{x y}=\frac{\sigma_{x y}}{\sigma_{x} \sigma_{y}}$$

但其实，我们是假设，过去的分布和未来相同，过去的模式会在未来不断重复出现，所以，我们可以用把这种历史数据的计算扩展到期望，即：

均值：$$\bar{r}=E(r)=\sum_{j=1}^M p_j r_j$$

方差：$$\sigma_{r}^{2}=E(r-\bar{r})$$

相关系数：$$\rho_{x y}=E(x-\bar{x})(y-\bar{y})$$

这些式子，在数学意义上不是严格相等，但是，在上面提到的金融假设上，就近似相等了。可是，过去就代表未来么？这个问题值的深思。


## 无风险和风险资产组合

无风险收益$$r_f$$和风险资产收益$$r_s$$，他们组合到一起，收益如何表达呢？表达成：组合收益均值$$r_p$$、组合收益方差$$\sigma_p$$:

$$
\begin{aligned}
&\bar{r}_{p}=E\left[(1-w) r_{f}+w r_{s}\right]=(1-w) r_{f}+w \bar{r}_{s}=r_{f}+w\left(\bar{r}_{s}-r_{f}\right) \\
&\sigma_{p}^{2}=E\left[(1-w) r_{f}+w r_{s}-(1-w) r_{f}-w \bar{r}_{s}\right]^{2}=E\left[w^{2}\left(r_{s}-\bar{r}_{s}\right)^{2}\right]=w^{2} \sigma_{s}^{2}
\end{aligned}
$$

然后，把这两者组合收益均值$$r_p$$、组合收益方差$$\sigma_p$$的关系表达出来：

$$\bar{r}_{p}=r_{f}+\frac{\bar{r}_{s}-r_{f}}{\sigma_{s}} \sigma_{p}$$

这是个线性关系，你愿意承担更大的风险$$\sigma_p$$，你就可以得到更高的收益$$\bar{r_p}/E(r_p)$$，而直线的斜率是个常数$$\frac{\bar{r}_{s}-r_{f}}{\sigma_{s}}$$。

![](/images/20211013/1634105867823.jpg)

## 两种风险资产组合
$$
\begin{array}{ll}
\bar{r}_{1}=E\left(r_{1}\right)\\
\bar{r}_{2}=E\left(r_{2}\right) \\
\sigma_{1}^{2}=E\left(r_{1}-\bar{r}_{1}\right)^{2} \\
\sigma_{2}^{2}=E\left(r_{2}-\bar{r}_{2}\right)^{2} \\
\sigma_{12}=E\left(r_{1}-\bar{r}_{1}\right)\left(r_{2}\right. & \left.-\bar{r}_{2}\right)
\end{array}
$$

好，我们现在给第一个分配权重$$w$$，那第二种资产权重是$$1-w$$

组合收益均值：

$$\bar{r}_{p}=E(r)=w \bar{r}_{1}+(1-w) \bar{r}_{2}$$

组合收益方差：
$$
\begin{aligned}
\sigma_{p}^{2} &=E\left[w r_{1}+(1-w) r_{2}-\left(w \bar{r}_{1}+(1-w) \bar{r}_{2}\right)\right]^{2} \\
&=E\left[w\left(r_{1}-\bar{r}_{1}\right)+(1-w)\left(r_{2}-\bar{r}_{2}\right)\right]^{2} \\
&=E\left[w^{2}\left(r_{1}-\bar{r}_{1}\right)^{2}+(1-w)^{2}\left(r_{2}-\bar{r}_{2}\right)^{2}+2 w(1-w)\left(r_{1}-\bar{r}_{1}\right)\left(r_{2}-\bar{r}_{2}\right)\right] \\
&=w^{2} \sigma_{1}^{2}+(1-w)^{2} \sigma_{2}^{2}+2 w(1-w) \sigma_{12}
\end{aligned}
$$

可变的变量是$$w$$，来调整第一个风险资产和第二个风险资产的组合。

那最优的$$w^{*}$$应该是多少好呢？就是这个$$w^{*}$$下，组合收益最大：

$$
\begin{aligned}
&\frac{\partial \sigma_{p}^{2}}{\partial w}=0 \Rightarrow 2 \sigma_{1}^{2} w^{*}-2 \sigma_{2}^{2}\left(1-w^{*}\right)+2 \sigma_{12}-4 \sigma_{12} w^{*}=0 \\
&\quad \Rightarrow 2 \sigma_{1}^{2} w^{*}-2 \sigma_{2}^{2}+2 \sigma_{2}^{2} w^{*}+2 \sigma_{12}-4 \sigma_{12} w^{*}=0 \\
&\quad \Rightarrow \sigma_{1}^{2} w^{*}-\sigma_{2}^{2}+\sigma_{2}^{2} w^{*}+\sigma_{12}-2 \sigma_{12} w^{*}=0 \\
&\quad \Rightarrow\left(\sigma_{1}^{2}+\sigma_{2}^{2}-2 \sigma_{12}\right) w^{*}=\sigma_{2}^{2}-\sigma_{12} \\
&\quad \Rightarrow w^{*}=\frac{\sigma_{2}^{2}-\sigma_{12}}{\sigma_{1}^{2}+\sigma_{2}^{2}-2 \sigma_{12}}
\end{aligned}
$$

那，最好的收益均值（$$\bar{r_p}^{*}$$）是多少？

$$
\begin{aligned}
\bar{r}_{p}^{*} &=w^{*} \bar{r}_{1}+\left(1-w^{*}\right) \bar{r}_{2} \\
&=\frac{\sigma_{2}^{2}-\sigma_{12}}{\sigma_{1}^{2}+\sigma_{2}^{2}-2 \sigma_{12}} \bar{r}_{1}+\left(1-\frac{\sigma_{2}^{2}-\sigma_{12}}{\sigma_{1}^{2}+\sigma_{2}^{2}-2 \sigma_{12}}\right) \overline{r_{2}} \\
&=\frac{\sigma_{2}^{2}-\sigma_{12}}{\sigma_{1}^{2}+\sigma_{2}^{2}-2 \sigma_{12}} \bar{r}_{2}+\frac{\sigma_{1}^{2}-\sigma_{12}}{\sigma_{1}^{2}+\sigma_{2}^{2}-2 \sigma_{12}} \bar{r}_{2} \\
&=\frac{\sigma_{1}^{2} \bar{r}_{2}+\sigma_{2}^{2} \bar{r}_{1}-\sigma_{12}\left(\bar{r}_{1}+\bar{r}_{2}\right)}{\sigma_{1}^{2}+\sigma_{2}^{2}-2 \sigma_{12}}
\end{aligned}
$$

好吧，看图就明白了，最优的点，就是方差最小的这个点：

![](/images/20211013/1634108422355.jpg)

不过这个，曲线可不是一直都是个曲线，当这两种风险资产的相关性（可以用相关系数$$\rho$$来衡量）不同的时候，曲线的形态也不同：

![](/images/20211013/1634108633696.jpg)

## 多种风险资产组合

上面是两种风险资产组合，那一堆（**多种**）资产组合在一起，啥样呢？那就不是个曲线了，而是一个区域了。

![](/images/20211013/1634108782826.jpg)

这个区域中，我们只关心同等风险（标准差）下，收益最大的那个组合，对吧？所以，这些点就形成了一个叫“有效前沿”的曲线：

![](/images/20211013/1634109238225.jpg)

这个求解，组合少的时候，可以用拉格朗日优化方式直接求解，组合比较多的时候，往往通过蒙特卡洛采样得到。





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
- [回形针：为什么你炒股总是亏钱？](https://www.bilibili.com/video/BV11J411K7tw/?spm_id_from=333.788.recommend_more_video.1)
- [柴知道：如何科学投资你的辛苦钱？科学理财为什么这么难？](https://www.bilibili.com/video/av844339890/)，通俗易懂的给你讲了最优风险组合理论。
- [博迪 -《投资学（原书第10版）》](https://book.douban.com/subject/27159606/)，最经典的投资学教材，没有之一。
- [中央财经大学-投资学（国家级精品课）](https://www.bilibili.com/video/BV1C4411X7zU?p=78&t=41)，刘志东老师讲的部分最有用。
- [清华大学 - 投资学](https://www.xuetangx.com/learn/thu02011003130/thu02011003130/5894332/video/9307292)，清华大学的王茵田教授的投资客讲解，也非常通俗易懂。
- [王蓁老师 - 金融量化/股票交易投资教程](https://www.bilibili.com/video/BV1si4y1T7BY?p=4&spm_id_from=pageDriver)，这个是一个难的的专门讲述量化的课程，比一般的那种高频交易，CTA啥的实在有用得多。
- [李锦堂 - 我如何分配我的收入](https://www.bilibili.com/video/BV17b41187PA)，我很喜欢的马来清华小哥，他对标普S&P500的讲解通俗易懂。
- [徐高 -《金融经济学二十五讲》](https://www.bilibili.com/video/BV1Bx411d714)，徐高的金融学，讲的很透彻，强烈推荐。
- [徐高 -《宏观经济学二十五讲：中国视角》](https://www.bilibili.com/video/BV1oE411Z7TU/)，徐高的宏观经济学，讲的很不错。
- [林毅夫 - 中国经济专题北京大学 ](https://www.bilibili.com/video/BV1ob411J7WC/)，了解中国经济，还要听中国经济学家的讲解。