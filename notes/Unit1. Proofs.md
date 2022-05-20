# **<u>*U1. Proofs*</u>**

# L1. Introduction and proofs

## Mathematical Proof

**Definition.** A *mathematical proof* of a *proposition* is a chain of *logical deductions* leading to the proposition from a base set of *axioms*.

## Propositions

**Definition.** A *proposition* is a statement that is either true or false

e.g. $\forall n \in \mathbb{N}, \underbrace{n^{2}+n+41\text{ is a prime number }}_{\text{predicate}}$ 

**Predicate.** A proposition whose truth depends on the value of one or more variables 

**Theorem.** Important propositions

**Lemma.** A preliminary proposition useful for proving later propositions

**Corollary.** A proposition that follows in just a few logical steps from a lemma or a theorem

### Axioms

**Definition.** A proposition that is “assumed” to be true

**Pursuit of a set of axioms is**

1. Consistent: if no propositions can be proved both $T$ and $F$
2. Complete: if it can be used to prove every proposition to be $T$ or $F$

**Kurt Gödel:** It's not possible that there exists any set of *axioms* that are both *consistent* and *complete*

## Compound Propositions

### Implication

$p \implies q$ is True, if $p$ is $\mathrm{F}$ or $q$ is $\mathrm{T}$

e.g. pigs can fly $\Longrightarrow$ l'm King

### If and Only If (IFF $\iff$)

### Notation

$
\begin{array}{ll}
\text { English } & \text { Symbolic Notation } \\
\operatorname{NOT}(P) & \neg P \quad \text { (alternatively, } \bar{P}) \\
P \text { AND } Q & P \wedge Q \\
P \text { OR } Q & P \vee Q \\
P \text { IMPLIES } & P \longrightarrow Q \\
\text { if } P \text { then } Q & P \longrightarrow Q \\
P \text { IFF } Q & P \longleftrightarrow Q
\end{array}
$

## *Thinking*

数理逻辑建立了一套严密的从公理开始的证明系统，遵循这种证明方式的论点确切为真（在假设公理的前提下）。





# L2. Induction

## Proof by Case

## Proof by Contradiction

To prove $P$ is $True$, we assume $P$ is $False$, then use that hypothesis to derive a falsehood or contradiction
$$
\text { If } \neg P \Rightarrow F \text { is true, } P \text { is true }
$$
e.g. $\sqrt{2}$ is irrational

### Well Ordering Principle ( WOP )

Every nonempty set of nonnegative integers has a least element.

#### e.g. $1+r+r^{2}+r^{3}+\cdots+r^{n}=\frac{r^{n+1}-1}{r-1}$

Let $m$ be smallest $n$ with $\neq$. But $=$ for $n=0$, so $m>0$, and
$1+r+r^{2}+r^{3}+\cdots+r^{m-1}=\frac{r^{(m-1)+1}-1}{r-1}$
add $r^m$ to both sides, so $=$ at $m$, contradicting $\neq$ :
there is no counterexample.

## Proof by Induction

### The Principle of Induction

Let $P(n)$ be a predicate. If

- $P(0)$ is true (Base Case), and

- $P(n)$ IMPLIES $P(n+1)$ for all nonnegative integers, $n$, (Inductive Step)

  then

- $P(m)$ is true for all nonnegative integers, $m$.

### Induction axiom

$$
\frac{P(0), \quad \forall n \in \mathbb{N} . P(n) \text { IMPLIES } P(n+1)}{\forall m \in \mathbb{N} . P(m)}
$$

### Stronger Induction

If you can’t prove something, try to prove something grander! 

e.g. Bill in the center $\rightarrow$ Bill anywhere!

## *Thinking*

这个讲座讨论了几个主要的证明方法，这些证明方法本身是数理逻辑的公理，即

1. 如果所有实例都为真，命题为真
2. 假设命题为假，如果存在反例，则命题为真
3. 归纳法：如果命题在0时为真，且假设命题在自然数n时为真可以推导出命题在n+1时为真，则命题在所有自然数集上为真



# L3. Strong Induction

### Good Proofs are

-Correct		-Brief			-In Order

-Complete		-Elegant ( Clever )

-Clear			-Well Organized

**<u>*one third of all published proofs have bugs, have flaws, that render the proof incorrect*</u>**

The trouble often arises because we get lazy.

We don't write down all the details or all the steps.

## Invariants

**Definition.** a property that holds at the beginning, is preserved by every step, but is not present in the target state.

### e.g. The 8-Puzzle ( p.60 )

