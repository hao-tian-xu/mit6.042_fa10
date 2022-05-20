# **<u>*U3. Counting*</u>**

# L12. Sums

## The Value of an Annuity

**Definition.** An *annuity* is a financial instrument that pays out a fixed amount of money at the beginning of every year for some specified number of years. In particular, an $n$-year, $m$-payment annuity pays $m$ dollars at the start of each year for $n$ years. $n$ can be finite or infinite.

Let’s assume that money can be invested at a *fixed annual interest rate* $p$

### Perturbation Method

$$
\begin{aligned}
S=1+&x+x^{2}+\cdots+x^{n-1} \\
xS= &x+x^{2}+\cdots+x^{n-1}+x^{n}
\end{aligned}
$$

$$
S-x S=1-x^{n}
$$

#### A Closed Form for the Annuity Value

$$
\begin{aligned}
V &=m\left(\frac{1-x^{n}}{1-x}\right) \\
&=m\left(\frac{1+p-(1 /(1+p))^{n-1}}{p}\right)
\end{aligned}
$$

#### Infinite Geometric Series

**Theorem 9.1.1.** If $|x|<1$, then
$$
\sum_{i=0}^{\infty} x^{i}=\frac{1}{1-x} .
$$

**e.g. to receive m dollars a year forever**
$$
\begin{aligned}
V &=m \cdot \sum_{j=0}^{\infty} x^{j} \\
&=m \cdot \frac{1}{1-x} \\
&=m \cdot \frac{1+p}{p}
\end{aligned}
$$

### Derivative Method

$$
\sum_{i=1}^{n-1} i x^{i}=x+2 x^{2}+3 x^{3}+\cdots+(n-1) x^{n-1}
$$

$$
\frac{d}{d x}\left(\sum_{i=0}^{n-1} x^{i}\right)=\frac{d}{d x}\left(\frac{1-x^{n}}{1-x}\right)
$$

$$
\cdots
$$

$$
\sum_{i=1}^{n-1} i x^{i}=\frac{x-n x^{n}+(n-1) x^{n+1}}{(1-x)^{2}}
$$

**Theorem 9.1.2.** If $|x|<1$, then
$$
\sum_{i=1}^{\infty} i x^{i}=\frac{x}{(1-x)^{2}} .
$$
**e.g. an annuity that pays $im$ dollars at the end of each year $i$ forever**
$$
\begin{aligned}
V &=\sum_{i=1}^{\infty} \frac{i m}{(1+p)^{i}} \\
&=m \cdot \frac{1 /(1+p)}{\left(1-\frac{1}{1+p}\right)^{2}} \\
&=m \cdot \frac{1+p}{p^{2}}
\end{aligned}
$$

## Power Sums

$$
\sum_{i=1}^{n} i^{2}=\frac{(2 n+1)(n+1) n}{6}
$$

**Guess:** $\sum_{i=1}^{n} i^{2}=a n^{3}+b n^{2}+c n+d$

$\begin{matrix}{}
n=0 & \text { implies } & 0=d \\
n=1 & \text { implies } & 1=a+b+c+d \\
n=2 & \text { implies } & 5=8 a+4 b+2 c+d \\
n=3 & \text { implies } & 14=27 a+9 b+3 c+d .
\end{matrix}$

$\implies a=1 / 3, b=1 / 2, c=1 / 6, d=0$

**Be careful!** This method lets you discover formulas, but it doesn’t guarantee they are right!

## Approximating Sums

**Theorem 9.3.1.** Let $f: \mathbb{R}^{+} \rightarrow \mathbb{R}^{+}$ be a nondecreasing continuous function and let
$$
S=\sum_{i=1}^{n} f(i)
$$
and
$$
I=\int_{1}^{n} f(x) d x
$$
Then
$$
I+f(1) \leq S \leq I+f(n)
$$
Similarly, if $f$ is nonincreasing, then
$$
I+f(n) \leq S \leq I+f(1)
$$
**e.g. **$S=\sum_{i=1}^{n} \sqrt{i}$
$$
\begin{aligned}
I &=\int_{1}^{n} \sqrt{x} d x \\
&=\left.\frac{x^{3 / 2}}{3 / 2}\right|_{1} ^{n} \\
&=\frac{2}{3}\left(n^{3 / 2}-1\right)
\end{aligned}
$$

