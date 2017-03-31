---
title: "A generalization of the Lexis surface"
author: "Jonas Schöley"
date: "March 31, 2017"
output:
  html_document: default
  pdf_document: default
---

The Lexis surface[^0] is a tool for working with time scales which are linearly dependent on each other, e.g. the two points in time "current period" and "birth cohort" are related by their difference -- the "current age". This relationship can be generalized to $n$ points in time and the $m$ durations between any pair of points. We show that the Lexis diagram, the Lexis' marriage diagram and the APCTDL space are instances of such a generalized Lexis diagram. We start by formalizing the notions of points in time $\textbf{p}$ and durations $\textbf{d}$ between these points.

[^0]: We understand the "Lexis-surface" as the Lexis diagram without the notion of life-lines. While life-lines may be added to the generalized Lexis surface they are not part of our definition -- e.g. a period-age Lexis surface featuring a life-line with clearly marked "death cohort" does not constitute an extension of the Lexis surface by death-cohort. Such an extension is only achieved by adding an orthogonal axis to the period-age plane featuring all possible death-cohorts.

**Definition 1:** Let $\textbf{p}$ be a vector with $n$ elements where $n \geq 2$ and elements $p_{i=1} \ldots p_n \in \mathbb{R}$. Let $\textbf{d}$ be a vector with $m$ elements such that $\textbf{d}_{ij} = p_i - p_j$ for all $i$ and $j = 1, \ldots, n$ where $i>j$.[^1]

**Theorem 1:** The number of elements in $\textbf{d}$ is $m = n(n-1)/2$.

**Proof:** Because $d_{ij}$ must satisfy $i > j$ it can be thought of as all the elements below the subdiagonal of a $n\times n$ matrix of which there are $m = n(n-1)/2$.

**Corollary 1.1:** The sum of the number of elements in $\textbf{p}$ and $\textbf{d}$ is the number of edges on a $n+1$-polytype.

**Proof:** The sum of the number of elements in $p$ and $d$ is $n+m = n + n(n-1)/2$ which is the number of edges on an $n+1$-polytype.

Instead of a particular choice of $n$-points in time we now consider the set $P$ of all possible choices of $n$ points in time.

**Definition 2:** Let $P=\mathbb{R}^n$ be the standard basis vector-space spanning all $\textbf{p}$.

**Theorem 2:** The linear transformation $T_\textbf{A}: P\rightarrow D$ where $D = \mathbb{R}^{n(n-1)/2}$ and $\textbf{A}_T \textbf{p} = \textbf{d}$ is given by[^2]

$$
\underbrace{\left[\begin{matrix}
-\textbf{I}_1 & \Big| & \textbf{1}_1 & \Big| & \textbf{0}_{1 \times n-2} \\
-\textbf{I}_2 & \Big| & \textbf{1}_2 & \Big| & \textbf{0}_{2 \times n-3} \\
\vdots & & \vdots & & \vdots \\
-\textbf{I}_{n-1} & \Big| & \textbf{1}_{n-1} & \Big| & \Big(\textbf{0}_{n-1 \times 0}\Big) \\
\end{matrix}\right]}_{\textbf{A}_T}
\times
\underbrace{\left[\begin{matrix}
p_1 \\ \vdots \\ p_n
\end{matrix}\right]}_{\textbf{p}}
=
\underbrace{\left[\begin{matrix}
d_1 \\ \vdots \\ d_{n(n-1)/2}
\end{matrix}\right]}_{\textbf{d}}.
$$

Given *any* $n$ points in time it is always possible to calculate the durations between any pair of these points. This calculation can be understood as a linear transformation of the *point-space* $P$ to the *duration-space* $D$.

**Proof:** $A_T$ is a simple consequence of the definition of $\textbf{d}$.

**Corollary 2.1:** There exists no linear map $T_\textbf{A}^{-1}: D \rightarrow P$.

Given only a set of $m$ durations it is impossible to identify a single set of $n$ points in time marking the endpoints of the durations, e.g. given only age one can not derive birth cohort and period.

