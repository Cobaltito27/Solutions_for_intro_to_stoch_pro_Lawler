# 1. Finite Markov Chains

## 1.1 Solution

Yes, it is reasonable. The state space is $S = \{0, 1, 2, 3, 4\}$. Transition matrix $P$ is:

$$ P = 
\begin{bmatrix}
1/3 & 2/3 & 0 & 0 & 0 \\
1/3 & 0 & 2/3 & 0 & 0 \\
1/3 & 0 & 0 & 2/3 & 0 \\
1/3 & 0 & 0 & 0 & 2/3 \\
1 & 0 & 0 & 0 & 0 
\end{bmatrix}
\tag{1.1.1}
$$

## 1.2 Solution

$$ \because
P^3 = 
\begin{bmatrix}
1/3 & 2/3 \\
3/4 & 1/4
\end{bmatrix}^3 =
\begin{bmatrix}
107/216 & 109/216 \\
109/192 & 83/192
\end{bmatrix}
$$

$$
\therefore p_3(0, 1) = 109/216 \tag{1.2.1}
$$

## 1.3 Solution
### 1)
Let's calculate the transition matrix to its power of 100.

$$
P^{100} = 
\begin{bmatrix}
0.4 & 0.2 & 0.4 \\
0.6 & 0 & 0.4 \\
0.2 & 0.5 & 0.3 \\
\end{bmatrix}^{100} \approx
\begin{bmatrix}
25/66 & 17/66 & 4/11 \\
25/66 & 17/66 & 4/11 \\
25/66 & 17/66 & 4/11 \\
\end{bmatrix}
$$

Therefore, $\pi(1) = 25/66$.

### 2)
Let's find the null space of the following matrix ($M$).

$$ M = (P - I)^T =
\begin{bmatrix}
-0.6 & 0.2 & 0.4 \\
0.6 & -1 & 0.4 \\
0.2 & 0.5 & -0.7
\end{bmatrix}^T =
\begin{bmatrix}
-0.6 & 0.6 & 0.2 \\
0.2 & -1 & 0.5 \\
0.4 & 0.4 & -0.7
\end{bmatrix}
$$

Solve $M\vec{\pi} = \vec{0}$, which means:
$$
\begin{bmatrix}
-0.6 & 0.6 & 0.2 \\
0.2 & -1 & 0.5 \\
0.4 & 0.4 & -0.7
\end{bmatrix}
\begin{bmatrix}
\pi_1 \\ \pi_2 \\ \pi_3
\end{bmatrix} =
\begin{bmatrix}
0 \\ 0 \\ 0
\end{bmatrix}
$$

$$ \therefore 
\vec{\pi}^T=(25/24, 17/24, 1)\alpha $$

On the other hand, 

$$
\because \pi_1 + \pi_2 + \pi_3 = 1 \\
\therefore \alpha = 24/66 \\
\therefore \vec{\pi}^T=(25/66, 17/66, 24/66)
$$

Therefore, $\pi(1) = 25/66$.

## 1.4 Solution

$$
P^{100} = 
\begin{bmatrix}
0.2 & 0.4 & 0.4 \\
0.1 & 0.5 & 0.4 \\
0.6 & 0.3 & 0.1 \\
\end{bmatrix}^{100} \approx
\begin{bmatrix}
11/39 & 16/39 & 4/13 \\
11/39 & 16/39 & 4/13 \\
11/39 & 16/39 & 4/13 \\
\end{bmatrix}
$$

The calculation of $\vec{\pi}$ is pretty much the same vis-a-vis Q1.3.

## 1.5 Solution

1. The communication classes are $\{0, 1\}$, $\{2, 4\}$, and $\{3, 5\}$.
2. The first two classes are recurrent, and the last one is transient.
3. In order to solve $\lim_{n \rightarrow + \infty} p_n(0, 0)$, one only needs to consider the transition matrix ($P_1$) of the recurrent class $\{0, 1\}$.

$$ P_1 = 
\begin{bmatrix}
0.5 & 0.5 \\
0.3 & 0.7
\end{bmatrix}
$$

$$ \therefore
\vec{\pi}^T = (\frac{0.3}{0.3+0.5}, \frac{0.5}{0.3+0.5})= (3/8, 5/8)
$$