$$
\frac{2}{3} n^{3 / 2}+\frac{1}{3} \leq S \leq \frac{2}{3} n^{3 / 2}+\sqrt{n}-\frac{2}{3}
$$

$$
S=\frac{2}{3} n^{3 / 2}+\delta(n) \quad \text { where } \frac{1}{3} \leqslant \delta(n) \leqslant \sqrt{n}-\frac{2}{3}
$$

**Definition.** $g(x) \sim h(x)$ means $\lim _{x \rightarrow \infty} \frac{g(x)}{h(x)}=1$
$$
S\sim \frac{2}{3} n^{3 / 2}
$$

## *Thinking*

1. 这一讲用年金总价值问题作为例子开始讨论计数。对于经济学来说，数学模型未必能包含所有现实世界的复杂度，但对于可以处理的变量来说却是极为有用的工具。
2. 对于不同的年金问题，介绍了微扰法和导数法；对于自然数等幂和，介绍了假设多项式，利用小整数实例求系数，从而得到猜测解的方法；对于可积分函数求和，介绍了通过积分函数界定上下边界的方法。



# L13. Sums and Asymptotic

## Hanging Out Over the Edge

### Greedy Strategy

Given: $n$ blocks of length $1$
Def: $r_{i}=$ amount by which its block extends beyond the table
Stability Constraint: The center of mass $C_{k}$ of the top $k$ blocks must lie on the $(k+1) t h$
block. (table $=$ block $_{n+1}$)
For Greedy Stacking, $C_{k}=r_{k+1}$
The center of math of $k$ th block is at $r_{k}-1 / 2$
The center of math of the top $k$ blocks is

$\begin{aligned}
C_{k} &=\frac{(k-1) C_{k-1}+1\left(r_{k}-1 / 2\right)}{k-1+1} \\
&=\frac{(k-1) C_{k-1}+r_{k}-1 / 2}{k}
\end{aligned}$

$\begin{aligned}
\Rightarrow r_{k+1} &=\frac{(k-1) r_{k}+r_{k}-1 / 2}{k} \\
&=\frac{kr_k-1 / 2}{k} \\
&=r_{k}-1 / 2k
\end{aligned}$

$\Rightarrow r_{k}-r_{k+1}=\frac{1}{2 k}$

$\Rightarrow r_{1}=\frac{1}{2} \sum_{i=1}^{n} \frac{1}{i} \text{ (Harmonic Sum)}$

### Harmonic Numbers

**Definition 9.4.1.** The $n$ th Harmonic number is
$$
H_{n}::=\sum_{i=1}^{n} \frac{1}{i}
$$
**Integration Bounds**

$\int_{1}^{n} \frac{1}{x} d x=\left.\ln (x)\right|_{1} ^{n}=\ln (n)$

$\ln (n)+\frac{1}{n} \leq H_{n} \leq \ln (n)+1$

**Better approximation** (without proof)

Because the Harmonic numbers *frequently arise in practice*, mathematicians have worked hard to get even better approximations for them:

$H_{n}=\ln (n)+\gamma+\frac{1}{2 n}+\frac{1}{12 n^{2}}+\frac{\epsilon(n)}{120 n^{4}}$

Here $\gamma$ is a value $0.577215664 \ldots$ called Euler's constant, and $\epsilon(n)$ is between 0 and 1 for all $n$.

## Products

$$
n !=\prod_{i=1}^{n} i
$$

### convert product into sum by logarithm

$$
\begin{aligned}
\ln (n !) &=\ln (1 \cdot 2 \cdot 3 \cdots(n-1) \cdot n) \\
&=\ln (1)+\ln (2)+\ln (3)+\cdots+\ln (n-1)+\ln (n) \\
&=\sum_{i=1}^{n} \ln (i)
\end{aligned}
$$

$$
\begin{aligned}
\int_{1}^{n} \ln (x) d x &=(x \ln (x)-x)\big|_{1} ^{n} \\
&=n \ln (n)-n+1 .
\end{aligned}
$$

