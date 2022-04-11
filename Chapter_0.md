# 0. Preliminaries
## 0.1 Solution

The coefficient matrix ($A$) of this ODE is:
$$ A=
\begin{bmatrix}
-1 & 1 \\
3 & -3 \\
\end{bmatrix} \tag{0.1.1}
$$

It is easy to see the diagonalization of matrix ($A$) being:

$$ A = Q \Lambda Q^{-1} =
\begin{bmatrix}
1 & 1 \\
1 & -3 \\
\end{bmatrix}
\begin{bmatrix}
0 &  \\
 & -4 \\
\end{bmatrix}
\begin{bmatrix}
3/4 & 1/4 \\
1/4 & -1/4 \\
\end{bmatrix} \tag{0.1.2}
$$

Therefore, the general solution to this ODE should be in the form of Eq. 0.1.3.

$$\vec{y_c}=
e^{At}\vec{c}=
Qe^{\Lambda t}Q^{-1}\vec{c}=
\begin{bmatrix}
1 & 1 \\
1 & -3 \\
\end{bmatrix}
\begin{bmatrix}
1 &  \\
 & e^{-4t} \\
\end{bmatrix}
\begin{bmatrix}
3/4 & 1/4 \\
1/4 & -1/4 \\
\end{bmatrix}
\vec{c} = \frac{1}{4}
\begin{bmatrix}
3+e^{-4t} & 1-e^{-4t} \\
3-3e^{-4t} & 1+3e^{-4t} \\
\end{bmatrix}
\vec{c} \tag{0.1.3}
$$

The particular solution for the given initial condition is:

$$ \because
\frac{1}{4}
\begin{bmatrix}
3+1 & 1-1 \\
3-3 & 1+3 \\
\end{bmatrix}
\vec{c} =
\begin{bmatrix}
1/2 \\
1/2
\end{bmatrix}
$$

$$ \therefore
\vec{c} =
\begin{bmatrix}
1/2 \\
1/2
\end{bmatrix} \tag{0.1.4}
$$

$$ \therefore
\vec{y_p} =
\vec{c} = \frac{1}{4}
\begin{bmatrix}
3+e^{-4t} & 1-e^{-4t} \\
3-3e^{-4t} & 1+3e^{-4t} \\
\end{bmatrix}
\begin{bmatrix}
1/2 \\
1/2
\end{bmatrix} =
\begin{bmatrix}
1/2 \\
1/2
\end{bmatrix} \tag{0.1.5}
$$

## 0.2 Solution
The characteristic equation for this problem is:

$$\lambda = \frac{1}{4} + \frac{3}{4} \lambda^2$$

$$\therefore \lambda_1 = 1, \lambda_2 = 1/3 \tag {0.2.1}$$

Its general solution is:

$$y_c = C_1+C_2(\frac{1}{3})^n \tag{0.2.2}$$

Under its given initial conditions, we have:

$$
\begin{cases}
C_1 + C_2 = 0 \\
C_1 + C_2/3 = 1
\end{cases}
$$

$$
\therefore C_1 = \frac{3}{2}, C_2 = -\frac{3}{2}
$$

$$
\therefore y_p = \frac{3}{2}-\frac{3}{2}(\frac{1}{3})^n
\tag{0.2.3}
$$

## 0.3 Solution
The characteristic equation for this problem is:

$$\lambda^2 - \lambda - 1 = 0$$

$$\therefore \lambda_1 = \frac{1+\sqrt{5}}{2}, \lambda_2 = \frac{1-\sqrt{5}}{2}
\tag {0.3.1}$$

Its general solution is:

$$ y_c = C_1(\frac{1+\sqrt{5}}{2})^n + C_2(\frac{1-\sqrt{5}}{2})^n \tag{0.3.2}$$

Under its given initial conditions, we have:

$$
\begin{cases}
C_1 (\frac{1+\sqrt{5}}{2}) + C_2 (\frac{1-\sqrt{5}}{2}) = 1 \\
C_1 (\frac{1+\sqrt{5}}{2})^2+ C_2 (\frac{1-\sqrt{5}}{2})^2 = 1
\end{cases}
$$

