---
author:
- Aqua Moye
- Notes taken by Robert Moye
- |
  Based on lectures by Dr Kayvan Sadeghi\
  Notes taken by Robert Moye
- |
  Based on lectures by Dr Kayvan Sadeghi\
  and lecture notes by\
  Notes taken by Robert Moye
date:
- Term 2 of 2021 -- 2022
- 
title: MATH0057 -- Probability and Statistics
---

These notes are not endorsed by the lecturer. I have taken significant
liberty in modifying them at my own discretion. As such, they should not
be used as a replacement for the course material. Whilst I have made
every effort to ensure these notes are as accurate and useful as
possible, I cannot guarantee that they are free from error. If you find
any mistakes or anything you think should be changed about these notes,
do not hesitate to email me at <zcahrmo@ucl.ac.uk>.

All my notes can currently be found at
[robmoye.neocities.org](https://robmoye.neocities.org). These notes were
last updated on

.

# Probability

## Basic probability theory

### Definitions

::: defi
**Definition 1** (Sample space). Probability statements, made in the
context of an experiment, may result in a number of possible outcomes,
each of which may be denoted $\omega$. The set of all possible outcomes
is a sample space, denoted $\Omega$.
:::

::: defi
**Definition 2** (Event). A collection of outcomes is an event. An event
$E$ occurs if the outcome of the experiment of $E$. $E\subseteq \Omega$.
:::

### Sets

::: notation
**Notation 1**. For events $E,F$, recall that

-   $E^c$ is the complement of $E$, the set of outcomes that are not in
    $E$.

-   $E\cup F$ is the union of $E$ and $F$, the set of outcomes in $E$ or
    in $F$ (or both).

-   $E\cap F$ is the intersection of $E$ and $F$, the set of outcomes in
    both $E$ and $F$.

-   $E\subseteq F$ denotes that $E$ is a subset of $F$, so every element
    of $E$ is in $F$.

-   $E\subset F$ denotes that $E$ is a subset of $F$, but $E$ and $F$
    are not identical.

-   $E\backslash F=E\cap F^c$ is the set of elements of $E$ that are not
    in $F$.

-   $\emptyset=\{\}=\Omega^c$ is the empty set, that which contains no
    elements.

-   If $E\cap F=\emptyset$ then no outcomes are common to both $E$ and
    $F$. These events are called disjoint, or mutually exclusive (m.e.)

-   If all possible pairs of events $E_1,\dots E_n$ are disjoint, they
    are called mutually disjoint or pairwise disjoint.
:::

::: law
**Law 1** (De Morgan's). For events $E,F$, $$\begin{aligned}
        (E\cap F)^c&=E^c\cup F^c\\
        (E\cup F)^c&=E^c\cap F^c
    \end{aligned}$$
:::

::: law
**Law 2** (Distribution). For events $E,F,G$, $$\begin{aligned}
        \label{eq:dis1}E\cap(F\cup G)&=(E\cap F)\cup (E\cap G)\\
        \label{eq:dis2}E\cup(F\cap G)&=(E\cup F)\cap (E\cup G)
    \end{aligned}$$
:::

### Axioms

::: defi
**Definition 3** ($\sigma$-algebra event space). For sample space
$\Omega$ and events $E_i\in \Omega$ in an event space $\mathcal{F}$,
$\mathcal{F}$ is a $\sigma$-algebra if $$\begin{gathered}
        \Omega\in\mathcal{F}\\
        \label{eq:axiom2}E\in\mathcal{F}\implies E^c\in \mathcal{F}\\
        \label{eq:axiom3}\displaystyle E_1\in\mathcal{F},\dots,E_n\in \mathcal{F}\implies \bigcup_{i=1}^n E_i\in \mathcal{F}
    \end{gathered}$$
:::

::: eg
**Example 1**. Consider an experiment with fair coin tossed once, which
lands on heads or tails, $H$ or $T$. The sample space is
$\Omega=\{H,T\}$ whilst the event space is
$\mathcal{F}=\big\{\emptyset,\{H\},\{T\},\Omega\big\}$.
:::

::: {#th:Kolmo .axiom}
**Axiom 3** (Kolmogrov's). A probability function $P$ is a mapping
$P:\mathcal{F}\to\mathbb{R}$ such that $\forall E,F\in \mathcal{F}$,
$$\begin{gathered}
        P(E)\ge 0\label{eq:Kolmo1}\\
        P(\Omega)=1\label{eq:Kolmo2}\\
        E\cap F=\emptyset\implies P(E\cup F)=P(E)+P(F)\label{eq:Kolmo3}
    \end{gathered}$$
:::

::: remark
**Remark 1**. For countably infinite sequences $E_1,E_2,\dots$ of
mutually disjoint sets in $\mathcal{F}$,
[\[eq:Kolmo3\]](#eq:Kolmo3){reference-type="ref" reference="eq:Kolmo3"}
may need to be adapted to
$$P\left(\bigcup_{i=1}^\infty E_i\right)=\sum_{i=1}^\infty P(E_i)$$
:::

### Constructing probability functions

::: remark
**Remark 2**. The axioms capture how probabilities behave intuitively,
based on relative frequency (how many times an event occurs over many
repetitions of an experiment), but allocation of useful probabilities
rely on mathematical modelling. All results will be deduced from the
axioms.
:::

::: method
**Method 1**. For a countable sample space, specify probabilities for
each individual $\omega\in\Omega$. For $\Omega=\{w_1,w_2,\dots\}$, let
$\{p_1,p_2\}$ be a set of 'weights' satisfying
$$p_k\ge 0,\quad \sum_{k=1}^\infty p_k=1$$ Then for any event
$E\subseteq \Omega$, $$P(E)=\sum_{k:w_k\in E}p_k$$ Clearly this
satisfies
[\[eq:Kolmo1,eq:Kolmo2\]](#eq:Kolmo1,eq:Kolmo2){reference-type="ref"
reference="eq:Kolmo1,eq:Kolmo2"}. For
[\[eq:Kolmo3\]](#eq:Kolmo3){reference-type="ref" reference="eq:Kolmo3"},
see that
$$P(E\cup F)=\sum_{i:\omega_i\in E\cup F}p_i=\sum_{i:w_i\in E}p_i+\sum_{j:w_j\in F}p_j=P(E)+P(F)$$
:::

::: remark
**Remark 3**. For an uncountable sample space, construction of a
probability function is more difficult, but the axioms still work.
:::

### Deductions

::: cor
**Corollary 4**. $\forall E,F,E_1,\dots E_n\in \mathcal{F}$,
$$\begin{gathered}
        \label{eq:cor1} P(E^c)=1-P(E)\\
        \label{eq:cor2} P(E)\le 1\\
        \label{eq:cor4} P(E\cup F)=P(E)+P(F)-P(E\cap F)\\
        \label{eq:cor3} E\subseteq F\implies P(F\backslash E)=P(F)-P(E)\quad \text{and}\quad P(E)\le P(F)\\
        \label{eq:cor5} P\left(\bigcup_{i=1}^n E_i\right)\le\sum_{i=1}^n P(E_i)
    \end{gathered}$$ $$\begin{aligned}
        \label{eq:cor6}
        \begin{split}
            P\left(\bigcup_{i=1}^n E_i\right)=\!\!&\phantom{-}\:\sum_{i=1}^n\: P(E_i)\\
            &-\:\sum_{i<j}\: P(E_i\cap E_j)\\
            &+\!\sum_{i<j<k}\! P(E_i\cap E_j\cap E_k)\\
            &\phantom{-}\ \ \ \ \vdots\\
            &+(-1)^{n-1}P(E_1\cap\dots\cap E_n)
        \end{split}
    \end{aligned}$$
:::

::: proof
*Proof.*

-   By
    [\[eq:Kolmo3,eq:Kolmo2\]](#eq:Kolmo3,eq:Kolmo2){reference-type="ref"
    reference="eq:Kolmo3,eq:Kolmo2"},
    $$P(E)+P(E^c)=P(E\cup E^c)=P(\Omega)=1$$

-   By [\[eq:Kolmo1,eq:cor1\]](#eq:Kolmo1,eq:cor1){reference-type="ref"
    reference="eq:Kolmo1,eq:cor1"}, $$P(E)\le P(E)+P(E^c)=1$$

-   By [\[eq:Kolmo1,eq:cor1\]](#eq:Kolmo1,eq:cor1){reference-type="ref"
    reference="eq:Kolmo1,eq:cor1"}, $$\begin{aligned}
                P(E\cup F)&=P\big(E\cup(F\cap E^c)\big)\\
                &=P(E)+P(F\cap E^c)\\
                
                &=P(E)+P(F^{cc}\cap E^c)\\
                &=P(E)+P(F^c\cup E)^c\\
                &=P(E)+1-P(F^c\cup E)\\
                &=P(E)+1-P\big(F^c\cup(E\cap F)\big)\\
                &=P(E)+1-P(F^c)-P(E\cap F)\\
                &=P(E)+P(F)-P(E\cap F)
            \end{aligned}$$

-   Since $E\subseteq F$, $F^c\subseteq E^c$, so $F\cup E^c=\Omega$. So
    by [\[eq:cor4,eq:cor1\]](#eq:cor4,eq:cor1){reference-type="ref"
    reference="eq:cor4,eq:cor1"}, $$\begin{aligned}
                P(F\backslash E)&=P(F\cap E^c)\\
                &=P(F)+P(E^c)-P(F\cup E^c)\\
                &=P(F)+1-P(E^c)-P(\Omega)\\
                &=P(F)-P(E)
                \shortintertext{By \cref{eq:Kolmo1},}
                P(E)+P(F\backslash E)&=P(F)\\
                P(E)&\le P(F)
            \end{aligned}$$

-   (by induction) The case $n=1$ is obvious (and $n=2$ is given by
    [\[eq:cor4\]](#eq:cor4){reference-type="ref" reference="eq:cor4"}).
    Let $$U_r=\bigcup_{i=1}^r E_i$$ Suppose true for $n=k$. Then
    $$P\left(U_k\right)\le\sum_{i=1}^k P(E_i)$$ By
    [\[eq:cor4\]](#eq:cor4){reference-type="ref" reference="eq:cor4"},
    $$\begin{aligned}
                P(U_{k+1})&=P(U_k\cup E_{r+1})\\
                &=P(U_k)+P(E_{k+1})-P(U_k\cap E^k+1)
                \shortintertext{By \cref{eq:Kolmo1},}
                &\le P(U_k)+P(E_{k+1})\\
                &=\sum_{i=1}^k P(E_i)+P(E_{k+1})\\
                P(U_{k+1})&\le\sum_{i=1}^{k+1} P(E_i)
            \end{aligned}$$ So true for $n=k+1$.

    True for $n=1$, and true for $n=k\implies$ true for $n=k+1$, so by
    induction, true for $n\in\mathbb{N}$.

-   (by induction) The case $n=2$ is given by
    [\[eq:cor4\]](#eq:cor4){reference-type="ref" reference="eq:cor4"}.
    As before, let $$U_r=\bigcup_{i=1}^r E_i$$ Suppose true for $n=k$.
    Then by [\[eq:cor4\]](#eq:cor4){reference-type="ref"
    reference="eq:cor4"},
    $$P(U_{k+1})=P(U_r\cup E_{k+1})=P(U_k)+P(E_{k+1})-P(U_k\cap E_{k+1})$$
    By [\[eq:dis1\]](#eq:dis1){reference-type="ref"
    reference="eq:dis1"}, $$\begin{aligned}
                U_k\cap E_{k+1}&=(E_1\cup\dots\cup E_k)\cap E_{k+1}\\
                &=(E_1\cap E_{k+1})\cup\dots\cup(E_k\cup E_{k+1})\\
                &=\sum_{i=1}^k E_i\cap E_{k+1}=:\sum_{i=1}^kI_i
            \end{aligned}$$ By the assumption, $$\begin{aligned}
                P(U_k)&=\sum_{i=1}^k P(E_i)-\dots+(-1)^{r-1}P(E_1\cap\dots\cap E_{k+1})\\
                P\left(\bigcup_{i=1}^kI_i\right)&=\sum_{i=1}^k P(I_i)-\dots+(-1)^{r-1}P(I_1\cap\dots\cap I_{k+1})\\
            \end{aligned}$$ So

    $$\begin{aligned}
                P(U_{k+1})\!&=P(U_k)+P(E_{k+1})-P(I_k)\\
                &=\!\sum_{i=1}^k P(E_i)-\dots+(-1)^{r-1}P(E_1\cap\dots\cap E_{k+1})+P(E_{k+1})\\
                &\phantom{=}-\left(\sum_{i=1}^k P(I_i)-\dots+(-1)^{r-1}P(I_1\cap\dots\cap I_{k+1})\right)\\
                &=\!\sum_{i=1}^{k+1}P(E_{k+1})\\
                &\phantom{=}-\sum_{1\le i<j\le k}P(E_i\cap E_j)+\dots+(-1)^{r-1}P(E_1\cap\dots\cap E_{k+1})\\
                &\phantom{=}-\left(\sum_{i=1}^k P(I_i)-\dots+(-1)^{r-1}P(I_1\cap\dots\cap I_{k+1})\right)
                \intertext{Substitute back $I_i=E_i\cap E_{k+1}$, and pair up and combine terms from the two lines.}
                &=\!\sum_{i=1}^{k+1}P(E_{k+1})\\
                &\phantom{=}-\left(\sum_{1\le i<j\le k}P(E_i\cap E_j)+\sum_{i=1}^k P(E_i\cap E_{k+1})\right)\\
                &\phantom{=}+\left(\sum_{1\le i<j<l\le k}P(E_i\cap E_j\cap E_l)+\sum_{1\le i<j\le k}P(I_i\cap I_j)\right)\\
                &\phantom{=}\;\;\vdots\\
                P(U_{k+1})&=\phantom{-}\:\sum_{i=1}^{k+1}\: P(E_i)-\sum_{1\le i<j\le k+1}\: P(E_i\cap E_j)+\dots\\
                &\phantom{=}\dots+(-1)^{k}P(E_1\cap\dots\cap E_{k+1})
            \end{aligned}$$ Hence true for $n=k+1$.

    True for $n=2$, and true for $n=k\implies$ true for $n=k+1$, so by
    induction, true for $n\in\mathbb{Z},\ n\ge 2$.

 ◻
:::

### Independence

::: defi
**Definition 4** (Independent). Events $E$ and $F$ are independent if
$$P(E\cap F)=P(E)P(F)$$ Events $E_1,\dots,E_n$ are mutually independent
if, for any collection $E_{i_1},\dots,E_{i_k}$,
$$P(E_{i_1}\cap\dots E_{i_k})=\prod_{j=1}^k P(E_{i_j})$$
:::

::: remark
**Remark 4**. Independence captures the idea that events are unrelated,
that one does not affect the other.
:::

::: remark
**Remark 5**. For independent events $E,F$, $$\begin{aligned}
        \text{Mutually exclusive}&\iff P(E\cap F)=0\iff P(E)P(F)=0\\
        &\iff P(E)=0\text{ or }P(F)=0
    \end{aligned}$$
:::

::: remark
**Remark 6**. Mutual independence is a stronger condition than pairwise
independence, which only requires pairs of events $E_i,E_j$ to be
independent.
:::

### Conditional probability

::: defi
**Definition 5** (Conditional probability). The conditional probability
of $F$ given $E$ is the probability that $F$ occurs when $E$ is known to
have occurred. For $P(E)>0$, it is given by
$$P(F|E)=\frac{P(E\cap F)}{P(E)}$$
:::

::: remark
**Remark 7**. The definition of conditional probability may be
interpreted as changing the sample space from $\Omega$ to $E$, that is
$P(F|E)$ is the probability of $F$ given that the outcome of the
experiment is known to be in $E$. Note that $P(E|E)=1$.
:::

::: remark
**Remark 8**. If $E$ and $F$ are independent, and $P(E)\ne 0$, then
$$P(F|E)=\frac{P(E\cap F)}{P(E)}=\frac{P(E)P(F)}{P(E)}=P(F)$$ So $E$
occurring does not change the chance of $F$ occurring.
:::

::: {#thm:tot .law}
**Law 5** (Total probability). Let $\{E_i\}$ be a partition of $\Omega$
(the $E_i$s are disjoint, and their union gives $\Omega$). Then for any
event $F$, $$P(F)=\sum_i P(F|E_i)P(E_i)$$
:::

::: proof
*Proof.* By induction on [\[eq:dis1\]](#eq:dis1){reference-type="ref"
reference="eq:dis1"},
$$F=F\cap\Omega=F\cap\left(\bigcup_iE_i\right)=\bigcup_iE_i\cap F$$ So
$$P(F)=\sum_i P(F\cap E_i)=\sum_i P(F|E_i)P(E_i)\qedhere$$ ◻
:::

::: {#thm:bay .thm}
**Theorem 6** (Bayes'). Let $\{E_i\}$ be a partition of $\Omega$ and $F$
be any event with $P(F)>0$. Then
$$P(E_i|F)=\frac{P(F|E_i)P(E_i)}{P(F)}=\frac{P(F|E_i)P(E_i)}{\sum_i P(F|E_i)P(E_i)}$$
:::

::: proof
*Proof.* By definition of conditional probability
$$P(E_i|F)=\frac{P(E_i\cap F)}{P(F)}\quad\text{and}\quad P(E_i\cap F)=P(F|E_i)P(E_i)$$
The denominator comes from the Law of Total Probability (). ◻
:::

::: eg
**Example 2**. An urn contains five red balls and one white ball. A ball
is drawn and then it and another ball of the same colour are placed back
in the urn. Finally a second ball is drawn.

1.  What is the probability that the second ball is white?

2.  If the second ball is white, what is the probability that the first
    was red?

Let $W_i$ be the probability the $i^\text{th}$ ball is white, and $R_i$
the corresponding probability for red.

1.  By the Law of Total Probability (),
    $$\displaystyle P(W_2)=P(W_2|R_1)P(R)+P(W_2|W_1)P(W_1)=\frac17\frac56+\frac27\frac16=\frac16$$

2.  By Bayes' Theorem (),
    $$\displaystyle P(R_1|W_2)=\frac{P(W_2|R_1)P(R_1)}{P(W_2)}=\frac{\frac17\frac56}{\frac16}=\frac57$$
:::

::: {#thm:genmult .law}
**Law 7** (Generalised Multiplication). For events $E_1,\dots,E_n$ that
satisfy $$P(E_1\cap\dots\cap E_{n-1})>0,$$ $$\begin{aligned}
        P\left(\bigcap_{i=1}^nE_i\right)&=\prod_{i=1}^n P(E_i|E_1\cap\dots\cap E_{i-1})\\
        P(E_1\cap \dots \cap E_{n})&=P(E_1)P(E_2|E_1)P(E_3|E_1\cap E_2)\dots P(E_n|E_1\cap\dots \cap E_{n-1})
    \end{aligned}$$
:::

::: proof
*Proof.* All conditional probabilities are defined, since
[\[eq:cor4\]](#eq:cor4){reference-type="ref" reference="eq:cor4"} gives
$$P(E_1)\ge P(E_1\cap E_2)\ge \dots\ge P(E_1\cap\dots\cap E_{n-1})>0$$
By the definition of conditional probability, $$\begin{aligned}
        \prod_{i=1}^n P(E_i|E_1\cap\dots\cap E_{i-1})&=\prod_{i=1}^n\frac{P(E_1\cap \dots \cap E_i)}{P(E_1\cap \dots \cap E_{i-1})}\\
        &=\prod_{i=1}^nP(E_1\cap \dots \cap E_i)\prod_{i=1}^{n-1}\frac{1}{P(E_1\cap \dots \cap E_{i})}\\
        &=\prod_{i=1}^{n-1} \frac{P(E_1\cap \dots \cap E_i)}{P(E_1\cap \dots \cap E_i)}P\left(\bigcap_{i=1}^nE_i\right)\\
        &=P\left(\bigcap_{i=1}^nE_i\right)
    \end{aligned}$$ or written out, $$\begin{aligned}
        P(E_1\cap \dots \cap E_n)&=P(E_1)\frac{P(E_1\cap E_2)}{P(E_1)}\!\frac{P(E_1\cap E_2\cap E_3)}{P(E_1\cap E_2)}\dots\frac{P(E_1\cap E_2\cap E_n)}{P(E_1\cap E_2\cap E_{n-1})}\\
        &=P(E_1)P(E_2|E_1)P(E_3|E_1\cap E_2)\dots P(E_n|E_1\cap\dots \cap E_{n-1})
    \end{aligned}$$ ◻
:::

::: remark
**Remark 9**. This may be useful for problems where an event of interest
arises from a sequence of contributing events.
:::

## Discrete random variables

### Distributions

::: defi
**Definition 6** (Discrete r.v.). For a countable sample space $\Omega$,
a function $$X:\Omega\to\mathbb{R}$$ is called a discrete random
variable (discrete r.v.). This maps outcomes of an experiment to
numbers. For brevity, its usage may be notated
$$P\big(\{\omega:X(\omega)=x\}\big)=P\big(X(\omega)=x\big)=P(X=x)$$
:::

::: eg
**Example 3**. When tossing a coin twice, the number of heads obtained
may be given by the function
$$X=\big\{(HH,2),(HT,1),(TH,1),(TT,0)\big\}$$
:::

::: defi
**Definition 7** (Probability mass function). For a discrete random
variable $X$ taking values in the set $\{x_i\}$, the function
$p_X(x)=P(X=x)$ is the probability mass function (pmf) of $X$.

If unambiguous, this may be written $p_X(x)=p(x)$. For integers, this
may be written $p(X=n)=p_n$.
:::

::: remark
**Remark 10**. For a collection $\{p(x_i)\}$ to be a pmf, it must
satisfy the axioms of probability ().

-   Since the $p$s are probabilities of events, $\forall i\ p(x_i)\ge0$.

-   Since the sample space may be written as a union of disjoint events
    $$\Omega=\bigcup_i\big\{\omega:X(\omega)=x_i\big\}$$ by
    [\[eq:Kolmo3\]](#eq:Kolmo3){reference-type="ref"
    reference="eq:Kolmo3"}, $$\begin{aligned}
                \sum_i p(x_i)&=P\left(\bigcup_i\big\{\omega:X(\omega)=x_i\big\}\right)\\
                &=\sum_i P\big(\big\{\omega:X(\omega)=x_i\big\}\big)=P(\Omega)=1
            \end{aligned}$$

-   Satisfied by the selection of mutually independent events $\{x_i\}$.
:::

::: remark
**Remark 11**. The collection $\{x_i\}$ may be regarded as a sample
space in its own right, with the probability function
$P\big(\{x_i\}\big)=p(x_i.)$. This may be appropriate to use when only
the values taken by $X$ are of interest.
:::

::: notation
**Notation 2**. It may be useful to consider the probability that $X$
lies within an interval.
$$P(a\le X\le b)=P\big(\{\omega:a\le X(\omega)\le b\}\big)=\sum_{i:a\le x_i\le b} p_x(x_i)$$
:::

::: defi
**Definition 8** (CDF). For any random variable $X$, the (Cumulative)
distribution function (cdf) of $X$ is
$$F_X(x)=P(X\le x)=\sum_{i:x_i\le x} p_X(x_i)$$
:::

::: rrule
**Rule 8**. $$\begin{gathered}
        F(x)\to 0\quad\text{as}\quad x\to -\infty\\
        F(x)\to 1\quad\text{as}\quad x\to\infty\\
        F(x)\ \text{is monotonic increasing}\\
        F(x)\ \text{is a step function, with discontinuities at }\{x_i\}\text{ of height }p(x_i)
    \end{gathered}$$
:::

::: proof
*Proof.* Obvious from the axioms of probability (). ◻
:::

::: remark
**Remark 12**. The pmf may be derived from the cdf as
$$p(x)=P(X=x)=P(X\le x)-P(X<x)=\lim_{\delta\to 0^+}\big(F(x)-F(x-\delta)\big)$$
A general version of this result follows in
[9](#thm:disint){reference-type="ref" reference="thm:disint"}
:::

::: {#thm:disint .rrule}
**Rule 9**. $$a<b\implies P(a<X\le b)=F(b)-F(a)$$
:::

::: proof
*Proof.* By [\[eq:Kolmo3\]](#eq:Kolmo3){reference-type="ref"
reference="eq:Kolmo3"} $$\begin{aligned}
        F(b)&=P(X\le b)\\
        &=P\big((X\le  a)\cup (a<X\le b)\big)\\
        &=P(X\le a)+P(a<X\le b)\\
        &=F(a)+P(a<X\le b)\qedhere
    \end{aligned}$$ ◻
:::

### Expectation

::: defi
**Definition 9** (Median). The median of a distribution is
$$x:F(x)=\frac12$$ If repeating an experiment, a random variable would
be expected to lie in equal proportions above and below the median.
:::

::: defi
**Definition 10** (Mode). The mode is the value with highest
probability.
:::

::: defi
**Definition 11** (Expectation). The expectation, or expected value, or
(population) mean of a discrete random variable $X$ is
$$E(X):=\sum_i x_i P(X=x_i)=\sum_i x_ip(x_i)$$ for probability mass
function $p$, provided the sum is well-defined.
:::

::: remark
**Remark 13**. In the countably-infinite case, the sum is not guaranteed
to converge. $E(X)$ exists if the sum converges absolutely, that is,
if$$\sum_i\left\lvert x_i\right\rvert P(X=x_i)<\infty$$
:::

::: remark
**Remark 14**. $E(X)$ represents an idealised long-run average for the
values of $X$.
:::

::: remark
**Remark 15**. Expected value may be calculated using the values taken
by $X$, or directly on the sample space.
$$E(x)=\sum_ix_iP\{\omega:X(\omega)=x_i\}=\sum_{\omega\in\Omega} X(\omega)P({\omega})$$
:::

::: prop
**Proposition 10** (Expectation of a function). For a random variable
$X$ and $\phi:\mathbb{R}\to\mathbb{R}$, $\phi(X)$ is a random variable
$\phi(X):\Omega\to \mathbb{R}$, so its expectation may be calculated
$$\begin{aligned}
        E\big(\phi(X)\big)&=\sum_{\omega\in\Omega} \phi\big(X(\omega)\big)P(\{\omega\})\\
        &=\sum_{i} \phi({x_i})P(\{\omega:X(w)=x_i\})\\
        &=\sum_{i} \phi({x_i})p_X(x_i)
    \end{aligned}$$
:::

::: prop
**Proposition 11**. For all constants $a,c$, $$\begin{aligned}
        \label{eq:expect1}P(X=c)=1&\implies E(X)=c\\
        Y=aX+c&\implies E(Y)=aE(X)+c\label{eq:expect2}
    \end{aligned}$$
:::

::: proof
*Proof.* By definition,

-   $$E(X)=\sum_i x_ip(x_i)=cP(X=c)=c$$

-   $$\begin{aligned}
                E(Y)&=\sum_i (ax_i+b)p(x_i)\\
                &=a\sum_ix_ip(x_i)+b\sum_ip(x_i)\\
                &=aE(X)+b\qedhere
            \end{aligned}$$

 ◻
:::

::: prop
**Proposition 12**. If a random variable $X$ has a symmetric probability
mass function and $E(X)$ exists, then $E(X)$ is the central value.
:::

::: proof
*Proof.* Suppose the pmf is symmetric about zero, so
$X=\{0,\pm x_1,\pm x_2,\dots\}$ with respective probabilities
$p_0,p_1,\dots$. Then
$$E(X)=0p_0+(x_1p_1-x_1p_1)+(x_2p_2-x_2p_2)+\dots=0$$

If $X$ is symmetric about some other value $\mu$, then define $Y=X-\mu$
to get a pmf symmetric about zero, so $E(Y)=0$. Then by
[\[eq:expect1\]](#eq:expect1){reference-type="ref"
reference="eq:expect1"}, $$E(X)=E(Y)+\mu=\mu\qedhere$$ ◻
:::

### Variance

::: defi
**Definition 12** (Variance). When it exists, the $r^\text{th}$ moment
of $X$ about $\alpha$ is $$E\big((X-\alpha)^r\big)$$
:::

::: defi
**Definition 13**. For a random variable $X$ with mean $E(X)=\mu$, the
variance of $X$ is $$\mathop{\mathrm{Var}}(X)=E\big((X-\alpha)^2\big)$$
:::

::: remark
**Remark 16**. $E(X)$ is the first moment about zero, and
$\mathop{\mathrm{Var}}(X)$ is the second moment about $\mu=E(X)$.
:::

::: prop
**Proposition 13**. For a random variable $X$ with $\mu=E(X)$,
$$\begin{aligned}
        \label{eq:var1}\mathop{\mathrm{Var}}(X)&=E(X^2)-\mu^2\\
        \label{eq:var2}\mathop{\mathrm{Var}}(X)&=E\big(X(X-1)\big)-\mu(\mu-1)
    \end{aligned}$$
:::

::: proof
*Proof.* Using [\[eq:expect1\]](#eq:expect1){reference-type="ref"
reference="eq:expect1"} gives

-   $$\begin{aligned}
                E\big((X-\alpha)^2\big)&=E(X^2-2\mu X+\mu^2)\\
                &=E(X^2)-2\mu E(X)+\mu^2\\
                &=E(X^2)-2\mu\mu+\mu^2\\
                &=E(X^2)-\mu^2
            \end{aligned}$$

-   $$\begin{aligned}
                E\big((X-\alpha)^2\big)&=E(X^2-X+X(1-2\mu)+\mu^2)\\
                &=E(X^2-X)+(1-2\mu )E(X)+\mu^2\\
                &=E\big(X(X-1)\big)+(1-2\mu)\mu+\mu^2\\
                &=E\big(X(X-1)\big)-\mu(\mu-1)\qedhere
            \end{aligned}$$

 ◻
:::

::: {#eq:var5 .prop}
**Proposition 14**. For a random variable $X$ and all constants $a,c$,

::: flalign
[]{#eq:var3 label="eq:var3"}&&(X)&     \
[]{#eq:var4 label="eq:var4"}&&(X)=0&P(X=c)=1\
&&Y=aX+c&(Y)=a\^2(X)
:::
:::

::: proof
*Proof.*

-   Variance is a sum of non-negative terms
    $$\mathop{\mathrm{Var}}(X)=E(X-\mu)^2=\sum_i (x_i-\mu)p(x_i)$$

-   By [\[eq:expect1\]](#eq:expect1){reference-type="ref"
    reference="eq:expect1"}, $$\begin{aligned}
                P(X=c)=1&\implies E(X)=c
                \intertext{so by the definition of varience,}
                &\implies \mathop{\mathrm{Var}}(X)=0
            \end{aligned}$$

    Now suppose $X$ is not constant. Then $X$ takes at least two values
    with non-zero probability. Therefore at least one term in
    $$\mathop{\mathrm{Var}}(X)=E(X-\mu)^2=\sum_i (x_i-\mu)p(x_i)$$ must
    not be zero, so $\mathop{\mathrm{Var}}(X)>1$. Hence in this case,
    $\mathop{\mathrm{Var}}(X)\ne 0$.

-   By [\[eq:expect2\]](#eq:expect2){reference-type="ref"
    reference="eq:expect2"}, $$\begin{aligned}
                \mathop{\mathrm{Var}}(Y)&=E\big(Y-E(Y)\big)^2\\
                &=E\big(aX+c-aE(X)-c\big)^2\\
                &=a^2E\big(X-E(X)\big)^2\\
                &=a^2\mathop{\mathrm{Var}}(X)\qedhere
            \end{aligned}$$

 ◻
:::

::: defi
**Definition 14** (Standard definition). Where it exists, the standard
deviation of $X$ is
$$\mathop{\mathrm{sd}}(X)=\sqrt{\mathop{\mathrm{Var}}(X)}$$
:::

::: remark
**Remark 17**. Unlike variance, standard deviation is measured in the
same units of $X$, so has a direct interpretation.
:::

::: notation
**Notation 3**. Expectation, variance and standard deviation may be
notated as $\mu,\sigma^2,\sigma$ respectively, or if necessary,
$\mu_X,\mu_Y,\sigma^2_X,\dots$.
:::

::: remark
**Remark 18**. Expectation may be interpreted as a measure of location,
and varience and standard deviation as measures of spread or dispersion.
:::

::: defi
**Definition 15** (Coefficient of variation). The coefficient of
variation of a random variable $X$ is the dimensionless ratio
$$\frac\sigma\mu$$
:::

### Probability generating function

::: defi
**Definition 16** (PGF). For a random variable $X$ taking values
$0,1,2,\dots$, the probability generation function (pgf) of $X$ is the
power series $$\Pi_X(z)=E(z^X)=\sum_{k=0}^\infty z^kp(k)$$ for all
values of $z$ where the expectation is defined.
:::

::: prop
**Proposition 15**. For a random variable $X$ with pgf $\Pi(z)$, where
the expectations exist, the $n^\text{th}$ factorial moment of $X$ is
$$\begin{aligned}
        \label{eq:pgf1}\Pi(1)&=1\\
        \label{eq:pgf2}\Pi'(1)&=E(X)\\
        \label{eq:pgf3}\Pi''(1)&=E\big(X(X-1)\big)\\
        \label{eq:pgf4}\Pi^{(n)}(1)&=E\left(\frac{X!}{(X-n)!}\right)
    \end{aligned}$$
:::