4. First, let's rearrange the state space into $S = \{0, 1 | 2, 4 | 3, 5\}$. Then the transition matrix $P$ becomes:

$$ P =
\begin{bmatrix}
\begin{matrix}
P_1 & O\\
O & P_2 \\
\end{matrix} & O \\
S & Q
\end{bmatrix},
\ where \ S =
\begin{bmatrix}
0.25 & 0.25 & 0 & 0.25 \\
0 & 0.2 & 0 & 0.2
\end{bmatrix},
\ and \ Q =
\begin{bmatrix}
0 & 0.25 \\
0.2 & 0.4
\end{bmatrix}
$$

Hence, matrix $M$:

$$M = (I-Q)^{-1} = 
\begin{bmatrix}
1 & -0.25 \\
-0.2 & 0.6
\end{bmatrix}^{-1} =
\begin{bmatrix}
12/11 & 5/11 \\
4/11 & 20/11
\end{bmatrix}
$$

$$
MS = \begin{bmatrix}
12/11 & 5/11 \\
4/11 & 20/11
\end{bmatrix}
\begin{bmatrix}
0.25 & 0.25 & 0 & 0.25 \\
0 & 0.2 & 0 & 0.2
\end{bmatrix} =
\begin{bmatrix}
3/11 & 4/11 & 0 & 4/11 \\
1/11 & 5/11 & 0 & 5/11
\end{bmatrix}
$$

We can see that, $\lim_{n \rightarrow + \infty} p_n(5, R1) = 1/11 + 5/11 = 6/11$. Based on previous analysis, $\lim_{n \rightarrow + \infty} p_n(5, 0) = 6/11 \times 3/8 = 9/44$.

## 1.6 Solution

The invariant probability of Q1.3 is:

$$ \vec{\pi}^T =(25/66, 17/66, 24/66). $$

$$ \therefore E(T) = 1/\pi_2 = 66/17 \approx 3.88 $$

## 1.7 Solution

First, let's prove the hint that for an irreducible Markov Chain with a state space of $S = \{1, 2, ..., N\}$, we have $min\{t|P(X_t = j|X_0 = i) > 0\} \le N$ for all $i, j \in S$.

Let's assume that $min\{t|P(X_t = j|X_0 = i) > 0\} > N$ for certain $i, j \in S$.

$$ k := min\{t|P(X_t = j|X_0 = i) > 0\} > N$$

Then,

$$ \exists \  r_0, r_1, r_2, ..., r_{k-1} \in S \ , s.t.$$

$$ P(r_0 \rightarrow r_1)P(r_1 \rightarrow r_2)...P(r_{k-1} \rightarrow j) > 0,\ where\ r_0 = i$$

On the other hand,

$$\because k > N$$

$$\therefore \exists \ 0 \le m < n \le k-1,\ s.t.$$

$$r_m = r_n$$

$$\therefore  P(r_0 \rightarrow r_1)...P(r_{m-1} \rightarrow r_m)P(r_n \rightarrow r_{n+1})...P(r_{k-1} \rightarrow j) > 0,\ where\ r_0 = i$$

It implies that,

$$k-n+m \in \{t|P(X_t = j|X_0 = i) > 0\}, where\ k-n+m < k$$

This contradicts the assumption that $k$ is the minimum in $\{t|P(X_t = j|X_0 = i) > 0\}$.

Thus, $min\{t|P(X_t = j|X_0 = i) > 0\} \le N$ for all $i, j \in S$.

Or equivalently,

$$\exists \ \delta > 0, m \le N, s.t.\ P\{X_m = j|X_0 = i\} > \delta, for\ all\ i,j \in S$$

Then, we can easily see that:

$$P\{X_m \ne j, m = 0,...,n|X_0 = i \} =
  P(i \rightarrow \bar{j})(P(\bar{j}\rightarrow \bar{j}))^n$$

For any $i, j \in S$, we can see that

$$ 0 \le P(\bar{j}\rightarrow \bar{j}) < 1$$

(, since it will not be an irreducible Markov Chain if $P(\bar{j}\rightarrow \bar{j}) = 1$!)

and that,

$$0 \le P(i \rightarrow \bar{j}) \le 1$$

Because there are only a finite number of states,

$$\therefore \exists \ C < \infty , \rho < 1, s.t. $$

