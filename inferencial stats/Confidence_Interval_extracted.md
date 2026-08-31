# Extracted content from Confidence_Interval.ipynb

Notebook format: nbformat 4.0

## Notebook metadata

{
  "colab": {
    "provenance": [],
    "collapsed_sections": [
      "r9aj6x8i1d4y",
      "P4-mjU9qulVQ"
    ]
  },
  "kernelspec": {
    "name": "python3",
    "display_name": "Python 3"
  },
  "language_info": {
    "name": "python"
  }
}


## Cells


================================================================================
CELL 1 — MARKDOWN
================================================================================

# Population Mean Confidence Intervals for Larger Sampels


================================================================================
CELL 2 — MARKDOWN
================================================================================

><strong>Note</strong>: <font color='red'>$\overline{x}$</font> is the mean of single sample,  <font color='red'>$\mu_{x}$</font> is the mean of the sampling distribution of the sample mean and <font color='red'>$\mu$</font> is the population mean


================================================================================
CELL 3 — MARKDOWN
================================================================================

<ol style="font-size:120%;">
<li>Consider the poplulation mean is <font color='red'>$\mu$</font>, and suppose you have taken a sample and calculated its mean as <font color='red'>$\overline{x}$</font></li>
<li>Often for a given population we don't know what is the values of <font color='red'>$\mu$</font></li>
<li> Here we try to esitmate the <font color='blue'> <i>unknown</i> <font color='red'>$\mu$</font> </font>with the help of <font color='blue'> known value <font color='red'>$\overline{x}$</font> </font> </li>
</ol>


================================================================================
CELL 4 — MARKDOWN
================================================================================

[Empty cell]


================================================================================
CELL 5 — MARKDOWN
================================================================================

[Empty cell]


================================================================================
CELL 6 — MARKDOWN
================================================================================

__<font  color='#7300e6'>Q: Here “Why do we need a sample mean to calculate the population mean? why can't we directly calcualte the mean of the population?” </font>__
<img src='https://i.imgur.com/rgWfmCf.png' width=150>


================================================================================
CELL 7 — MARKDOWN
================================================================================

<font color='#339933'>
Ans: Suppose your population of interest in Delhi, and you want to know the mean age of the population.
<ul>
<li>Due to lack of time, energy, and money, you cannot obtain the age of every person in Delhi.</li>
<li>You can select a sample (e.g. a simple random sample) and calculate the mean of that sample, <font color='red'>$\overline{x}$</font></li>
</ul>
</font>


================================================================================
CELL 8 — MARKDOWN
================================================================================

__<font  color='#7300e6'>Q: Then “Why don’t we just use the sample mean  <font color='red'>$\overline{x}$</font> to estimate the population mean <font color='red'>$\mu$</font>?” </font>__
<img src='https://i.imgur.com/rgWfmCf.png' width=150>


================================================================================
CELL 9 — MARKDOWN
================================================================================

<font color='#339933'>
<ul>
<li>We can – but the sample mean <font color='red'>$\overline{x}$</font> may be quite different from the population mean <font color='red'>$\mu$</font>,even if we obtained the sample correctly.</li>
    
<li>In addition, a single number estimate by itself, such as <font color='red'>$\overline{x}$</font>, provides no information about the precision and reliability of the estimate with respect to the larger population. </li>

</ul>
</font>


================================================================================
CELL 10 — MARKDOWN
================================================================================

[Empty cell]


================================================================================
CELL 11 — MARKDOWN
================================================================================

[Empty cell]


================================================================================
CELL 12 — MARKDOWN
================================================================================

[Empty cell]


================================================================================
CELL 13 — MARKDOWN
================================================================================

<p style="font-family:'Georgia';font-size:18px" >
Statisticians use the sample statistic <font color='red'>$\overline{x}$</font> and the population(<font color='red'>$\sigma$</font>) or sample standard deviation to provide <font color='blue'>an interval of plausible estimates</font> for the population parameter <font color='red'>$\mu$</font>. This interval is called a <font color='blue'>confidence interval.</font>
</p>