**The Invariant:** In every sate reachable from the start state, the parity of the number of inversions is the same as in the start state

++ 分析每一步操作的逻辑和结果（对于可能的参数的改变 - 穷举？）

## Strong Induction Axiom

$$
\frac{P(0), \quad \forall n \in \mathbb{N} .(P(0) \text { AND } P(1) \text { AND } \ldots \text { AND } P(m)) \text { IMPLIES } P(n+1)}{\forall m \in \mathbb{N} . P(m)}
$$

any proof using strong induction can be reformatted into a proof using ordinary induction—you just need to use a “stronger” induction hypothesis. 

e.g. The Stacking Game

## *Thinking*

更多的证明方法，不变量和强归纳法



# L4. Number theory I

the study of the *integers*

used in *cryptography*

### Divisibility

$a$ divides $b \quad$ iff $\quad a k=b$ for some $k$.

## The Greatest Common Divisor (GCD)

**Definition.** The largest number that is a divisor of both $a$ and $b$ 

### Relatively Prime Numbers

**Definition.** $a$ and $b$ are relatively prime iff $\operatorname{gcd}(a, b)=1$

e.g. Water Jug Problems

### Linear Combinations and the GCD

**Theorem 4.2.1.** The greatest common divisor of $a$ and $b$ is equal to the smallest positive linear combination of $a$ and $b$.
$$
\operatorname{gcd}(a, b)=s a+t b
$$
**Lemma 4.2.4.** The following statements about the greatest common divisor hold:

1. Every common divisor of a and b divides $\operatorname{gcd}(a, b)$.
2. $\operatorname{gcd}(k a, k b)=k \cdot \operatorname{gcd}(a, b)$ for all $k>0$.
3. If $\operatorname{gcd}(a, b)=1$ and $\operatorname{gcd}(a, c)=1$, then $\operatorname{gcd}(a, b c)=1$
4. If $a \mid b c$ and $\operatorname{gcd}(a, b)=1$, then $a \mid c$.
5. $\operatorname{gcd}(a, b)=\operatorname{gcd}(b, \operatorname{rem}(a, b))$.

### Euclid’s Algorithm as a State Machine

States $::=\mathbb{N} \times \mathbb{N}$
$$
\text { start }::=(a, b)
$$
state transitions defined by
$$
(x, y) \rightarrow(y, \operatorname{rem}(x, y)) \text { for } y \neq 0
$$
at termination $y=0$ (if any)
$$
x=\operatorname{gcd}(a, b)
$$
$\begin{aligned} \text{e.g. }\operatorname{gcd}(1147,899) &=\operatorname{gcd}(899, \underbrace{\operatorname{rem}(1147,899)}_{=248}) \\ &=\operatorname{gcd}(248, \underbrace{\operatorname{rem}(899,248)}_{=155}) \\ &=\operatorname{gcd}(155, \underbrace{\operatorname{rem}(248,155)}_{=93}) \\ &=\operatorname{gcd}(93, \underbrace{\operatorname{rem}(155,93)}_{=62}) \\ &=\operatorname{gcd}(62, \underbrace{\operatorname{rem}(93,62)}_{=31}) \\ &=\operatorname{gcd}(31, \underbrace{\operatorname{rem}(62,31)}_{=0}) \\ &=\operatorname{gcd}(31,0) \\ &=31 \end{aligned}$

### The Pulverizer

$\operatorname{gcd}(a, b)=s a+t b$

find $s$, $t$ (p.93)

## *Thinking*

这一讲开始讨论数论，最大公约数、互素，现在看来只是一些抽象的、简单的概念，下一讲开始便会开始讨论密码学是如何建立在这些抽象的、简单的概念之上的。对于抽象的、简单的概念的明确定义，以及通过数理逻辑证明而得出的确切的命题，是构建于其上的大厦的基础。



# L5. Number theory II

## Turing’s code V1

1. translate a text message into an integer 

$$
\begin{matrix}{} 
& \text { "v } & \text { i } & \text { c } & \text { t } & \text { o } & \text { r } & \text { y" } \\
\rightarrow & 22 & 09 & 03 & 20 & 15 & 18 & 25
\end{matrix}
$$

2. pad the result with a few more digits to make a prime (13 in this case)

$$
m:2209032015182513 
$$

3. **Secrete key:** a large prime $k$
4. **Encryption:** $m^{*}=m \cdot k$
5. **Decryption:** $\frac{m^{*}}{k}=\frac{m \cdot k}{k}=m$