$$C = sup\{P(i \rightarrow \bar{j})|i,j \in S\},\ 
 \rho = sup\{ P(\bar{j}\rightarrow \bar{j})|i,j \in S\}$$

Then we have the first conclusion

$$P\{X_m \ne j, m = 0,...,n|X_0 = i \} \le C\rho^n$$

Finally, we will prove that $E(T) < \infty$.

One can easily see that:

$$P(T = n) = P\{X_m \neq j, m = 0, ..., n-1 | X_0 = i\} P\{X_n = j|X_{n-1} \neq j\}
\le C\rho^{n-1}$$

Based on the hint that we have already proven:

$$P(T > N) = 0$$

Therefore,

$$E(T) = \sum_{n = 0}^{\infty}nP(T = n)
       = \sum_{n = 0}^{N}nP(T = n)
       \le \sum_{n = 1}^{N} nC\rho^{n-1}
       \le \sum_{n = 1}^{N} NC
       \le N^2C $$

Here, $N^2C$ is a finite number.

## 1.8 Solution
### a)
The number of edges are $e = 6$, while the number of edges connected to vertex A is $d(A) = 3$. Thus, we have $\pi(A) = \frac{d(A)}{2e} = 1/4$. This is also the fraction of time at vertex A.

### b)
$$1/\pi(A) = 4$$

### c)
Consider a Markov chain with state space S and P:

$$S = \{A, B, C, D, E\}$$
$$P = 
\begin{bmatrix}
0 & 1/3 & 1/3 & 1/3 & 0 \\
1/3 & 0 & 1/3 & 0 & 1/3 \\
1/2 & 1/2 & 0 & 0 & 0 \\
1/2 & 0 & 0 & 0 & 1/2 \\
0 & 1/2 & 0 & 1/2 & 0
\end{bmatrix}
$$

We alter state A into an absorbing state, with a new transition matrix P':

$$P' = 
\begin{bmatrix}
1 & 0 & 0 & 0 & 0 \\
1/3 & 0 & 1/3 & 0 & 1/3 \\
1/2 & 1/2 & 0 & 0 & 0 \\
1/2 & 0 & 0 & 0 & 1/2 \\
0 & 1/2 & 0 & 1/2 & 0
\end{bmatrix}
$$

Here the matrix Q for transient class is:

$$Q = 
\begin{bmatrix}
0 & 1/3 & 0 & 1/3 \\
1/2 & 0 & 0 & 0 \\
0 & 0 & 0 & 1/2 \\
1/2 & 0 & 1/2 & 0
\end{bmatrix}
$$

$$\therefore M = (I-Q)^{-1} = 
\begin{bmatrix}
18/11 & 6/11 & 4/11 & 8/11 \\
9/11 & 14/11 & 2/11 & 4/11 \\
6/11 & 2/11 & 16/11 & 10/11 \\
12/11 & 4/11 & 10/11 & 20/11
\end{bmatrix}
$$

The answer is 9/11.

### (d)

First, define $p(k)$:

$$p(k) = p(X_0 \rightarrow A \rightarrow C|X_0 = k),\ k \in \{A, B, C, D, E\}$$

We can see that:

$$
\begin{cases}
p(A) = 1 \\
p(C) = 0 \\
p(B) = (p(A) + p(C) + p(E))/3 \\
p(D) = (p(A) + p(E))/2 \\
p(E) = (p(B) + p(D))/2
\end{cases}
$$

Hence we have $p(B) = 4/7$.


### (e)

Based on matrix $M$ in (c), the answer is $9/11 + 14/11 + 2/11 + 4/11 = 29/11$.


## 1.9 Solution
### (a)
This Markov chain is irreducible.

### (b)
Its period is 3.

### (c)
$$p_{1000}(2,1) = 0,\ p_{1000}(2,2) = 0, p_{1000}(2,4) = \frac{5}{12}$$

### (d)
$T = 3$ is a constant. Thus, $E(T) = 3$, and $\pi(1) = 1/3$.

### (e)
$$\vec{\pi}^T = (\frac{1}{3}, \frac{1}{9}, \frac{2}{9}, \frac{5}{36}, \frac{7}{36})$$
So the expected return time for state 2 is 9.


## 1.10 Solution
The transition matrix P of this Markov chain is:

$$
P = 
\begin{bmatrix}
3/4 & 1/4 & & & & & \\
1/2 & 1/4 & 1/4 & & & & \\
1/4 & 1/4 & 1/4 & 1/4 & & & \\
1/4 & & 1/4 & 1/4 & 1/4 & & \\
1/4 & & & 1/4 & 1/4 & 1/4 & \\
1/4 & & & & 1/4 & 1/4 & 1/4 \\
1/4 & & & & & 1/4 & 1/2
\end{bmatrix}
$$

### (a)
This Markov Chain is irreducible and aperiodic.

### (b)
One can calculate its invariant probability distribution as $\vec{\pi}$:

$$\vec{\pi}^T = \frac{1}{377}(233, 89, 34, 13, 5, 2, 1)$$

Herein, $p(4) = 5/377,\ p(5) = 2/377,\ p(0) = 233/377$.

### (c)
First, define $p(k)$:

$$p(k) = p(X_0 \rightarrow 6 \rightarrow 0|X_0 = k),\ k \in \{0, 1, 2, 3, 4, 5, 6\}$$

We can see that:

$$
\begin{cases}
p(0) = 0 \\
p(1) = p(0)/2 + p(1)/4 + p(2)/4 \\
p(2) = (p(0) + p(1) + p(2) + p(3))/4 \\
p(3) = (p(0) + p(2) + p(3) + p(4))/4 \\
p(4) = (p(0) + p(3) + p(4) + p(5))/4 \\
p(5) = (p(0) + p(4) + p(5) + p(6))/4 \\
p(6) = 1
\end{cases}
$$

Hence we have $p(1) = 1/144$.

### (d)
The expectation of returning steps for state 3 is 377/13.

### (e)
We alter state 6 into an absorbing state and the $Q$ matrix becomes:

$$
Q =
\begin{bmatrix}
3/4 & 1/4 & & & & \\
1/2 & 1/4 & 1/4 & & & \\
1/4 & 1/4 & 1/4 & 1/4 & & \\
1/4 & & 1/4 & 1/4 & 1/4 & \\
1/4 & & & 1/4 & 1/4 & 1/4 \\
1/4 & & & & 1/4 & 1/4
\end{bmatrix}
$$

$$
M = (I - Q)^{-1} =
\begin{bmatrix}
576 & 220 & 84 & 32 & 12 & 4 \\
572 & 220 & 84 & 32 & 12 & 4 \\
564 & 216 & 84 & 32 & 12 & 4 \\
544 & 208 & 80 & 32 & 12 & 4 \\
492 & 188 & 72 & 28 & 12 & 4 \\
356 & 136 & 52 & 20 & 8 & 4
\end{bmatrix}
$$

$$
M\bar{1} = 
\begin{bmatrix}
928 \\ 924 \\ 912 \\ 880 \\ 796 \\ 576
\end{bmatrix}
$$

Therefore, the expectated number of steps from state 0 to state 6 is 928


## 1.11 Solution

Let's define a Markov chain with state space S and transition matrix P:

$$S = \{0, 1, 2, 3, 4, 5, 6, 7\}$$

$$
P = 
\begin{bmatrix}
0 & 1/6 & 1/6 & 1/6 & 1/6 & 1/6 & 1/6 & 0 \\
0 & 0 & 1/6 & 1/6 & 1/6 & 1/6 & 1/6 & 1/6 \\
1/6 & 0 & 0 & 1/6 & 1/6 & 1/6 & 1/6 & 1/6 \\
1/6 & 1/6 & 0 & 0 & 1/6 & 1/6 & 1/6 & 1/6 \\
1/6 & 1/6 & 1/6 & 0 & 0 & 1/6 & 1/6 & 1/6 \\
1/6 & 1/6 & 1/6 & 1/6 & 0 & 0 & 1/6 & 1/6 \\
1/6 & 1/6 & 1/6 & 1/6 & 1/6 & 0 & 0 & 1/6 \\
1/6 & 1/6 & 1/6 & 1/6 & 1/6 & 1/6 & 0 & 0 \\
\end{bmatrix}
$$

We have $T_1 = min\{n \ge 1: S_n = 0 | S_0 = 0\}$, and $T_2 = min\{n \ge 1: S_n = 1 | S_0 = 0\}$.

