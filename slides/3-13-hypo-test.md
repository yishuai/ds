class: middle, center
# 假设检验

---
# 疫苗有效吗？
- 43,738 志愿者
- 随机分配，一半疫苗，一半安慰剂
- 28天后，43270人没得，468人得了新冠，117 疫苗，351 没疫苗
- 假设检验
  - 假设：疫苗有效

---
# Urn 模型仿真假设检验

NULL 假设：疫苗无效，得不得新冠，概率是一样的

仿真验证：43738个人，468人得了，43270人没得，从中随机采样一半人 21869 人。
50 万次实验

仿真代码

        simulations_fast = np.random.hypergeometric
            (ngood=468, nbad=43270, 
            nsample=21869, size=500000)

---
# 假设检验

平均应该是 234 人得了，但因为采样的随机性，也有少数的情况，会只有 117 人得，这是我们观察到的情况。

统计“只有 117 人得”这种情况，以及比它更极端的情况，就是得的人，还少于 117 人的情况。

这个概率如果很小，那么：NULL 假设的可能性很小，所以，“疫苗有效”的假设很可能有效

---
# 结果

- .center[.width-80[![](./fig/12-theory_vaccine_efficacy_11_0.svg)]]
  - 50万次实验中，每次实验中“得了新冠”人数的分布，没有少于 117 人的
  - 所以，NULL 假设（疫苗无效）成立的概率很小
  - 所以，疫苗很可能有效

---
# 注意

-  基于一部分数据的观察，建立假设后，要用同一来源的另一部分新数据，检验假设
-  切勿使用相同的数据来提出假设，并对其进行检验

???

Brown PPT: https://static.us.edusercontent.com/files/RO89pRh7jHG6gXfx8uodTuEX

“explore”, “analyze trends”, “look for patterns”, “visualize”
- Come up with possible explanations of the observed phenomena
- Formulate hypotheses on the “world” from which the data is observed
- Test your hypotheses using new data from the same source
- Never use the same data to formulate hypotheses and to test them
- Risk of overfitting and false discoveries

- We formulate a priori “null” hypothesis (H0) on the “world” or some phenomena
- You can think of this as some widely held belief
- We then come up with a new “alternative hypothesis” (H1 or Ha) which contradicts the null.
- This is the hypothesis we are interested in testing (our new
belief)
- It is not always complementary to the null
- We obtain some data to test our hypothesis

---
# 假设检验

- 我们对“世界”或某些现象提出先验的 NULL 假设（H0）
    - 你可以认为这是一些广泛持有的信念
    - 疫苗无效
- 然后我们提出一个与 NULL 假设相矛盾的新“替代假设”（H1 或Ha）。
    - 这是我们有兴趣测试的假设（我们的新信仰）
    - 疫苗有效

---
# 假设检验
- 我们不直接测试替代假设 Ha
- 相反，我们测试空假设 H0
- 考虑：遵循 NULL 假设时产生的数据，与观察到的一个或多个极端情况的可能性有多大
- 假设 NULL 假设是正确的，我观察到的现象的可能性有多大？

---
# 假设检验
- 如果现象在 NULL 假设下显得极不可能
    - 我们说：NULL 假设似乎没有正确描述这种现象，所以，可以拒绝 NULL 假设
    - 小心：我们不接受替代假设 Ha 哈
    - 相反，我们只是说：Ha 可能是正确的
- 否则
  - 我们无法拒绝 NULL 假设
  - 小心：我们并不接受 NULL 假设

???
- We do not directly test the alternative Ha
- Rather we test the null H0
- We will consider how unlikely it is that a phenomenon that follows the null
hypothesis has generated data which behaves as the observed one or more
extreme
- Imagine this as saying:
- Assuming that the null is correct and the phenomenon has given properties
- How (un)likely am I to observe the given data!
- If the data appears extremely unlikely under the null hypothesis we reject
the null hypothesis
- We are saying the null hypothesis does not seem to correctly describe the
phenomenon
- CAREFUL: we are NOT accepting the alternative Ha
- Rather we are saying Ha has a possibility of being correct
- Otherwise, we fail to reject the null hypothesis
- CAREFUL: we are NOT accepting H0

???
- We want guarantees on the accuracy of our decisions:
- We would like to say that if we reject/fail to reject a null we
are correct in doing so with some probability (confidence)
- We will get asymptotic guarantees on the accuracy of our
rejections