================================================================================
CELL 14 — MARKDOWN
================================================================================

> <strong>Definition:</strong> A confidence interval is an entire interval of plausible values for a population parameter, such as <font color='red'>$\mu$</font>, based on observations obtained from a random sample of size <font color='red'>$n$</font>.


================================================================================
CELL 15 — MARKDOWN
================================================================================

### Let us answer a question


================================================================================
CELL 16 — MARKDOWN
================================================================================

><font color=#EB07BA > __What is the avarage money spent by Male population on black friday ?__</font>


================================================================================
CELL 17 — MARKDOWN
================================================================================

Before we know how to estimate that lets have a look at couple of concepts
<h3>1. <font color='blue'><a href='https://en.wikipedia.org/wiki/Standard_error'>Standard error</a> </font> </h3>
<pre>

<li>The standard error (SE) of a statistic (usually an estimate of a parameter) is the standard deviation of its sampling distribution or an estimate of that standard deviation.</li>
<li>If the parameter or the statistic is the mean, it is called the standard error of the mean (SEM). </li>
<li>The standard error of the mean (SEM) can be expressed as: </li>
</pre>
$$\sigma_\overline{x}=\frac{\sigma}{\sqrt{n}}$$
<pre>
Since the population standard deviation is seldom known, the standard error of the mean(SEM) is usually estimated as the sample standard deviation divided by the square root of the sample size (assuming statistical independence of the values in the sample).
</pre>
$${\displaystyle {\sigma }_{\bar {x}}\ \approx {\frac {s}{\sqrt {n}}}} $$


<h3>2. <font color='blue'> $zScore$</font> and Confidence Levels:</h3>

<ul>
    <li>Let $\alpha$ be a number between 0 and 1, and let 100 * (1 – $\alpha$)% denote the confidence level.
    <br>For example,
        <ul>
        <li>if $\alpha$ = 0.05, then the corresponding confidence level is 95%. </li>
        <li>If $\alpha$= 0.01, then the confidence level is 99%.</li>
        </ul>
    </li>
    <li>
        Suppose we have a standard normal distribution $Z$. <br>Let $z_\frac{\sigma}{2}$ denote a $zScore$ with α/2 probability to its right. <br>Similarly let -$z_\frac{\sigma}{2}$ denote a $zScore$ with α/2 probability to its left.
    </li>
    <li> Example: <img src='https://i.imgur.com/mntg6h2.png' width=700>
        The value $z_{0.10}$ is the positive z-score that has α/2 = 0.1 probability to its right. The desired $zScore$ is 1.282. <br>The value $-z_{0.25}$ is the negative z-score that has α/2 = 0.25 probability to its left. The
desired $zScore$ is -0.6745.

</ul>


================================================================================
CELL 18 — CODE
================================================================================

# https://stackoverflow.com/a/20864883/4084039
import scipy.stats as st
print("zScore for 0.1 probability to right is",st.norm.ppf(1-0.10))
print("zScore for 0.25 probability to left is",st.norm.ppf(0.25))


--- OUTPUT ---

[Output 1: stream]

zScore for 0.1 probability to right is 1.2815515655446004
zScore for 0.25 probability to left is -0.6744897501960817




================================================================================
CELL 19 — MARKDOWN
================================================================================

[Empty cell]


================================================================================
CELL 20 — MARKDOWN
================================================================================

[Empty cell]


================================================================================
CELL 21 — MARKDOWN
================================================================================

[Empty cell]


================================================================================
CELL 22 — MARKDOWN
================================================================================

<strong>Note:</strong> the data we have in hand might not included all the purchases that are made, and assume we have given the whole <font color='blue'>population standard deviation as 5051.</font>


================================================================================
CELL 23 — CODE
================================================================================

