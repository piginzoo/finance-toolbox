## 多元回归

多元回归，是指，因变量是和多个自变量之间存在线性关系。

$$y=\beta_0 + \beta_1 x_1 +  \beta_2 x_2 + ... + \beta_k k + \epsilon$$

$$\epsilon$$是个随机变量，他的期望为0，$$E(\epsilon) = 0$$，方差也是固定的。另外，不同x的输入，得到的$$\epsilon$$，彼此是不相关的，你的和我的，得到的$$\epsilon$$，彼此无关。

### 拟合度评价

跟一元回归一样，我们仍需要判断我们的线性模型拟合的好坏，同样，我们还是用$$R^2$$来作为我们评价拟合程度的指标（这里细节可以翻到一元回归里复习），不过，多元回归中，有个问题：

>当增加变量后，会使预测误差变小，这样残差平方和SSE就变小，SSR=SST-SSE，SST恒定时候，SSR就变大，从而使得$$R^2$$变大，从而高估$$R^2$$。

[教材](https://book.douban.com/subject/30422797/)*上这样说的，不是特别理解，我的理解是，多个变量来解释y，可能会过拟合，导致$$R^2$$变大*。

解决的办法，是使用**调整的多重判定系数（Adjusted Multiple Coefficient of Determination）**：

$$R^2_a = 1 - (1-R^2)\left(\frac{n-1}{n-k-1}\right)$$

这个是考虑了样本量后，做出了调整后的$$R^2$$，更客观。

### 显著性检验

之前，还记得一元回归中，你“线性关系检验-是不是线性”，以及你“系数检验-系数不能为0”，是等价的、一样的，都是验证$$\beta_1 \ne 0$$，只是统计量不同，但是是等价的。

但是，在多元回归中，线性关系检验，和，系数检验就不等价了，原因很简单，系数现在有个多个了，得一个一个地检验了。

比如我有5个系数，其实只有2个是独立的，另外3个是是共线的（就是彼此狠雷同），这样，线性检验是可以通过的，但是，系数检验，就会发现那2个是通过检验，剩下的3个是无法通过检验的。这个时候，就需要出现这些共线系数。

#### 线性关系检验


1、线性关系的检验，转化成这个$$H_0$$假设：

$$H_0: \beta_1 = \beta_2 = ... = \beta_k = 0$$

$$H_1: \beta_1, \beta_2 , ... , \beta_k$$，至少有一个不为0

如果$$H_0$$成立，就不是线性，否则，就是线性。

2、然后，我们构建统计量：

$$F=\frac{SSR/k}{SSE/(n-k-1))} ~ F(k,n-k-1)$$，然后我我们根据我们真实的样本算出这个F值。

这个和一元回归是类似的，只不过那个时候，k=1而已。

3、然后我们给出一个显著水平$$\alpha$$，根据自由度k，去查表达到对应的$$F_{\alpha}$$值。

如果$$F>F_{\alpha}$$，拒绝原假设$$H_0$$，接受备择假设$$H_1$$，即，符合线性关系。否则，不拒绝原假设$$H_0$$，即不符合线性关系。


#### 系数检验

和一元回归类似，对系数检验采用t检验，但是，不同于一元回归，多元回归有多个系数，所以要逐一地进行检验，方法和一元回归一模一样：

统计量为：$$t=\frac{\hat{\beta_i}-\beta_i}{s_{\hat{\beta_i}}},i>0$$，它符合自由度为n-k-1的t分布。

其中，$$s_{\hat{\beta}\_1}=\frac{s_e}{\sqrt{\sum x^2_i - \frac{1}{n}(\sum x_i)^2}}$$。

这样，就可以使用这个统计量做假设检验：

1、提出原假设$$H_0:\beta_i = 0, H_1:\beta_i \ne 0$$

2、计算统计量$$t=\frac{\hat{\beta_1}-\beta_1}{s_{\hat{\beta_1}}}$$