---
# 假设检验方法
1. 从对数据的一些观察开始
2. 提出一个“研究”（替代）假设 Ha
3. 针对一个“默认”的 NULL假设 H0 进行测试
4. 获取新数据来检验 H0 假设
5. 适当选择统计检验方法，确定数据是否支持 NULL 假设

???
The hypothesis testing method
1. Start from some observation on the data
2. Formulate a “research” (alternative) hypothesis Ha
according to the prescribed rules
3. Test it against a “default” null-hypothesis H0
4. Obtain fresh data to test the hypothesis
5. Using an opportunely chosen statistical test, determine if the data supports the null hypothesis or not

---
# 示例

a,b,c,d 四个选项，随机选择

- 基于一段时间的观察，提出 Null 假设 H0：“b”的概率为 80%
   - X 是二项分布随机变量，参数：12, 0.8

---
# 假设检验

收集新数据:

        a b c b
        a b c c
        d c b d

b: 4, not b: 8

Null 假设 b 的概率是 0.8，但这个 b 才 4：太少了

更极端的情况：b 的数目比 4 更少

---
# 假设检验

计算 NULL 假设下，b 只有 4 个或者更少（更极端的情况）的概率：

P(X ≤ 4) < 0.0006! 非常不可能

所以，倾向于 reject 这个 NULL 假设

---
# 假设检验

如果收集到的新数据是 

        a b b b
        b b b c
        b b b b

b: 10, not b: 2

---
# 假设检验

在 NULL 假设下，b 有 10 个甚至更少（更极端的情况）的概率：

P(X ≤ 10) < 0.73! 还是可能的，所以，

我们没有证据拒绝它

小心：不能说 NULL 假设很可能是正确的！

???

Brown 假设检验 PPT 2：https://static.us.edusercontent.com/files/14HfwdTegHr7oGqhZmqWqaPi

---
# 统计测试

- P(X ≤ n) 是一种统计测试
    - P(X ≤ 4) < 0.0006
    - P(X ≤ 10) < 0.73
- 为我们提供了一种方法，来衡量数据“支持我们的假设”的程度

---
# p 值
- 0.0006，0.73 表示“实验数据以及比它更极端的情况”在 NULL 假设下出现的概率
- 这个概率越小，我们 Reject NULL 假设的“信心”就越大
  - 设置一个判决门限，比如 0.05
  - 小于这个门限，就 Reject NULL 假设

---
# 判决门限

- 0.05
- 我们人为设置的一个标准，决定假设何时可以被拒绝
- 它代表了：决定拒绝 NULL 假设时，观察到的数据应该“多么令人惊讶”（即，多么不可能）
- 表示决策的置信度

???
statistical tests which give us a way to measure how much the data “supports our hypothesis”

idea of p-value which gives us a criteria for deciding which hypotheses can be rejected with some guarantee

Normal or Gaussian Distribution

The values less than one standard deviation away from the mean account for 68.27% of the set
- Within two standard deviations from the mean account for 95.45%
- Within three standard deviations account for 99.73%.

Central Limit Theorem

The distribution of the sample average of n
independent and identically distributed samples from a distribution with expected value $\mu$ and finite variance $\sigma^2/n$ converges to a normal distribution with expected value $\mu$ and variance $\sigma^2/n$ as n → ∞

- Let X be the number of heads obtained when flipping a fair coin 12 times.
- This is binomial random variable with expected value 0.5×12 = 6

- We can apply statistical methods designed for normal distributions even when underlying distribution is not normal

A hypothesis is a claim (assumption) about a population parameter:

Is always about a population parameter, not about a sample statistic

The blueprint

- Formulate alternative hypothesis Ha
- Analyze null hypothesis H0
- Set up experiment
- Select an appropriate statistical test and a test statistic
- Come up with a priori theoretical distribution for the test statistic
- This is is often already given in the definition of the statistical test and H0
- Select a threshold 0 ≤ � ≤ 1 value for “how surprising” (i.e., how unlikely) under the current assumption H0 the observed data should be in order to decide to reject the null
- � will denote the level of confidence of the decision
- If the threshold is used to state the level of confidence which whom we want to decide on rejection

---
# 统计检验方法