# we are taking a sample of male persons and calculating their mean
data_male = np.array(df[df['Gender']=='M']['Purchase'].values)
samples = random.sample(range(0, data_male.shape[0]), 100)
print("the mean of money spent by sample set of 100 persons :",data_male[samples].mean())
print("Given that the we have population standard deviation : 5051")

print("From central limit theorem we can say that, the std of sampling distribution of the sample mean is \u03C3/\u221An :", 5051/10)


--- OUTPUT ---

[Output 1: stream]

the mean of money spent by sample set of 100 persons : 10474.31
Given that the we have population standard deviation : 5051
From central limit theorem we can say that, the std of sampling distribution of the sample mean is σ/√n : 505.1




================================================================================
CELL 24 — MARKDOWN
================================================================================

<img src='https://i.imgur.com/vXSIeng.jpg'>

<html>
<body>

__ We know that in normal distribution, given a data point there is $95\%$ probability that it will be within the range [ <font color='red'>$\mu-2\sigma$</font>, <font color='red'>$\mu+2\sigma$</font>] __

<ul>
    <li>The sampling distribution of the sample means is a normal distribution</li>
    <li>Any sample mean we take <font color='red'>$\overline{x}$</font> it is 95% probability that it will be within the range [ <font color='red'>$\mu_{x}-2\sigma_{x}$</font>, <font color='red'>$\mu_{x}+2\sigma_{x}$</font>] $i.e.$ for every 100 sample means typically 95 of them are in this range [ <font color='red'>$\mu_{x}-2\sigma_{x}$</font>, <font color='red'>$\mu_{x}+2\sigma_{x}$</font>]</li>
    <li>It is similar to that for any sample mean we take <font color='red'>$\overline{x}$</font> it is 95% probability that the range [ <font color='red'>$\overline{x}-2\sigma_{x}$</font>, <font color='red'>$\overline{x}+2\sigma_{x}$</font>] will contain distribution mean <font color='red'>$\mu_{x} [\approx \mu]$</font>.
    </li>
</ul>

</body>
</html>


================================================================================
CELL 25 — MARKDOWN
================================================================================

<font color='brown'><b>Question:</b></font> Choose the best interpretation of a 95% confidence interval for the population mean μ? <br>
<font color='blue'><b>Option 1:</b></font> If repeated random samples were taken and the 95% confidence interval was computed for each sample, 95% of the intervals would contain the population mean. <br>
<font color='blue'><b>Option 2:</b></font> The probability that the population mean μ is in the confidence interval is 0.95 <br>
<font color='blue'><b>Option 3:</b></font> 95% of the population distribution is contained in the confidence interval.
<br><br>
<font color='green'><b>Answer:</b></font> The correct answer is <font color='green'><b>Option 1</b></font> please check the above 3 points, <font color='red'><b>Option 2</b></font> is incorrect because it places the probability on $\mu$, instead of on the confidence interval. <font color='red'><b>Option 3</b></font> is incorrect since the confidence interval for the population mean is built using sample means and not values from the population distribution. Using population distribution values would give us a confidence interval that is wider than the one for the population mean.


================================================================================
CELL 26 — MARKDOWN
================================================================================

[Empty cell]


================================================================================
CELL 27 — MARKDOWN
================================================================================

[Empty cell]


================================================================================
CELL 28 — MARKDOWN
================================================================================

<font size='3'>From the above equations Let us construct an intravel [<font color='red'>$\overline{x}$- 2\*505.1, $\overline{x}$+2\*505.1</font>] = [<font color='red'> $\overline{x}$- 2\*$\frac{\sigma}{\sqrt{n}}$, $\overline{x}$+2\*$\frac{\sigma}{\sqrt{n}}$</font>]</font>


================================================================================
CELL 29 — CODE
================================================================================

