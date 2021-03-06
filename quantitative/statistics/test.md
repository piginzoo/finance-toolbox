## 假设检验

啥是假设检验？

参数估计，是用样本去估总体参数，而假设检验，是先假设一个参数情况，然后用样本去验证它，是否靠谱。

举个例子：我假设北京市学生高一男生身高是$$173 \pm 3$$，然后，你去各学校抽样，然后假设检验，你就可以接受这个参数正确的假设，或者推翻这个参数估计正确的假设。

开始这个假设，叫**原假设$$H_0$$/零假设**，它的相反的假设叫**备择假设$$H_1$$**，他们俩互斥，否定一个，意味着接受另外一个。

### 原理

这个假设检验怎么来的呢？怎么就想出这么一个办法，来检验你估计的参数靠谱不靠谱呢？

假设检验，是基于**小概率原理**，所谓小概率原理，是指，“*发生概率很小的事件，在一次实验中几乎是不可能发生的*”。

这里有个几个点：
- 小概率事件，这个概率有多小？一般是0.05，是英国概率学家费希尔给的建议值，大家都沿用了。
- 你假设了一个参数，然后，你用这个参数去算某一次事件的概率，如果这个概率小于0.05，那说明你的假设不靠谱啊，你的假设下，应该大概率发生才对；现在小概率发生了，说明你的假设不对啊。


### 步骤

假设检验的步骤：

1、提出原假设和备择假设，原假设就是你想验证的结论，备择假设是它的方面。

2、指定检验中的显著性水平，就是他们一般说的$$\alpha$$，往往都很小，比如0.05，$$1-\alpha$$就是**置信度**。

3、收集样本数据并计算检验统计量的值，就是算一下样本们的方差啊、均值啊

4、利用检验统计量的值计算**p-值**

5、p-值法的拒绝法则，如果p-值<=显著性水平的值，则拒绝原假设H0

6、解读统计结论

【**p值**是什么，**$$\alpha$$**是什么？】

[参]: [1](https://zhuanlan.zhihu.com/p/26068572)，[2](https://zhuanlan.zhihu.com/p/86178674)，[3](http://www.eastwin-med.com/newsitem/278412468)

其实就是概率，你假设检验了$$H_0$$,那$$H_0$$发生的概率就是**p-value**，而**$$\alpha$$**是阈值，你接受还是拒绝假设的概率阈值。


### 正态检验

看一个序列是不是符合正态分布。话说，正态检验太重要了，如果一个时间序列不符合正态分布，那后面的检验都没有意义了。

常见的有SW检验（样本<50）和KS检验（样本>50），[示例代码](https://github.com/piginzoo/fund_analysis/blob/master/test/test_stat.py)。

#### SW:Shapiro-Wilk检验（小数据<50）


Shapiro-Wilk检验和Lilliefor检验都是进行大小排序后得到的，所以易受异常值的影响。

Shapiro-Wilk检验只适用于小样本场合（3≤n≤50）

$${\left(\sum_{i=1}^n a_i x_{(i)}\right)^2 \over \sum_{i=1}^n (x_i-\overline{x})^2}$$


[参]：[1](https://zhuanlan.zhihu.com/p/26539771),[2](https://www.jianshu.com/p/e202069489a6),[3](https://www.biaodianfu.com/python-normal-distribution-test.html),[4](https://zhuanlan.zhihu.com/p/26477641),[5](https://www.medsci.cn/article/show_article.do?id=0805180e5132)

#### KS:Kolmogorov-Smirnov检验（小数据>50）

柯尔莫戈洛夫-斯米诺夫检验（Kolmogorov-Smirnov test），简称K-S检验

K-S检验适合用于大数据样本的正态性检验，当样本的数据量超过50行时，它被认为是一个大样本，我们倾向于看K-S检验的分析结果得出结论。



### T检验

T检验，又叫做学生T检验，用于样本含量较小（如n<30），总体标准差$$\sigma$$未知的正态分布。

t检验是用t分布理论来推论差异发生的概率，从而**比较两个平均数的差异是否显著**。与f检验、卡方检验并列。