$E(T_1)$ can be deduced by calculating the invariant probability distribution $\vec{\pi}^T$. In this case, we have $\vec{\pi}^T = 1/8(1, 1, 1, 1, 1, 1, 1, 1)$. Therefore, $E(T_1) = 8$.

$E(T_2)$ can be computed by first changing state 1 into an absorbing state, and then calculating $(I - Q)^{-1}$ matrix. Here $E(T_2) \approx 6.86$.


## 1.12 Solution

Here we define a nine-state Markov chain with state space S and transition matrix P:

$$S = \{00, 01, 02, 10, 11, 12, 20, 21, 22\}$$

$$
P = 
\begin{bmatrix}
   0.25 &  0.125 &  0.125 &  0.125 & 0.0625 & 0.0625 &  0.125 & 0.0625 & 0.0625 \\
  0.125 &  0.125 &   0.25 & 0.0625 & 0.0625 &  0.125 & 0.0625 & 0.0625 &  0.125 \\
      0 &   0.25 &   0.25 &      0 &  0.125 &  0.125 &      0 &  0.125 &  0.125 \\
  0.125 & 0.0625 & 0.0625 &  0.125 & 0.0625 & 0.0625 &   0.25 &  0.125 &  0.125 \\
 0.0625 & 0.0625 &  0.125 & 0.0625 & 0.0625 &  0.125 &  0.125 &  0.125 &   0.25 \\
      0 &  0.125 &  0.125 &      0 &  0.125 &  0.125 &      0 &   0.25 &   0.25 \\
      0 &      0 &      0 &   0.25 &  0.125 &  0.125 &   0.25 &  0.125 &  0.125 \\
      0 &      0 &      0 &  0.125 &  0.125 &   0.25 &  0.125 &  0.125 &   0.25 \\
      0 &      0 &      0 &      0 &   0.25 &   0.25 &      0 &   0.25 &   0.25 \\
\end{bmatrix}
$$

### (a)
Let set  $\{00, 11, 22\}$ to be absorbing states, and the M matrix is:

$$ \therefore
M = (I - Q)^{-1} = 
\begin{bmatrix}
1.378 & 0.550 & 0.222 & 0.432 & 0.250 & 0.368 \\
0.535 & 1.602 & 0.150 & 0.468 & 0.169 & 0.446 \\
0.222 & 0.250 & 1.378 & 0.368 & 0.550 & 0.432 \\
0.314 & 0.353 & 0.143 & 1.421 & 0.161 & 0.522 \\
0.150 & 0.169 & 0.535 & 0.446 & 1.602 & 0.468 \\
0.143 & 0.161 & 0.314 & 0.522 & 0.353 & 1.421 \\
\end{bmatrix}
$$

$$ \therefore (M\vec{1})^T = (3.20, 3.37, 3.20, 2.91, 3.37, 2.91)$$

So the answer is 3.37.

### (b)
$$ \because
S =
\begin{bmatrix}
0.125 & 0.0625 & 0.125 \\
0.000 & 0.1250 & 0.125 \\
0.125 & 0.0625 & 0.125 \\
0.000 & 0.1250 & 0.250 \\
0.000 & 0.1250 & 0.125 \\
0.000 & 0.1250 & 0.250 \\
\end{bmatrix}
$$

$$ \therefore
MS =
\begin{bmatrix}
0.20000000 & 0.3000000 & 0.5000000 \\
0.08571429 & 0.3785714 & 0.5357143 \\
0.20000000 & 0.3000000 & 0.5000000 \\
0.05714286 & 0.3357143 & 0.6071429 \\
0.08571429 & 0.3785714 & 0.5357143 \\
0.05714286 & 0.3357143 & 0.6071429
\end{bmatrix}
$$

The probability is 0.54.

### (c)

$$\vec{\pi}^T = \frac{1}{121}(4, 8, 10, 8, 16, 20, 10, 20, 45)$$

So the probability is $(4 + 16 + 45)/121 = 65/121$

## 1.13 Solution

### (a)
$$\because \vec{\pi} = \frac{1}{211}(81, 54, 36, 24, 16) $$
$$\therefore E(X) = 262/211$$

### (b)
$$E(T) = 211/81$$

## 1.14 Solution
The method used here is basically the same as similar problems solved before (e.g., Problems 1.8 and 1.10). Herein, we simply give the final numbers with no details in deduction.