def plt_confidence_interval(data, sample_mean, population_std, i, j, color):
    sns.distplot(data, color=color, ax=axs[i, j])
    axs[i, j].axvline(data.mean(), linestyle="-", color='k', label="p_mean")
    axs[i, j].axvline(sample_mean, linestyle="--", color='m', label="s_mean")
    axs[i, j].axvline(sample_mean+2*(population_std/np.sqrt(100)), linestyle=":", color='g', label="s_mean+2*SE")
    axs[i, j].axvline(sample_mean-2*(population_std/np.sqrt(100)), linestyle=":", color='g', label="s_mean-2*SE")
    axs[i, j].legend()


================================================================================
CELL 30 — CODE
================================================================================

fig, axs = plt.subplots(3, 2,  figsize=(15, 10))
for i in range(6):
    sample = data_male[random.sample(range(0, data_male.shape[0]), 100)]
    plt_confidence_interval(data_male, np.array(sample).mean(), population_std, plt_grid[i][0],plt_grid[i][1],colrs[i])
plt.show()


--- OUTPUT ---

[Output 1: display_data]

<Figure size 1080x720 with 6 Axes>



================================================================================
CELL 31 — MARKDOWN
================================================================================

In the above figure, the read line show the sample mean <font color='red'>$\overline{x}$</font> and the two green lines shows [<font color='red'> $\overline{x}$- 2\*$\frac{\sigma}{\sqrt{n}}$, $\overline{x}$+2\*$\frac{\sigma}{\sqrt{n}}$</font>]


================================================================================
CELL 32 — MARKDOWN
================================================================================

<p style="font-family:'Georgia';font-size:22px" >Note: We have a big Assumption that, we know the population standard deviation as 5051.</p>


================================================================================
CELL 33 — MARKDOWN
================================================================================

## 2.1 Confidence interval when don't have knowldge about population standard deviation


================================================================================
CELL 34 — MARKDOWN
================================================================================

we know the the cofidenance interval[<font color='red'> $\overline{x}$- 2\*$\frac{\sigma}{\sqrt{n}}$, $\overline{x}$+2\*$\frac{\sigma}{\sqrt{n}}$</font>] when we know the popuplation standard deviation. If you observe here we estimating population mean with sample mean (from above pdf plots, the sample mean is almost close to population mean)


================================================================================
CELL 35 — MARKDOWN
================================================================================

__ <font color='#E91BBC'>Can we do the similar estimation of population stadard deviation using sample stadard deviation?</font> __


================================================================================
CELL 36 — MARKDOWN
================================================================================

<font color='#398114'><strong>Ans: Yes, We can estimate it</strong></font>


================================================================================
CELL 37 — MARKDOWN
================================================================================


SE is used is to make confidence intervals of the unknown population mean. If the sampling distribution is normally distributed, the sample mean, the standard error, and the quantiles of the normal distribution can be used to calculate confidence intervals for the true population mean.

The following expressions can be used to calculate the upper and lower 95% confidence limits


${\text{Upper 95%  limit}{\displaystyle ={\bar {x}}+{\text{SE}}\times 1.96}}$ <br>
${\text{Lower 95%  limit}{\displaystyle ={\bar {x}}-{\text{SE}}\times 1.96}}$

${\displaystyle {\bar {x}}} $ is equal to the sample mean, an estimation to population mean<br>
$SE$ is equal to the standard error for the sample mean, <br>
$1.96$ is the $0.975$ quantile of the normal distribution <br>

<br>
<font color='brown'> But we have taken 0.975 quantile?</font>

<font color='green'> Answer: as we need the confidence level of 95%, the ${\alpha}$ value will be 0.05, so $\frac{\alpha}{2}=0.025$
As we know <br><br>
$${\text{Upper 95%  limit}{\displaystyle ={\bar {x}}+{\text{SE}}\times z_\frac{\alpha}{2}}} = {\bar{x}}+{\text{SE}} \times z_{0.025}  = {\bar{x}}+{\text{SE}} \times 1.96 $$ <br>
$${\text{Lower 95%  limit}{\displaystyle ={\bar {x}}-{\text{SE}}\times z_\frac{\alpha}{2}}} = {\bar{x}}-{\text{SE}} \times z_{0.025}= {\bar{x}}-{\text{SE}} \times 1.96$$