$$
\therefore C_1 = \frac{1}{\sqrt{5}}, C_2 = -\frac{1}{\sqrt{5}}
$$

$$
\therefore y_p = \frac{1}{\sqrt{5}}(\frac{1+\sqrt{5}}{2})^n
                -\frac{1}{\sqrt{5}}(\frac{1-\sqrt{5}}{2})^n
\tag{0.3.3}
$$

## 0.4 Solution

The characteristic equation for this problem is:

$$3\lambda = 1 + \lambda^2 + \lambda^3$$

$$\therefore (\lambda-1)(\lambda^2 + 2\lambda -1) = 0 $$

$$\therefore \lambda_1 = 1, \lambda_2 = -1+\sqrt{2}, \lambda_3 = -1 - \sqrt{2}$$

Its general solution is:

$$\therefore y_c = C_1 + C_2 (-1+\sqrt{2})^n + C_3(-1-\sqrt{2})^n
\tag{0.4.1}$$

Under its initial condistions:

$$
\because \lim_{n \rightarrow + \infty} y_c \ exists\ and = 1 $$

$$
\therefore C_1 = 1, C_3 = 0
\tag{0.4.2}
$$

$$
\because y_p(n=0) = C_1 + C_2 = 0 $$

$$ \therefore C_2 = -1 $$
$$
\therefore y_p = 1-(\sqrt{2} - 1)^n
\tag{0.4.2}
$$

## 0.5 Solution

First, one needs to solve its corresponding homogeneous equation:

$$f(n) = \frac{1}{2} f(n+1) + \frac{1}{2} f(n-1)$$

Its general solution is:

$$\tilde{y_c} = C_1 + C_2n \tag{0.5.1}$$

Then let's try and get a particular solution for this heterogeneous equation using **undetermined coefficient method** by assuming a particular solution in the form of Eq. 0.5.2. (In fact, B and C in Eq. 0.5.2 are not necessary, since they are already implied in its general solution.)

$$ y_p = An^2 + Bn + C \tag{0.5.2} $$

By taking $y_p$ into the original equation, we will see that $A = 1$. Hence the general solution to this heterogeneous equation is:

$$y_c = C_1 + C_2n + n^2 \tag{0.5.3}$$

## 0.6 Solution
Both (a) and (b) have the identical characteristic equation:

$$\lambda^2 + \lambda + 1 = 0 $$

$$\therefore \lambda = -\frac{1}{2} \pm \frac{\sqrt{3}}{2}i$$

Let's denote $\lambda = a \pm bi$ for simplicity.

### (a) ODE

$$
\begin{aligned}
y_c & = C_1e^{\lambda_1t} + C_2e^{\lambda_2t} \\
    & = C_1e^{(a+bi)t} + C_2e^{(a-bi)t} \\
    & = e^{at}(C_1(\cos{bt}+i\sin{bt}) + C_2(\cos{bt}-i\sin{bt})) \\
    & = e^{at}(D_1 \cos{bt} + D_2 \sin{bt})
\end{aligned}
$$

$$
\therefore y_c = e^{-\frac{1}{2}t}(D_1\cos{\frac{\sqrt{3}}{2}t} +
                                     D_2\sin{\frac{\sqrt{3}}{2}t} )
\tag{0.6.1}
$$

### (b) Difference equation

$$ y_c = C_1\lambda_1^n + C_2\lambda_2^n $$

On the other hand, we have:

$$\lambda = -\frac{1}{2} \pm \frac{\sqrt{3}}{2}i = e^{\pm\frac{2}{3}i\pi}$$

$$\therefore \lambda ^ n = e^{\pm\frac{2}{3}in\pi} = \cos{\frac{2}{3}n\pi} \pm i \sin{\frac{2}{3}n\pi}$$

Ultimately, we have:

$$y_c = D_1 \cos{\frac{2}{3}n\pi} + D_2 sin{\frac{2}{3}n\pi}$$