- 分析 NULL 假设，设计实验
  - 选择合适的假设测试
  - 确定统计量，确定该统计量的先验统计分布
- 获取数据
- 计算在 NULL 假设下，观察数据出现的概率
- 将该概率与 p 值比较，决定是否可以拒绝 NULL 假设

---
# 小心我们的表述
- 我们只是拒绝 NULL 假设，并不是证明它不正确
  - 我们只是说，根据数据，不太可能是正确的
- 拒绝 NULL 假设 并不意味着原假设（替代方案）是“正确的”
  - 只是我们不能排除它！
  - 不要说：我们“接受”原假设
- 我们的拒绝是有“置信度”的

---
# 示例：测试硬币的公平性
- H1：“这枚硬币有偏见”
- H0：“这枚硬币是公平的”

---
# 测试过程
- 独立抛一枚硬币 20 次，每次分布相同
- 统计出现正面的数量 X
  - “检验统计量” = 4
- 假设 NULL 假设是正确的，计算观察到至少与 X 一样极端的结果的概率 p
  - p 值
- 设置阈值 0 ≤ a ≤ 1，如果 p ≤ a，则拒绝 NULL 假设
  - a：所需的置信水平

---
# 注意

获取数据之前需要确定测试程序，包括：
- 样本数量
- 统计测试类型
- 阈值

???

- Acquire data
- Compute the likelihood of observing the test statistic under the null hypothesis
- p-values!
- Compare the computed value with � and decide if it is possible to reject the null hypothesis

Careful with your terminology!
- Just because we reject a null hypothesis it does not
mean we are proving it not to be correct
- We are merely saying that, given the data, it is unlikely to
be correct
- We can fix the level of confidence of this kind of statement
- Rejecting a null does not imply that the alternative is
“correct”
- Just we cannot exclude it!
- Avoid the terminology “accepting the alternative”

Example: testing the fairness of a coin
H1: “this coin is biased”
H0: “this coin is fair”

Testing procedure
- We flip the coin 20 times independently and with the same distribution
- We count the number of heads called X
- The “test statistic”
- We compute the probability p of observing a result at least as extreme as X
assuming the null hypothesis is correct (“under the null hypothesis”)
- the p-value
- We set a threshold 0 ≤ a ≤ 1 such that if the null hypothesis is rejected if
p ≤ a
- The desired confidence level
The testing procedure, including the number of samples, type of statistical
test and threshold need to be fixed before obtaining the data!!

---
# 显着性水平

- 门限 a
  - Level of significance a
  - 许多术语：临界水平/控制水平/临界阈值...
- 拒绝区域
  - p 值 < a
- 限制做出错误决定的可能性
- 反映了我们想有多确定？
- 示例：a = 0.05
  - 5% 的情况下我们会偶然拒绝正确的 NULL 假设

???
Level of significance a

How certain do you want to be?
- Many terminologies: Critical level/control level/critical threshold...
- Example: Significance level of 0.05
- 5% of the time we will observe higher mean by chance
- 95% of the time the higher mean will be real
- a bounds the likelihood of making wrong decisions
- 5% of the time we will reject a correct null by chance

We use a to determinate the rejection region
- All the values whose likelihood of being observed is < a
- X is within the rejection region

---
# p 值

- 在 H0 下，获得比观察到的样本值更极端（≤ 或 ≥）的检验统计量的概率
- 也称为“观察到的显着性水平”
- 两种 p 值
  - 单边测试（one tail）
  - 双边测试（two tail）

---
# 双边测试

- H1：“这枚硬币有偏见”
- H0：“这枚硬币是公平的”

- 出现正面的“检验统计量” = 4
- 假设 NULL 假设是正确的，计算观察到至少与 X 一样极端的结果的概率 p
  - p 值
  - 双边测试：两边都极端 H <= 4, T <= 4

---
# 单边测试

- H1：“这枚硬币偏向尾部”
- H0：“这枚硬币不偏向尾部”

- 出现正面的“检验统计量” = 4
- 假设 NULL 假设是正确的，计算观察到至少与 X 一样极端的结果的概率 p
  - p 值
  - 单边测试：H <= 4 是极端的

???

A slightly different question
H1: “this coin is biased towards tail”
H0: “this coin is not biased towards tail”