================================================================================
CELL 38 — MARKDOWN
================================================================================

<font size='3'>From the above equations Let us construct an intravel  [<font color='red'> $\overline{x}$- 2\*$\frac{s}{\sqrt{n}}$, $\overline{x}$+2\*$\frac{s}{\sqrt{n}}$</font>]</font>


================================================================================
CELL 39 — CODE
================================================================================

fig, axs = plt.subplots(3, 2,  figsize=(15, 10))
for i in range(6):
    sample = data_male[random.sample(range(0, data_male.shape[0]), 100)]
    plt_confidence_interval(data_male, np.array(sample).mean(), np.array(sample).std(), plt_grid[i][0],plt_grid[i][1],colrs[i])
plt.show()


--- OUTPUT ---

[Output 1: display_data]

<Figure size 1080x720 with 6 Axes>



================================================================================
CELL 40 — MARKDOWN
================================================================================

__Conclusion: Finding Confidenace interval of population mean__
<ul>
    <li>Case 1: Knowing Population Standard Deviation <font color='red'> ${\sigma}$ </font>  
    <ol>
        <li>Get a sample with decent size(<font color='red'> $n$</font>) from population and caculate its mean <font color='red'> $\overline{x}$</font></li>
        <li>Report confidence intravel as[<font color='red'> $\overline{x}$- 2*$\frac{\sigma}{\sqrt{n}}$, $\overline{x}$+2*$\frac{\sigma}{\sqrt{n}}$</font>]</li>
    </ol>
</li>
<li>Case 2: Without Knowing Population Standard Deviation
    <ol>
        <li>Get a sample with decent size(<font color='red'> $n$</font>) from population and caculate its mean <font color='red'> $\overline{x}$</font></li>
        <li>Calculate the sample std <font color='red'>s</font> and find the The standard error of mean or <font color='red' > SE mean </font>as  <font color='red'>$\frac{s}{\sqrt{n}}$</font>.</li>
        <li>report confidence intravel as[<font color='red'> $\overline{x}$- 2*$\frac{s}{\sqrt{n}}$, $\overline{x}$+2*$\frac{s}{\sqrt{n}}$</font>] or [<font color='red'> $\overline{x}$- 2*SE mean, $\overline{x}$+2*SE mean</font>]</li>
    </ol>
</li>
</ul>


================================================================================
CELL 41 — MARKDOWN
================================================================================

### Example Problems on confidence interval


================================================================================
CELL 42 — MARKDOWN
================================================================================

><font color=#EB07BA >Given the population standard deviation as 5051 , and 10 samples each of size 100 and thier respective sample means is given , then what is the 95% C.I for the mean of population?.</font>


================================================================================
CELL 43 — MARKDOWN
================================================================================

___Solution___:
<ul>
    <li>Take 10 random samples each of size 100 from our data and calculate their mean <font color='red'> $\overline{x}$</font></li>
    <li> Now for every sample , calculate the 95% C.I as [<font color='red'> $\overline{x}$- 2*$\frac{5051}{\sqrt{n}}$, $\overline{x}$+2*$\frac{5051}{\sqrt{n}}$</font>]. We get <font color='red'> 10 </font> C.I , one for each sample.</li>
    <li> Ideally, instead of 10 samples if we take 100 samples(we get 100 C.Is), 95 C.I's must catch true Pop mean, i.e. true population mean must be in range for approximately 95 Confidence Intervals. So, for 10 samples, we might see 9 C.I's catching the Pop mean. Let's see practically by comparing it with Pop mean.</li>
    </ul>