### (a)
This Markov Chain is irreducible and periodic (T = 3).

### (b)
$$\vec{\pi} = \frac{1}{37}(10, 5, 5, 3, 14)$$

### (c)
$$37/10 = 3.7$$

### (d)
$$34/3$$

### (e)
$$4/9$$


## 1.15 Solution
### (a)

To prove 

$$r(j) = \sum_{k \in S}r(k)p_{k,j}$$

We will see that:

$$ r(j) = E[\sum_{n=0}^{T - 1}I\{X_n= j\}] = \sum_{n=0}^{T - 1}p\{X_n= j\}$$

$$ \sum_{k \in S}r(k)p_{k,j} =
   \sum_{k \in S}(p_{k,j}\sum_{n=0}^{T - 1}p\{X_n= k\}) =
   \sum_{n=0}^{T - 1}\sum_{k \in S}(p_{k,j}p\{X_n= k\}) =
   \sum_{n=0}^{T - 1} p\{X_{n+1} = j\} = 
   \sum_{n=0}^{T - 1} p\{X_{n} = j\} $$

$$\therefore r(j) = \sum_{k \in S}r(k)p_{k,j}$$
$$\therefore \bar{r} = \bar{r}P $$


### (b)

$$ T = \sum_{n=0}^{T-1}1 = \sum_{n=0}^{T-1}\sum_{j \in S}I\{X_n = j\}
     = \sum_{j \in S}\sum_{n=0}^{T-1}I\{X_n = j\}$$
$$ \therefore E(T) = E(\sum_{j \in S}\sum_{n=0}^{T-1}I\{X_n = j\})
                   = \sum_{j \in S}E(\sum_{n=0}^{T-1}I\{X_n = j\}) =  \sum_{j \in S} r(j)$$

### (c)

$$\because \bar{r}P = \bar{r} $$
$$\therefore \frac{\bar{r}}{E(T)}P = \frac{\bar{r}}{E(T)}$$
$$\because E(T) = \sum_{j \in S} r(j)$$
$$\therefore \frac{\bar{r}}{E(T)} = \bar{\pi}$$
$$\therefore \pi(i) = \frac{r(i)}{E(T)} = \frac{1}{E(T)}$$