### Breaking Turing’s code v1

Knowing that $m_{1}^{*}=m_{1} \cdot k \quad \text { and } \quad m_{2}^{*}=m_{2} \cdot k$

$k=\mathrm{gcd}(m_{1}^{*},m_{2}^{*})$

## Modular Arithmetic

### Congruency

$x$ is congruent to $y$ modulo $n: x \equiv y\quad(\bmod n)$, iff $n \mid(x-y)$

e.g. $31 \equiv 16\quad(\bmod 5)$

### Multiplicative Inverse

The multiplicative inverse of $x \bmod n$ is a number $x^{-1}$, in $\{0,1, \ldots, n-1\}$ such that
$$
x \cdot x^{-1} \equiv 1(\bmod n)
$$

## Turing’s code v2

1. **Public key:** a large prime $p$

2. **Secrete key:** $k \in \{1, 2, ..., p-1\}$

3. **Encryption**

$$
m \in \{0,1, 2, ..., p-1\}
$$

$$
m^{*}=\operatorname{rem}(m k, p)
$$

4. **Decryption**

$$
\begin{array}{l}
\operatorname{gcd}(p, k)=1 \\
\Longrightarrow \exists s, p. s p+t k=1 \Longrightarrow s p=1-t k \\
\Longrightarrow p \mid(1-t k) \Longrightarrow t k \equiv 1(\bmod p) \\
\Longrightarrow t \text { is a } k^{-1}
\end{array}
$$


$$
\begin{aligned}
m^{*} \cdot k^{-1} &=\operatorname{rem}(m k, p) \cdot k^{-1} \\
& \equiv(m k) k^{-1} \quad(\bmod p) \\
& \equiv m \quad(\bmod p)
\end{aligned}
$$

$$
\implies m=\operatorname{rem}\left(m^{*} k^{-1}, p\right)
$$

### A known-plaintext attack

- known: a pair of $m, m^{*}$

$m^{*} \equiv m k \quad(\bmod p)$
$\operatorname{gcd}(m, p)=1$
compute $m^{-1}$ s.t. $m \cdot m^{-1} \equiv 1(\bmod p)$
$m^{*} \cdot m^{-1} \equiv m k \cdot m^{-1}(\bmod p) \equiv k(\bmod p)$

## Euler’s Theorem

**Theorem 4.6 .4​ (Fermat's Little Theorem).** Suppose $p$ is a prime and $k$ is not a multiple of $p$. Then:
$$
k^{p-1} \equiv 1 \quad(\bmod p)
$$

**Definition (Euler’s Totient Function).** $\phi(n)$ : The number of integers in $\{1,2,3, \ldots, \mathrm{n}-1\}$ that are relative prime to $n$

**Theorem 4.7.6 (Euler's Theorem).** Suppose $n$ is a positive integer and $k$ is relatively prime to $n .$ Then
$$
k^{\phi(n)} \equiv 1 \quad(\bmod n)
$$
## The RSA Algorithm

**Beforehand** The receiver creates a public key and a secret key as follows.

1. Generate two distinct primes, $p$ and $q$. Since they can be used to generate the secret key, they must be kept hidden.

2. Let $n=p q$.

3. Select an integer $e$ such that $\operatorname{gcd}(e,(p-1)(q-1))=1$. The public key is the pair $(e, n)$. This should be distributed widely.

4. Compute $d$ such that $d e \equiv 1(\bmod (p-1)(q-1))$. This can be done using the Pulverizer. The secret key is the pair $(d, n) .$ This should be kept hidden!

**Encoding** Given a message $m$, the sender first checks that $\operatorname{gcd}(m, n)=1 .^{a}$ The sender then encrypts message $m$ to produce $m^{\prime}$ using the public key:
$$
m^{\prime}=\operatorname{rem}\left(m^{e}, n\right) .
$$
**Decoding** The receiver decrypts message $m^{\prime}$ back to message $m$ using the secret key:
$$
m=\operatorname{rem}\left(\left(m^{\prime}\right)^{d}, n\right)
$$

## *Thinking*

1. 欧拉生活在十八世纪，其对于数论这一纯粹数学领域的研究成果，在200多年后的1973年被应用在了RSA加密算法上，而后者在当代得到了广泛的应用。

2. 这一讲定义了同余（按模计算相等），欧拉函数（互素数的数量）。在此基础上推导出费马小定理以至于欧拉定理，以此作为RSA加密算法的数学基础。另外也基于最大公约数和同余讨论了图灵加密算法。