================================================================================
CELL 44 — CODE
================================================================================

x = PrettyTable()
x = PrettyTable(["#samples", "Sample Size", "Sample mean", "Pop Std","Left C.I","Right C.I","Pop mean","Catch"])
male_population_std = data_male.std()
male_population_mean= np.round(data_male.mean(), 3)
for i in range(10):
    sample=data_male[random.sample(range(0, data_male.shape[0]), 100)]
    sample_mean = sample.mean()
    sample_size = len(sample)
    left_limit  = np.round(sample_mean - 2*(male_population_std/np.sqrt(sample_size)), 3)
    right_limit = np.round(sample_mean + 2*(male_population_std/np.sqrt(sample_size)), 3)
    row = []
    row.append(i+1)
    row.append(sample_size)
    row.append(sample_mean)
    row.append(population_std)
    row.append(left_limit)
    row.append(right_limit)
    row.append(male_population_mean)
    row.append((male_population_mean <= right_limit) and (male_population_mean >= left_limit))
    x.add_row(row)
print(x)


--- OUTPUT ---

[Output 1: stream]

+----------+-------------+-------------+----------+----------+-----------+----------+-------+
| #samples | Sample Size | Sample mean | Pop Std  | Left C.I | Right C.I | Pop mean | Catch |
+----------+-------------+-------------+----------+----------+-----------+----------+-------+
|    1     |     100     |   9468.25   | 4981.017 | 8458.04  |  10478.46 | 9504.772 |  True |
|    2     |     100     |   9352.07   | 4981.017 | 8341.86  |  10362.28 | 9504.772 |  True |
|    3     |     100     |   9565.07   | 4981.017 | 8554.86  |  10575.28 | 9504.772 |  True |
|    4     |     100     |   9027.31   | 4981.017 |  8017.1  |  10037.52 | 9504.772 |  True |
|    5     |     100     |   9352.42   | 4981.017 | 8342.21  |  10362.63 | 9504.772 |  True |
|    6     |     100     |   9639.05   | 4981.017 | 8628.84  |  10649.26 | 9504.772 |  True |
|    7     |     100     |   9710.18   | 4981.017 | 8699.97  |  10720.39 | 9504.772 |  True |
|    8     |     100     |   8455.66   | 4981.017 | 7445.45  |  9465.87  | 9504.772 | False |
|    9     |     100     |   9253.39   | 4981.017 | 8243.18  |  10263.6  | 9504.772 |  True |
|    10    |     100     |   9244.32   | 4981.017 | 8234.11  |  10254.53 | 9504.772 |  True |
+----------+-------------+-------------+----------+----------+-----------+----------+-------+




================================================================================
CELL 45 — MARKDOWN
================================================================================

Now assuming that <b>we don't know the population std</b>


================================================================================
CELL 46 — MARKDOWN
================================================================================

><font color=#EB07BA >Given 10 sample each with their sample mean and sample std find the 95% confidence interval for each of the sample and compare it with population mean.(Population Std unknown)</font>


================================================================================
CELL 47 — MARKDOWN
================================================================================

___Solution___:
<ul>
    <li>Take 10 random samples each of size 100 from our data and calculate their mean <font color='red'> $\overline{x}$</font> and also thier standard deviation <font color='red'>$s$</font> </li>
    <li> Now for as we don't know the population deviation, we can take the standard error of mean or <font color='red' > SE mean </font>as  <font color='red'>$\frac{s}{\sqrt{n}}$</font> and calculate the 95% C.I as [<font color='red'> $\overline{x}$- 2*$\frac{s}{\sqrt{n}}$, $\overline{x}$+2*$\frac{s}{\sqrt{n}}$</font>]. We get <font color='red'> 10 </font> C.I , one for each sample.</li>
    <li> Ideally , instead of 10 samples if we take 100 samples(we get 100 C.Is), 95 C.I's must catch true Pop mean ,i.e true population mean must be in range for approximately 95 Confidence Intervals. So , for 10 samples , we might see 9 C.I's catching the Pop mean . Let's see practically by comparing it with Pop mean.</li>
    </ul>