Unidirectional
Probability of a result at
least as extreme as X 

只看偏 H

p-value
- p-value: Probability of obtaining a test statistic more extreme ( ≤ or ≥ ) than the observed sample value given H0 is true
- Also called observed level of significance
- Function of the data takes values in [0,1]
more extreme： ( ≤ or ≥ )

As n → ∞, the p-value p is a random variable
whose pmf is uniform in [0,1] if the nullhypothesis is correct
- Assume we set a = 0.05:
- Pr p ≤ 0.05 = 0.05!

---
# 单样本 vs 双样本测试
- 单样本测试
  - 有来自一个群体的观察结果（样本）
  - 想将它们与固定模型或分布进行比较
  - 例如，此分布的均值为 0.5
- 双样品测试
  - 有来自两个群体的观察结果（样本）
  - 希望通过观察来比较两个群体的统计特性
  - 例如，这两个分布是相同的，它们相同的均值
- 许多重要的测试都有这两种版本

???

One sample vs two samples test
- One sample tests:
- We have observations (samples) from one population, we
want to compare them with a fixed model or distribution
- E.g., this distribution as mean �
- Two samples tests:
- We have observations (samples) from two populations
- We want to compare statistical properties of the two
populations through the observations
- E.g., these two distributions are the same, they have the
same average, ....

Many important test have both versions

---
# 选择合适的测试

- 有点像根据下面的成分找到正确的菜谱
  - 假设类型
  - 数据类型
  - 样本量
  - 方差已知？几个组的方差相等吗？

---
# 选择合适的测试