3、给出一个显著水平$$\alpha$$，自由度是n-k-1，查表可得临界值$$t_{\alpha/2}$$，如果$$t>t_{\alpha/2}$$，拒绝原假设$$H_0$$，$$\beta_i \ne 0$$。否则，接受原假设$$\beta_i=0$$。

### 多重共线性

现在有多个变量了，她们彼此之间应该无关的才好，但是她们在一些情况下，可能相关了，书上说，这种相关性是有“毒害”的，是会导致，会让回归方程出现问题，具体什么问题和什么原因，教材上没有说，我也没去深究，就当做结论吧。

既然不好，就要先发现它，然后再消除掉它。

#### 多重性判别

**方法1：做自变量间相关性检验**

就是对变量之间两两做相关性检验，并对这个相关系数，做显著性检验。

这个可以参考“一元回归中相关性分析”章节，计算出相关系数，这里有个细节，既然都算出来相关系数了，干嘛还要做显著性检验，原因是：

>接下来一个问题，$$r$$可不是总体的相关性$$\rho$$，它只是抽样的，那么一个问题是，这个抽样能代表总体么？也就是所谓r的可靠性、显著性。

**方法2：观察对系数检验的结果**

在做多元回归的线性回归F通过后，但是，某些系数检验（也就是某些系数为0了）没有通过，那些系数，可能和别的变量间存在共线性。要警觉了。

**方法3：容忍度（tolerance）、方差扩大因子（viariance inflation factor VIF）**

某个变量的“容忍度（tolerance）” 等于=：把这个变量变成“因变量”，把他变成y（之前的y不要了，暂时扔掉），然后，去算你新造出来这个“y”，和剩余的那些“x”们，他们的判定系数$$R_i^2$$（啥是判定系数$$R_i^2$$来着？数学就怕学了后面的忘了前面的，它是在一元回归的拟合度评价里，来判断，你造的这个回归公式，是不是很好地拟合了真实的y，不过，现在这个y，是你的那个被考察的变量而已）

我理解，就是逼着看看这个变量，假y，是不是可以被其他人（其他x），线性表达出来，如果能，那我还要它干嘛呢？对吧，我是这么理解的。所以，用1减去他，他就会更小（他要是能被别人拟合，他的$$R^2$$J就会很大，$$1-R^2$$就会很小）。

而方差扩大因子：$$VIF = \frac{1}{1-R_i^2}$$，如果共线的话，就会很大（取了倒数了嘛），一般认为大于10，也就是$$1-R^2<0.1$$，也就是$$R^2>0.9$$，就认为，这个变量和别人存在严重共现了。

#### 处理多重性

那共线了，咋办？

第一个方法，就是删，直接给丫删了不就得了，只要想关的都给丫删了。

第二个方法，没看懂！

说是，"对y的推测，要限定在自变量的样本的范围内"，啥意思？我理解是，为了防止共线导致的预测不准，你的x必须要在你过去生成模型的样本的定义域内。那超过了咋办？总之，没太理解，好吧，我将来还是粗暴的用第一种方法把，删删删！

书上，建议，如无必要，尽量用尽可能少的变量，尽量不要引入新变量，恩，牢记！

### 变量选择

上面也提到了，如无必要，尽量选择少的变量，那么，问题就是，如何选？

#### 逐步回归

这种选法，就是一个一个地来，每次增加1个变量，引入后，再查一遍已有的变量的t统计量显著不显著（显著性是啥来着？就是它该不该为0，$$\beta_i \ne 0$$），这里我有个好奇？为何这种显著性还会变？引入一个新的兄弟，你丫（你的显著性）就变了？


统计量为：$$t=\frac{\hat{\beta_i}-\beta_i}{s_{\hat{\beta_i}}},i>0$$，它符合自由度为n-k-1的t分布。

其中，$$s_{\hat{\beta}\_1}=\frac{s_e}{\sqrt{\sum x^2_i - \frac{1}{n}(\sum x_i)^2}}$$。

而
$$
s_{e}=\sqrt{\frac{\sum\left(y_{i}-\hat{y}\_{i}\right)^{2}}{n-2}}=\sqrt{\frac{S S E}{n-2}}=\sqrt{M S E}
$$