================================================================================
CELL 48 — CODE
================================================================================

x = PrettyTable()
x = PrettyTable(["#samples", "Sample Size", "Sample mean", "Pop Std","Left C.I","Right C.I","Pop mean","Catch"])
for i in range(10):
    sample=data_male[random.sample(range(0, data_male.shape[0]), 100)]
    sample_mean = sample.mean()
    sample_std =  sample.std()
    sample_size = len(sample)
    # here we are using sample standard deviation instead of population standard deviation
    left_limit  = np.round(sample_mean - 2*(sample_std/np.sqrt(sample_size)), 3)
    right_limit = np.round(sample_mean + 2*(sample_std/np.sqrt(sample_size)), 3)
    row = []
    row.append(i+1)
    row.append(sample_size)
    row.append(sample_mean)
    row.append(population_std)
    row.append(left_limit)
    row.append(right_limit)
    row.append(male_population_mean)
    row.append((male_population_mean <= right_limit) and (male_population_mean >= left_limit))
    x.add_row(row)
print(x)


--- OUTPUT ---

[Output 1: stream]

+----------+-------------+-------------+----------+----------+-----------+----------+-------+
| #samples | Sample Size | Sample mean | Pop Std  | Left C.I | Right C.I | Pop mean | Catch |
+----------+-------------+-------------+----------+----------+-----------+----------+-------+
|    1     |     100     |   8675.65   | 4981.017 | 7771.743 |  9579.557 | 9504.772 |  True |
|    2     |     100     |   9786.34   | 4981.017 | 8744.072 | 10828.608 | 9504.772 |  True |
|    3     |     100     |   9871.08   | 4981.017 | 8820.17  |  10921.99 | 9504.772 |  True |
|    4     |     100     |   9301.86   | 4981.017 | 8201.032 | 10402.688 | 9504.772 |  True |
|    5     |     100     |   9565.01   | 4981.017 | 8530.041 | 10599.979 | 9504.772 |  True |
|    6     |     100     |    9263.4   | 4981.017 | 8212.071 | 10314.729 | 9504.772 |  True |
|    7     |     100     |   9684.09   | 4981.017 | 8693.858 | 10674.322 | 9504.772 |  True |
|    8     |     100     |   9770.69   | 4981.017 | 8731.224 | 10810.156 | 9504.772 |  True |
|    9     |     100     |   9138.08   | 4981.017 | 8127.903 | 10148.257 | 9504.772 |  True |
|    10    |     100     |   9794.23   | 4981.017 | 8758.503 | 10829.957 | 9504.772 |  True |
+----------+-------------+-------------+----------+----------+-----------+----------+-------+




================================================================================
CELL 49 — MARKDOWN
================================================================================

**When we have small samples pick Z values from T-Distribution.**


================================================================================
CELL 50 — MARKDOWN
================================================================================

**Refer - ift.world screenshots**


Pop Var - large sample size
Pop unknown - large sample size

Pop var - small sample
Pop var unknown - large sample size


================================================================================
CELL 51 — MARKDOWN
================================================================================

**Confidence Interval using empirical bootstrap.**

Which holds for any statistics CI eg. Median,std,any stats


================================================================================
CELL 52 — MARKDOWN
================================================================================

**Refer assignment for bootstrap samples**


================================================================================
CELL 53 — CODE
================================================================================

[Empty cell]


================================================================================
CELL 54 — MARKDOWN
================================================================================

#  From Live session


================================================================================
CELL 55 — MARKDOWN
================================================================================

### Bootstrapping
- Non-parametric Stats + Computational-Simulations
- CLT: Sample means are Gaussian distributed with mean=population-mean.
- Q. How to estimate the population median (or other statistics) given a single sample (S)?
- Ans: Bootstrapping
- Assmumption: Each observed value in the sample (S) is randomly collected and are independent.


