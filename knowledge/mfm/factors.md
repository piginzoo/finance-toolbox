# 因子列表
  * [市场因子](#市场因子)
  * [市值因子](#市值因子)
  * [动量因子](#动量因子)   
  * [CLV因子](#CLV因子)
  * [PEG因子](#PEG因子)
  * [换手率因子](#换手率因子)
  * [特质波动率因子](#特质波动率因子)


## 市值因子
参考：https://zhuanlan.zhihu.com/p/161706770

规模因子 - 市值因子Market Value

## 动量因子
动量因子，动量因子是指与股票的价格和交易量变化相关的因子，常见的动量因子：一个月动量、3个月动量等。
计算个股（或其他投资标的）过去N个时间窗口的收益回报：
```
adj_close = (high + low + close)/3
adj_return = adj_close_t - adj_close_{t-n}
```
来计算受盘中最高价和最低价的调整的调整收盘价动量，逻辑是，在日线的层面上收盘价表示市场主力资本对标的物的价值判断，
而最高价和最低价往往反应了市场投机者的情绪，同时合理考虑这样的多方情绪可以更好的衡量市场的动量变化。

计算动量，动量，就是往前回溯period个周期，然后算收益，
由于股票的价格是一个随经济或标的本身经营情况有变化的变量。那么如果变量有指数增长趋势（exponential growth），
比如 GDP，股票价格，期货价格，则一般取对数，使得 lnGDP 变为线性增长趋势（linear growth），
为了防止有的价格高低，所以用log方法，更接近，参考：https://zhuanlan.zhihu.com/p/96888358

本来的动量用的是减法，这里，换成了除法，就是用来解决文中提到的规模不同的问题    
    
参考：
- https://zhuanlan.zhihu.com/p/96888358
- https://zhuanlan.zhihu.com/p/379269953

## CLV因子
clv: close location value,

`( (close-day_low) - (day_high - close) ) / (day_high - day_low)`

这玩意，是一个股票的，每天都有，是一个数，
我们要从一堆的股票N只中，得到N个这个值，可以形成一个截面，
用这个截面，我们可以拟合出β和α，
然后经过T个周期（交易日），就可以有个T个β和α，
因子长这个样子：
```
trade_date
 	      	000001.XSHE  000002.XSHE
2019-01-02  -0.768924    0.094851    
```
类比gpd、股指（市场收益率），这个是因子不是一个啊？而是多个股票N个啊？咋办？

参考：https://www.bilibili.com/read/cv13893224?spm_id_from=333.999.0.0

## 特质波动率因子
所谓"特质波动率"： 就是源于一个现象"低特质波动的股票，未来预期收益更高"。

好，那啥是**特质**、啥是**波动率**？

特质，其实就是你无法解释的价格上的异象，比如，你用fama-french三因子无法解释的残差部分，就是这个值股票的特质。

波动率，我们往往用方差来衡量。

所以，**"特质波动率"**，就是看残差的方差结果，通俗易懂吧（继续吐槽，网上的各种讲的云山雾罩的文章）。

### 参考

- https://www.joinquant.com/view/community/detail/b27081ecc7bccfc7acc484f8a63e2459
- https://www.joinquant.com/view/community/detail/1813dae5165ee3c5c81e2408d7fe576f
- https://zhuanlan.zhihu.com/p/30158144
- https://zhuanlan.zhihu.com/p/379585598
- https://mp.weixin.qq.com/s/k_2ltrIQ7jkgAKhDc7Vo2A
- https://blog.csdn.net/FightingBob/article/details/106791144
- https://uqer.datayes.com/v3/community/share/58db552a6d08bb0051c52451


>特质波动率(Idiosyncratic Volatility, IV)与预期收益率的负向关系既不符合经典资产定价理论，
也不符合基于不完全信息的定价理论，因此学术界称之为“特质波动率之谜”。

>该因子虽在多头部分表现略逊于流通市值因子，但在多空方面表现明显强于流通市值因子，
说明特质波动率因子具有很好的选股区分能力，并且在空头部分有良好的风险警示作用。

>基于CAPM的特质波动率 IVCAPM: 就是基于CAMP的残差的年化标准差来衡量。
基于Fama-French三因子模型的特质波动率 IVFF3： 就是在IVCAMP的基础上，再剔除市值因子和估值因子后的残差的年化标准差来衡量。

### 细节实现

特质波动率，可以有多种实现方法，可以是用CAMP市场的残差，也可以是Fama-Frech的残差，或者其他的模型，都成。

这里，我用的是Fama-Frech三因子，简称FF3，的残差。

啥叫FF3的残差，就是，用Fama定义的模型，先去算因子收益，比如使用股票池（比如中证500），去算出来的全市场的SML、HML因子收益率。

注意哈，这里的SML、HML就是因子收益率，不是因子暴露（或者有人叫因子值），这俩玩意不一样，再次强调，因子收益率是全市场1天就一个值（大家共享这个值）；而因子暴露，是1只股票1天就一个值。再次强调一下哈。

这里有了SML和HML两个因子收益了，三因子啊，还缺一个？对！缺市场收益，你可以用上证指数，我代码里用的是我股票池的收益率，
比如我用的中证500的股票池的话，我就用中证500的指数收益率。

你准备好三因子收益率，你就可以对市场中的所有股票进行回归了：
对，这里回归，使用的是一只股票池中的所有日子的数据来回归，FF3，就是为了解释这个股票的定价的嘛。

$$\tilde{r}_{i}-r_{f}=\alpha_{i}+\beta_{i M}\left(\tilde{r}_{M}-r_{f}\right)+\beta_{i s} \tilde{S} M B+\beta_{i h} \tilde{H} M L+\tilde{\varepsilon}_{i}$$


我们再来看看原始的FF3表达式，这里$$r_f$$我们省了，为何省？搞起来麻烦，恩，就是这么任性。

这里的下标$$i$$是股票序号，某只股票。

我们利用这个式子，得到$$e_i$$，i是某只股票的序号，不赘述了。但是，这个$$e_i$$，可不是一个数，是一堆数，
多少个呢？这种股票有多少天数据，就有多少个残差。这个就是我们要的这种股票的**特质**。

那波动率呢？

就是计算你回测周期的内的标准差 * $$sqrt(T)$$，比如你回测周期是20天，那就是把招商银行这20天的特异残差求一个标准差，然后再乘以根号下$$T$$。这个值，是这20天共同拥有的一个"特异波动率"，对，这20天的因子暴露值，都一样，都是这个数！

特异波动率的表达式：

$$IVFF_{i, t}=\operatorname{Std}\left(\varepsilon_{i, t}\right) \cdot \sqrt{T}$$

特别说一下，这个$$T$$，文章里说，用的是一年的时间，取T=243，代表1年内交易日天数。

上式中的下标小$$t$$，指的是你的调仓期。


## PEG因子
参考：
- https://zhuanlan.zhihu.com/p/29144485
- https://www.joinquant.com/help/api/help#factor_values:%E6%88%90%E9%95%BF%E5%9B%A0%E5%AD%90
- https://www.joinquant.com/view/community/detail/087af3a4e27c600ed855cb0c1d0fdfed
在时间序列上，PEG因子的暴露度相对其他因子较为稳定，在近一年表现出较强的趋势性
市盈率相对盈利增长比率PEG = PE / (归母公司净利润(TTM)增长率 * 100) # 如果 PE 或 增长率为负，则为 nan
对应tushare：netprofit_yoy	float	Y	归属母公司股东的净利润同比增长率(%)

财务数据"归属母公司股东的净利润同比增长率(%)"的取得：https://tushare.pro/document/2?doc_id=79
```
    输入参数
        ts_code	str	Y	TS股票代码,e.g. 600001.SH/000001.SZ
        ann_date	str	N	公告日期
        start_date	str	N	报告期开始日期
        end_date	str	N	报告期结束日期
        period	str	N	报告期(每个季度最后一天的日期,比如20171231表示年报)
    输出参数
        ts_code	str	Y	TS代码
        ann_date	str	Y	公告日期
        end_date	str	Y	报告期
```
这里的逻辑是，某一天，只能按照公告日期来当做"真正"的日期，毕竟，比如8.30号公告6.30号之前的信息，
加入今天是7.1日，所以只能用最近的一次，也就是最后一次8.30号的，
再往前倒，比如6.15号还发布过一次，那6.15号之后到6.30号，之间的，就用6.15好的数据，
所以，报告期end_date其实没啥用，因为他是滞后的，外界是无法提前知道的。
这样处理也简单粗暴，不知道业界是怎么处理的？我感觉应该很普遍的一个问题。
```
            shift(-1)
current     next
            2021.1.1
---------------------
2021.1.1    2021.3.1
2021.3.1    2021.6.30
2021.6.30   2021.9.30
2021.9.30
---------------------
2021.1.1之前的，不应该用2021.1.1去填充，但是，没办法，无法获得再之前的数据，只好用他了
2021.9.30之后的，都用2021.9.30来填充
```
季报应该是累计数，为了可比性，所以应该做一个处理
研报上的指标用的都是TTM
PE-TTM 也称之为 滚动市盈率
TTM英文本意是Trailing Twelve Months，也就是过去12个月，非常好理解
比如当前2017年半年报刚发布完，那么过去12个月的净利润就是：
2017Q2 (2017年2季报累计值) + 2016Q4 (2016年4季度累计值) - 2016Q2 (2016年2季度累计值)

## 换手率因子

换手率因子：

- https://zhuanlan.zhihu.com/p/37232850
- https://crm.htsc.com.cn/doc/2017/10750101/6678c51c-a298-41ba-beb9-610ab793cf05.pdf  华泰~换手率类因子
- https://uqer.datayes.com/v3/community/share/5afd527db3a1a1012acad84c

换手率因子是一类很重要的情绪类因子，反映了一支股票在一段时间内的流动性强弱，和持有者平均持有时间的长短。
一般来说换手率因子的大小和股票的收益为负向关系，即换手率越高的股票预期收益越低，换手率越低的股票预期收益越高。

四个构造出来的换手率类的因子（都是与股票的日均换手率相关）：
- turn_Nm：个股最近N个月的日均换手率，表现了个股N个月内的流动性水平。N=1,3,6
- bias_turn_Nm：个股最近N个月的日均换手率除以个股两年内日均换手率再减去1，代表了个股N个月内流动性的乖离率。N=1,3,6
- std_turn_Nm：个股最近N个月的日换手率的标准差，表现了个股N个月内流动性水平的波动幅度。N=1,3,6
- bias_std_turn_Nm：个股最近N个月的日换手率的标准差除以个股两年内日换手率的标准差再减去1，代表了个股N个月内流动性的波动幅度的乖离率。N=1,3,6

这是4个因子哈，都是跟换手率相关的，他们之间具备共线性，是相关的，要用的时候，挑一个好的，或者，做因子正交化后再用。

市值中性化：换手率类因子与市值类因子存在一定程度的负相关性，我们对换手率因子首先进行市值中性化处理，从而消除了大市值对于换手率因子表现的影响。

知乎文章的结论：进行市值中性化处理之后，因子表现有明显提高。在本文的回测方法下，turn_1m和std_turn_1m因子表现较好。