- 好消息：有很多表可用，例如
- UCLA ATS 统计测试选择表，R, SAS, Stata, SPSS 示例，[网页](http://www.ats.ucla.edu/stat/mult_pkg/whatstat/default.htm)
- PSU 统计测试总结表，[PDF](http://sites.stat.psu.edu/~ajw13/stat500_su_res/notes/lesson14/images/summary_table.pdf)
- How to select appropriate statistical test? [PDF](https://www.tnstate.edu/eduadmin/Statistics.pdf)

???
Select your test
- Testing is a bit like finding the right recipe based on
these ingredients:
- Type of hypothesis
- Data type
- Sample size
- Variance known? Variance of several groups equal?
- Good news: Plenty of tables available, e.g.,
- http://www.ats.ucla.edu/stat/mult_pkg/whatstat/default.htm (with examples in R, SAS, Stata, SPSS)
- http://sites.stat.psu.edu/~ajw13/stat500_su_res/notes/lesson14/images/summary_table.pdf

---
# t-test

- 均值差异
  - 两个群体某些特征的不同的均值
- 例如
  - 男人比女人高吗？
  - 电信学生比其他专业的学生努力吗？

???
t-test: difference of means; is the average value of some feature different between two populations
- e.g., Are men taller than women? 
- Are blue states more populated than red states? 
- Do CS students work harder than other majors?

---
# t-test 

- Ha = Mean age is not 35
- H0 = Mean age is 35

- 单样本测试
- 双边测试

---
# 假设检验

- 测量新数据
    - n：数据点数
- 计算测试统计 z
  - z 符合参数为 0,1 的正态分布
- 计算观察到至少像它这样，以及更极端的情况的似然率：p-value
    - 查表法
    - 双边
- 看 p 是不是小于门限 a
    - 小于，就说明确实很极端，可以 reject H0

---
# 假设检验

- 方法 2
- 根据设定的 a，查表，得到对应的 p
    - 因为是双边，就查 a/2
- 看 z 是不是大于这个 p
    - 大于，就说明确实很极端，可以 reject H0

---
# 单边（one tail）

Ha = “the average age is less than 35”

类似上面的过程，但要查单边的

---
# 两样本 t 检验
- 使用两样本的 t-test 来比较两个观察群体的平均值
- 观察从每个群体中抽取的样本集合
- 假设样本独立
- 假设两个群体中的值呈正态分布
- 甚至可以用于具有不同方差的群体

---
# 计算每个群体测量数据的实验方差
- 计算合并方差
- 检验统计量 t
- 自由度：(n − 1 + m) − 1
- 使用表格计算 p 值
- 将 p 值与设定的置信度 a 进行比较

---
# 非参数测试
- 如果数据很小，不接近正态分布怎么办？
  - 如果样本量非常小，可能无法测试正态性
  - 可以基于您对数据的理解
- 当无法安全地假设正态性时，用不假设正态性的非参数检验

---
# 非参数测试
- 非参数检验非常稳健
  - 无论数据分布如何都可以使用
  - 不依赖于正态分布或 CLT 的假设
- 这非常有用，因为在实践中我们很难检查这些假设的正确性
- 但当然，没有什么是完美的：检测能力有限

---
# 主要思想
- “我观察到的结果是随机噪声的结果，还是代表统计上显着的现象？”
- “假设 NULL 假设为真，观察到的结果至少与数据一样极端的可能性有多大？”

---
# 排列测试（Permutation）

- 为数据添加一些随机性
- 然后评估扰乱后数据的测试统计量
- 评估观察数据在随机后的数据中的极端程度
- 如果很奇特（例如，在 5% 中），那么它很可能不仅是由于偶然性
- 拒绝 NULL 假设

---
# 非参数测试
- The Rank-Sum Test (Mann-Whitney U test)
- Wilcoxon Signed-Rank Test for Paired Data

---
# 卡方 $X^2$ 检验

- 检验离散变量
- 一个离散变量的取值的频率差异
  - 离散取值均匀分布
  - 本社区在各种音乐的偏好方面，是否存在差异？
- 比较两个离散随机变量的分布
  - 两个大学专业的学生，人口特征分布是否不同？
  - 对两个连续变量，最好使用 Kolmogorov-Smirnoff 检验

???
chi-squared X^2-test: 

difference in frequencies of a categorical variable; is the distribution of some feature uniform across groups
- Used to compare distributions of discrete random variables: for continuous ones is better to use Kolmogorov-Smirnoff test

- e.g. Do neighborhoods differ in terms of music preferences? 
- Do college majors differ in terms of sociodemographic features?

---
# 离散变量取值分布

多选题的四个选项的概率分布

H0 = all answers are equally likely

Chi Squared Test

???
X2 test statistic

Pearson showed that z’s distribution converges to X2 distribution as n → ∞

Degrees of freedom are the values that the discrete distribution being observed can assume +1

---
# 课堂练习

- 假设检验
  - 你心仪职位的职责中，有没有需要做单样本和双样本假设检验的？请各举一个例子
  - 说明你举的例子，是 one tail，还是 two tail
  - 请选择合适的统计测试，如 t-text、Chi Squared test，并说明测试过程

???
Brown 假设检验 PPT 3

Multiple Hypotheses Testing

https://static.us.edusercontent.com/files/j6D0olYYsQJRCT5Wtl74KZrf

- Problems with hypothesis testing
- p-hacking
- Publication Bias
- Multiple hypothesis testing
- Family Wise Error Rate
- False Discovery Rate

P-Values

It is NOT the probability that the null or the alternative hypothesis are correct or incorrect 

Probability of observing an effect equal to or more extreme than the one observed, assuming the null hypothesis is true

---
# 课堂测试

运行一个测试，获得 p 值 p = 0.05。

这意味着原假设有 5% 的机会为真
- a) 同意
- b) 不同意
- c) 不确定

???
We run a test and we obtain a p-value p=0.05.
This means that the null hypothesis has a 5% chance of being true
a) Agree
b) Disagree
c) Cannot say

---
# 课堂测试

我们运行一个测试，获得 p 值 p=0.05。

此时，如果我们拒绝 NULL 假设，则该决策是错误的概率（Null 其实为真）最多为 5%

- a) 同意
- b) 不同意
- c) 不确定

???
We run a test and we obtain a p-value p=0.05.

If we reject the null, the probability of that being a wrong
decision (thus assuming the null is true) is at most 5%

a) Agree
b) Disagree
c) Cannot say

You read a study showing that a new drug leads to a significant decrease in cholesterol. You later read a newer study that shows that there is a decrease in cholesterol but it is not statistically significant. These studies are contradictory, one of them must be wrong.
a) Agree
b) Disagree
c) Cannot say

I test a new cancer treatment and find a statistically significant
decrease in tumor size for patients receiving the treatment
compared to a control group. I should prescribe this treatment to all of my patients now

A p-value p=0.05 means that the probability of observing
a statistical phenomena at least as extreme as the one
seen in the data is at most 0.05 assuming the nullhypothesis is correct