================================================================================
CELL 56 — CODE
================================================================================

# Bootstrapping diagram


================================================================================
CELL 57 — CODE
================================================================================

# Synthetically create a sample with random and independent observations

# Let us use a sample of synthetic data (from some disb)
# we generated so that we know the population medain to compare against
# Let sample from Beta disb with alpha = 2,beta=2 which has a population median of 0.5
# Refer: https://en.wikipedia.org/wiki/Beta_distribution Median ~ (alpha-1/3)/(alpha+beta-2/3) if alpaha, beta >1

n=100;
S = np.random.beta(2,2,n) # data can have any distribution.

#Q. Given S, how to estimate the popualtion median?

# function to generate a bootstrap(sampling with repalcement) sample of size n given a sample S. Each sample
def bootstrapSample(S, m):

  n = S.size; # size of S
  indx = np.random.randint(n, size=m) # generates random integer indices from discrete unif random disb
  r = S[indx]
  return r


m = 50; # size of each bootstap sample
k = 1000; # number of botostrap samples

medians = np.zeros(k)

for i in range(k):
  medians[i] = np.median(bootstrapSample(S, m))

print(medians.size)


--- OUTPUT ---

[Output 1: stream]

1000




================================================================================
CELL 58 — CODE
================================================================================

# Now estimate median
print(np.mean(medians))


--- OUTPUT ---

[Output 1: stream]

0.4914740968731999




================================================================================
CELL 59 — CODE
================================================================================

print(np.median(medians))


--- OUTPUT ---

[Output 1: stream]

0.4885759760968837




================================================================================
CELL 60 — CODE
================================================================================

sns.set()
ax = sns.distplot(medians)


--- OUTPUT ---

[Output 1: display_data]

<Figure size 432x288 with 1 Axes>



================================================================================
CELL 61 — CODE
================================================================================

# 95% C.I on the medain estimate with n=100, m=50, k=1000

#https://docs.scipy.org/doc/numpy/reference/generated/numpy.percentile.html
lb_M = np.percentile(medians,2.5)
ub_M = np.percentile(medians,97.5)
mid_M = np.percentile(medians,50)

print(lb_M, mid_M, ub_M)


--- OUTPUT ---

[Output 1: stream]

0.4086213750845128 0.4885759760968837 0.576183443992925




================================================================================
CELL 62 — CODE
================================================================================

# same experiment as above with same S, n=100, m=100, k=1000

n=100
m=100 # size of each bootstap sample
k=1000  # number of botostrap samples

medians = np.zeros(k)

for i in range(k):
  medians[i] = np.median(bootstrapSample(S, m))

print(medians.size)

lb_M = np.percentile(medians,2.5)
ub_M = np.percentile(medians,97.5)
mid_M = np.percentile(medians,50)

print(lb_M, mid_M, ub_M)


--- OUTPUT ---

[Output 1: stream]

1000
0.4279954763663735 0.4898898120873415 0.5630365917463543




================================================================================
CELL 63 — CODE
================================================================================

# same experiment as above with same S, n=100, m=200, k=1000

n=100
m=200 # size of each bootstap sample
k=1000  # number of botostrap samples

medians = np.zeros(k)

for i in range(k):
  medians[i] = np.median(bootstrapSample(S, m))

print(medians.size)

lb_M = np.percentile(medians,2.5)
ub_M = np.percentile(medians,97.5)
mid_M = np.percentile(medians,50)

print(lb_M, mid_M, ub_M)


--- OUTPUT ---

[Output 1: stream]

1000
0.4645238138051946 0.4905515969092869 0.5384725608181098




================================================================================
CELL 64 — MARKDOWN
================================================================================

Exercise: Estimate 10th percentile value of the population given a sample of 100 points from any distribution.