## 1.16 Solution
[Here](https://math.stackexchange.com/questions/116446/random-walk-on-n-cycle) are some discussions about the exact question on StackExchange. Below are more details:

First, let's look into a random walk on integer $\bold{Z}$ with $X_0 = 0$. Denote event $E$ as $X$ traverses on every vertex in $[-a, b]$, where $a, b \ge 0$. One can see that:

$$E = E_1 \cup E_2, and\ E_1 \cap E_2 = \emptyset \\
where,\ E_1 = \{X\rightarrow-a\rightarrow b\}, and\ E_2 = \{X\rightarrow b\rightarrow -a\}$$

Then, we will examine $E_1$ thoroughly. In fact, $E_1$ implies a sequence of two events: $X$ visites vertex $-a$ before $b$, and then visits $b$ before $-a-1$. For the first half of event, denote $p(i)$ is the probability of a given vertex (i) visiting $-a$ before $b$, we will see that $p(i)$ must be the particular solution to the following equation:

$$
p(i) =
\begin{cases}
1\ (i \le -a) \\
0.5p(i-1) + 0.5p(i+1)\ (-a \le i \le b) \\
0\ (i \ge b)
\end{cases}
$$

$$\therefore p(i) = \frac{b}{a+b}-\frac{1}{a+b}i \tag{1.16.1} $$
$$\therefore p(0) = \frac{b}{a+b}$$

For the second half, we can use the formula Eq. 1.16.1 and the probability is:

$$q = \frac{1}{a+b+1}$$

Therefore, we have:

$$P(E_1) =  \frac{b}{a+b} \frac{1}{a+b+1} $$

Similarly,

$$P(E_2) =  \frac{a}{a+b} \frac{1}{a+b+1} $$

And,

$$P(E) = P(E_1) + P(E_2) =  \frac{1}{a+b+1} $$

The implication here is that for a random walk on integer $\bold{Z}$ with $X_0 = 0$, the probability to traverse an interval of $[-a, b]$ is identical as long as the length of interval is the same. In this specific problem, we are dealing with intervals an identical lenght of N-1.

## 1.17 Solution

First, we can simplify this problem into a two-state Markov Chain with state space being $S = \{1, \bar{1}\}$ and its transition matrix $P$:

$$P =
\begin{bmatrix}
0 & 1 \\
q & 1-q
\end{bmatrix}, \ where \ q=\frac{1}{N-1}
\tag{1.17.1}
$$

### (a)
The distribution of T should be a derivative of a geometric distribution:

$$
P(T = t) =
\begin{cases}
0, \ t = 1 \\
q(1-q)^{t-2}, \ t \ge 2
\end{cases}
$$

The expectation of T is:

$$
E[T] = 0 \times 1 + \sum_{t = 2}^{\infty}tq(1-q)^{t-2}
     = \frac{1}{1-q} \sum_{t = 2}^{\infty}tq(1-q)^{t-1}
     = \frac{1}{1-q} (\frac{1}{q} - q)
     = \frac{1 + q}{q}
$$

On the other than, the invariant probability of matrix P in Eq. 1.17.1 is:

$$\vec{\pi}^T = (\frac{q}{1+q}, \frac{1}{1+q})$$

So we do have $E[T] = 1/\pi_1$.

### (b)
It is easy to see that $E[T|x_0=2] = 1/q$.

### (c)

Let's define $T_k$ is the first time when the number of visited vertex is $k$. To begin with, $T_1 = 0$ since the random walk must start somewhere, and $T_2 = 1$.

Therefore, we can see that:

$$T_k - T_{k-1} \sim Geometric(p=\frac{N-k+1}{N-1})$$

$$\therefore E[T_k - T_{k-1}] = \frac{1}{p}=\frac{N-1}{N-k+1}$$

$$\therefore E[T_k] = \sum_{k = 2}^N\frac{N-1}{N-k+1}
                    = (N-1) \sum_{n = 1}^{N-1}\frac{1}{n}$$


## 1.18 Solution
$$
52!/(365 \times 24 \times 3600) \approx 2.56 \times 10^{60} \ years
$$

## 1.19 Solution
Let's define a Markov Chain with state space $S = \{0,1,2,3,4\}$ and a transition matrix $P$:
$$
P =
\begin{bmatrix}
0.5 & 0.5 & & & \\
0.5 & & 0.5 & & \\
0.5 & & & 0.5 & \\
0.5 & & & & 0.5 \\
& & & & 1
\end{bmatrix}
$$

And further define a random variable T with:

$$ T:= min(n>0:X_n = 4 | X_0 = 0) $$

We want to know $E(T)$.

### Method A

Apparently, there is one recurrent class $\{4\}$ and one transient class $\{0, 1, 2, 3\}$. According to textbook, its corresponding $Q$ matrix is:

$$ Q =
\begin{bmatrix}
0.5 & 0.5 & & \\
0.5 & & 0.5 & \\
0.5 & & & 0.5 \\
0.5 & & & \\
\end{bmatrix}
$$

$$\therefore
M = (I-Q)^{-1} = 
\begin{bmatrix}
16 & 8 & 4 & 2\\
14 & 8 & 4 & 2\\
12 & 6 & 4 & 2\\
8 & 4 & 2 & 2\\
\end{bmatrix}
$$

$$\therefore
M \vec{1} = 
\begin{bmatrix}
30\\
28\\
24\\
16\\
\end{bmatrix}
$$

This implies that the expectation of number of steps from state 0 to state 4 is 30.

### Method B

Denote $\psi(i)$ is the expected number of steps move from state $i$ to state 4. Based on this Markov chain, one can see that:

$$
\begin{cases}
\psi(0) = 1 + 0.5\psi(0) + 0.5\psi(1) \\
\psi(1) = 1 + 0.5\psi(0) + 0.5\psi(2) \\
\psi(2) = 1 + 0.5\psi(0) + 0.5\psi(3) \\
\psi(3) = 1 + 0.5\psi(0) 
\end{cases}
$$

By solving these linear equations above, one can reach the same results as in Method A. It's not hard to see the resemblance of these two methods if one carefully examine these linear equations.

## 1.20&21 THEOREM PROOF OMITTED

## Reference
Lawler, G. F. (2018). Introduction to stochastic processes. Chapman and Hall/CRC.

https://doi.org/10.1201/9781315273600