Effect Size

([Mean of experimental group] - [Mean of control group])/Standard deviation

- The higher the effect size, the stronger the apparent impact of the recommended method/procedure
- Something that measures how “good” the result is
- Not just “significant” - how significant?
- Used prolifically in meta-analysis to combine results from multiple studies
- Careful! Averaging results from different experiments can produce nonsense
- Caveat: Other definitions of effect size exist: odds-ratio, correlation coefficient

Publication Bias: the decline effect

As the study size increases, the effect size diminishes (Rhine 1934 )
- The largest the study size the lower the effect size
- Lower effect size à weaker apparent statistical evidence supporting the result

Spurious correlations

BROWN PPT 4 Non-parametric testing
https://static.us.edusercontent.com/files/yNhpY3sAtVgyhJzUM06hX4T8

- Limits of normal-distribution based testing
- Non-parametric testing
- Permutation testing
    - One sample
    - Two sample
- Rank-Sum test
- Signed-Rank test

Two-sample t-tests
- We can use a two-sample t-test to compare the means of two observed populations
- We observe a collection of samples drawn from each population
- We assume samples are independent
- We assume that the values in the two populations are normally distributed
- Can be used even with populations with different variance

Compute the empirical variances of each population
- Compute the pooled variance
- Test statistic t 
- Degrees of freedom ( nm − 1 + nw) − 1
- Compute p-value using a table
- Compare p-value with set level of confidence a

Can we always use this test?
- What if my data is small and not nearly normally distributed?
- If your sample sizes are very small, you might not even be able to test for normality
- You might need to rely on your understanding of the data.
- When you cannot safely assume normality, you can perform a nonparametric test that doesn’t assume normality.

Non-parametric testing
- Non-parametric tests are very robust:
- Can be used regardless of the distribution of the data
- They do not rely on assumptions on normal distributions or the CLT
- This is extremely useful as in practice we can hardly check the correctness of these assumptions
- But of course, nothing is perfect: What you gain in robustness you lose in power
- The main idea is still the same we used so far:
- “Is what I am observing a result of random noise, or representative of a statistically significant phenomenon?”
- “Assuming the null hypothesis is true, how likely it is to observe a result as least as extreme as the one from the data?”

Permutation tests

- The word permutation refers to the arrangement of a (multi)set of objects into some specified order.

- New idea: “Let us add some randomness to the data”
- We then evaluate our test statistic on the scrambled data
- We want to decide how extreme our initial evaluation (on the unscrambled data) is with respect to the distributions of the
randomized ones
- If the initial observation is still peculiar (E.g., in the 5% of the values obtainable adding randomness) then we interpret it as evidence of the fact that the observed phenomenon is not just due to chance
- We reject the null hypothesis J
- What is going to be the confidence of this decision?

- One-sample permutation test to compare means

The Rank-Sum Test (Mann-Whitney U test)

Two-samples permutation to compare distributions

Wilcoxon Signed-Rank Test for Paired Data
    Used to study the distribution of the difference of paired observations

CHOOSING THE CORRECT STATISTICAL TEST IN SAS, STATA, SPSS AND R

https://stats.oarc.ucla.edu/other/mult-pkg/whatstat/

Technical Notes
How to select appropriate statistical test?

    https://www.tnstate.edu/eduadmin/Statistics.pdf

---
# 课堂编程

Brown CS1951a Lab 3：Stats

文件：hypo-test.ipynb

---
# 课堂编程

两部分内容：
1. 基于好莱坞电影数据集，介绍 
   1. z-test
   2. two samples t-test
   3. chi-squared test

2. 警察逮捕数据，回答关于无家可归的人被捕时是否被区别对待的问题
  1. 被起诉
  2. 被抓时的警察人数

---
# 作业

Brown CS1951a HW 4：Regression & Stats， [Webpage](https://cs1951a-summer2021-brown.github.io/assignments/stats/stats-summer2021.html)

Part 2, 假设检验

数据：大学入学数据，435 名学生

---
# 作业

两个工作：

1. 实现
- t-test
  - one sample
  - two sample
  - paired
- chi-sqare 独立性测试

文件：stats_tests.py

---
# 作业

2. 针对 5 种不同的场景，选择合适的假设检验方法

文件：run_tests.py