**Proof:** $T_\textbf{A}^{-1}$ exists if and only if $\textbf{A}_T^{-1}$ exists. $\textbf{A}_T$ has no inverse since the columns of $\textbf{A}_T$ are always linearly dependent on each other, i.e. the last element in each row of $\textbf{A}_T$ is always the negation of the sum of all the other row elements. Therefore $T_\textbf{A}^{-1}$ does not exist.

**Theorem 3:** *(Work in progess)* Something that states that you can transform $P^n \leftrightarrow M^n$ where the basis vectors of $M$ are a mixture of point dimensions and duration dimensions.

**Theorem 4:** *(Work in progess)* There are $b = ?$ many ways to choose $n$ elements out of $\left\{p_{i=1,\ldots,n}, d_{k=1,\ldots,m}\right\}$ whoose linear combination yields one or more remaining elements of $\left\{p_{i=1,\ldots,n}, d_{k=1,\ldots,m}\right\}$.


### Example 1: The Lexis surface

Let $\textbf{p}$ have two elements. Then, following definition 1, $\textbf{d}$ is defined as

$$
d_1 = p_2 - p_1.
$$

Interpreting $d_1$ as *age*, $p_2$ as *period* and $p_1$ as *birth cohort* yields the classic APC identities. The Lexis surface as the plane of all possible combinations between *age* and *period* with cohorts as diagonals results from the transformation $P^2 \rightarrow M^2$ as shown to be possible in theorem 3.

### Example 2: Lexis' marriage identity

Along with his well known 2-dimensional diagram Lexis (1875) also published a 3-dimensional extension which he applies to marriage and separation processes.

Let $\textbf{p}$ have three elements. Then $\textbf{d}$ is defined as

$$
\begin{matrix}
d_1 = p_2 - p_1\\
d_2 = p_3 - p_1\\
d_3 = p_3 - p_2
\end{matrix}.
$$

Interpreting $p_1$ as *birth cohort*, $p_2$ as *marriage cohort* and $p_3$ as *separation cohort* yields the durations *age at marriage* ($d_1$), *age at separation* ($d_2$), and *duration of marriage* ($d_3$). Lexis' "marriage space" is reconstructed by transforming $P^3 \rightarrow M^3$ where $M$ has three orthogonal basis vectors corresponding to $(p_1, d_1, d_3)$.

### Example 3: Adding death cohort to the Lexis surface

Equivalent to example 2 we start with a three element vector $\textbf{p}$ yielding the very same identities as shown above.

Interpreting $p_1$ as *birth cohort*, $p_2$ as *period* and $p_3$ as *death cohort* yields the durations *age* ($d_1$), *lifespan* ($d_2$), and *time until death* ($d_3$). This vector space $P^3$ contains the Lexis surface as a sub-space.

[^1]: Equivalently $\textbf{d}$ can be expressed as $\text{vech}(\textbf{p}\times \textbf{1}_n^\textsf{T} - \textbf{1}_n \times \textbf{p}^\textsf{T})$. For ease of notation we use double indices to index each element of the vector $\textbf{d}$. The indices $ij$ of the $k^\text{th}$ element of $\textbf{d}$ are given by $d_{ij} = d_k = p_{i=\left\lfloor \frac {1}{2}+\sqrt{2k}\right\rfloor+1} - p_{j=k-C\left(\left\lfloor \frac{1+\sqrt{8k}}{2}\right\rfloor\right)}$ with $C[f(k)]$ being the binomial coefficient $\left(\begin{matrix} f(k)\\2\end{matrix}\right)$.
[^2]: $\textbf{I}_n$ is the $n \times n$ identity matrix; $\textbf{1}_n$ is a vector with $n$ elements where each element is 1; $\textbf{0}_{m \times n}$ is a $m \times n$ matrix where each element is 0. For notational convenience we allow for a matrix with 0 columns, written $\Big(\textbf{0}_{n \times 0}\Big)$.