$$
n \ln (n)-n+1 \leq \sum_{i=1}^{n} \ln (i) \leq n \ln (n)-n+1+\ln (n)
$$

$$
\frac{n^{n}}{e^{n-1}} \leq n ! \leq \frac{n^{n+1}}{e^{n-1}}
$$

### Stirling’s Formula

**Theorem 9.6.1 (Stirling's Formula).** For all $n \geq 1$,
$$
n !=\sqrt{2 \pi n}\left(\frac{n}{e}\right)^{n} e^{\epsilon(n)}
$$
where
$$
\frac{1}{12 n+1} \leq \epsilon(n) \leq \frac{1}{12 n}
$$
$n ! \sim \sqrt{2 \pi n}\left(\frac{n}{e}\right)^{n}$

## Asymptotic Notation

**Tilde**
$f(x) \sim g(x) \iff \lim _{x \rightarrow \infty} \frac{f(x)}{g(x)}=1$
**Little Oh**
$f(x)=o(g(x)) \iff \lim _{x \rightarrow \infty}\left|\frac{f(x)}{g(x)}\right|=0 \quad(f<g)$
**Big Oh**
$f=O(g)\iff \lim _{x \rightarrow \infty}\left|\frac{f(x)}{g(x)}\right|<\infty \quad(f \leq g)$
**Omega**
$f=\Omega(g)\iff \lim _{x \rightarrow \infty}\left|\frac{f(x)}{g(x)}\right|>0 \quad(f \geq g)$
**Little Omega**
$f(x)=\omega(g(x)) \iff \lim _{x \rightarrow \infty}\left|\frac{f(x)}{g(x)}\right| \rightarrow \infty \quad(f>g)$
**Theta**
$f=\Theta(g)\iff  f=O(g)$ and $f=\Omega(g) \quad(f=g)$

### Pitfalls with Asymptotic Notation

$\sum_{i=1}^{n} i=O(n)$ Proof by Induction

Never ever use asymptotic notation for induction, they are only for functions

## *Thinking*

1. 这一讲通过骨牌堆叠问题引出调和级数，但并没有再做更多的引申。之后讨论了通过自然对数将连乘问题转化为级数问题。最后讨论了渐进符号，作为分析算法复杂性的工具。
2. 如果说我对于抽象的数学问题不感兴趣，对于具体的工程问题也不感兴趣的话，那么我的兴趣点或许就在于物理学了，介于数学和工程之间，或者说是数学和工程的桥梁。
   1. 其实很多事情你要坚持做下去，只有坚持做下去，过程中的优与劣才会渐渐浮现，至少10000小时，每天10小时的话也要1000天，事实上每天8小时，每周5天的话要4.8年。
   2. 这个阶段在补足大量的基础知识，当拥有一定的基础知识后，或许可以融会贯通，静下心来再等待一下。



# L14. Divide and Conquer Recurrences

## The Towers of Hanoi

$T_{1}=1$

$T_{n}=2 T_{n-1}+1 \quad$(for $n \geq 2$)

Guess and Verify: $T_{n}=2^{n}-1 \quad$ (Proof by Induction)

### Plug and Chug

#### Step I: Plug and Chug Until a Pattern Appears

$$
\begin{aligned}
T_{n} &=2 T_{n-1}+1 \\
&=2\left(2 T_{n-2}+1\right)+1 \\
&=4 T_{n-2}+2+1 \\
&=4\left(2 T_{n-3}+1\right)+2+1 \\
&=8 T_{n-3}+4+2+1 \\
&=8\left(2 T_{n-4}+1\right)+4+2+1 \\
&=16 T_{n-4}+8+4+2+1
\end{aligned}
$$

$$
\begin{aligned}
T_{n} &=2^{k} T_{n-k}+2^{k-1}+2^{k-2}+\ldots+2^{2}+2^{1}+2^{0} \\
&=2^{k} T_{n-k}+2^{k}-1
\end{aligned}
$$

#### Step II: Verify the Pattern

$$
\begin{aligned}
T_{n} &=2^{k} T_{n-k}+2^{k}-1 \\
&=2^{k}\left(2 T_{n-(k+1)}+1\right)+2^{k}-1 \\
&=2^{k+1} T_{n-(k+1)}+2^{k+1}-1
\end{aligned}
$$

#### Step III: Write $T_{n}$ Using Early Terms with Known Values

$$
\begin{aligned}
T_{n} &=2^{n-1} T_{1}+2^{n-1}-1 \\
&=2^{n-1} \cdot 1+2^{n-1}-1 \\
&=2^{n}-1
\end{aligned}
$$

## Merge Sort

To sort $n>1, x_{1}, x_{2}, \ldots, x_{n}$ ($n=$ power of 2)

1. sort $x_{1}, x_{2}, \ldots, x_{n / 2} \& x_{n / 2+1}, \ldots, x_{n}$ recursively
2. merge

$T_{1}=0$

$T_{n}=2 T_{n / 2}+n-1$

Plug and Chug: $T_{n}=n \log n-n+1$

In practice: $T(n)=T(\lceil n / 2\rceil)+T(\lfloor n / 2\rfloor)+n-1 \quad$ (for $n \geq 2$)

## The Akra-Barzzi Theorem

### Divide and conquer recurrence

$$
T(x)=\begin{cases}{}
\text { is nonnegative and bounded } & \text { for } 0 \leq x \leq x_{0} \\
\sum_{i=1}^{k} a_{i} T\left(b_{i} x+h_{i}(x)\right)+g(x) & \text { for } x>x_{0}
\end{cases}
$$

where

1. $a_{1}, \ldots, a_{k}$ are positive constants.
2. $b_{1}, \ldots, b_{k}$ are constants between 0 and 1 .
3. $x_{0}$ is large enough so that $T$ is well-defined.
4. $g(x)$ is a nonnegative function such that $g^{\prime}(x) \mid$ is bounded by a polynomial.
5. $\left|h_{i}(x)\right|=O\left(x / \log ^{2} x\right)$

Then,
$$
T(x)=\Theta\left(x^{p}\left(1+\int_{1}^{x} \frac{g(u)}{u^{p+1}} d u\right)\right) \quad \text { where } \sum_{i=1}^{k} a_{i} b_{i}^{p}=1
$$

## *Thinking*

这一讲从著名的汉诺塔问题引出递归问题，讨论了两种方法，猜测证明以及插入展开。继而讨论了归并排序。并利用上一讲的渐进符号定义了归并排序这类分治递归的复杂度。



# L15. Linear Recurrences

**Definition.** A recurrence is linear if it is of the form
$$
\begin{aligned}
f(n)&=a_{1} f(n-1)+a_{2} f(n-2)+\ldots+a_{d} f(n-d)+g(n) \\
&=\sum_{i=1}^{d} a_{i} f(n-i)+g(n) \quad \text { for fixed } a_{i}, d
\end{aligned}
$$
$d=$ order of the recurrence

## Homogeneous Linear Recurrence

### Fibonacci recurrence

$\begin{cases}
f(0)=1 \\
f(1)=1 \\
f(n)=f(n-1)+f(n-2) \quad \text { for } n \geq 2 .
\end{cases}$

**Guess:** $f(n)=x^{n}$ for $f(n)=f(n-1)+f(n-2)$

$\implies x^{n}=x^{n-1}+x^{n-2}$

$\implies x=\frac{1 \pm \sqrt{5}}{2}$

**Theorem 10.3.1.** If $f(n)$ and $g(n)$ are both solutions to a homogeneous linear recurrence, then $h(n)=s f(n)+\operatorname{tg}(n)$ is also a solution for all $s, t \in \mathbb{R}$.

**Boundary Condition:** $f(0)=1, f(1)=1$
$$
s=\frac{1}{\sqrt{5}} \cdot \frac{1+\sqrt{5}}{2} \quad t=-\frac{1}{\sqrt{5}} \cdot \frac{1-\sqrt{5}}{2}
$$

### Solving Homogeneous Linear Recurrence

p.298

### Solving Inhomogeneous Linear Recurrence

p.299

## *Thinking*

这一讲讨论了第二种常见的递归问题：线性递归。汉诺塔和斐波那契数列都属于这类问题。

# L16. Counting Rules I

## *Thinking*

Dr. Marten van Dijk的讲座

# L17. Counting Rules II

## *Thinking*

Dr. Marten van Dijk的讲座









