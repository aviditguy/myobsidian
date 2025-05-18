## Laws of Exponents
$$
\begin{align}
x^1             &= x \\[1em]
x^0             &= 1 \\[1em]
x^{-n}          &= \frac{1}{x^n} \\[1em]
x^m \cdot x^n   &= x^{(m+n)} \\[1em]
\frac{x^m}{x^n} &= x^{(m-n)} \\[1em]
(x^m)^n         &= x^{m \cdot n} \\[1em]
(x \cdot y)^m   &= x^m \cdot y^m \\[1em]
\left( \frac{x}{y} \right)^m &= \frac{x^m}{y^m} \\[1em]
x^\frac{1}{n}   &= \sqrt[n]{x} \\[1em]
x^\frac{m}{n}   &= \sqrt[n]{x^m}
\end{align}
$$

## Prove $x^0 = 1$
We can prove it in 2 ways -
#### 1. Using the Pattern Approach
Let's examine a pattern with decreasing exponents:
$$
\begin{align}
x^3 &= x \cdot x \cdot x \\[1em]
x^2 &= \frac{x^3}{x} = x \cdot x \\[1em]
x^1 &= \frac{x^2}{x} = x \\[1em]
x^0 &= \frac{x^1}{x} = 1
\end{align}
$$
from here we can conclude $x^0 = 1$ but we can do better.
#### 2. Using the Laws of Exponents
One of the fundamental exponent rule states that:
$$
x^m \cdot x^n = x^{(m+n)}
$$
Let's put $m=a$ and $n=-a$
$$
x^a \cdot x^{-a} = x^{(a+(-a))} = x^0
$$
We also know,
$$
x^a \cdot x^{-a} = x^a \cdot \frac{1}{x^a} = 1
$$
From here we can conclude,
$$
x^0 = 1
$$

## Cool exponents problems
#### 1. Simplify: $\quad \left(81x^6\right)^\frac{1}{4}$
**Solution**
$$
\left(81x^6\right)^\frac{1}{4} = \left(3^4x^6\right)^\frac{1}{4} = 3x\cdot x^\frac{1}{2} = 3x^{1+\frac{1}{2}} = 3x^\frac{3}{2}
$$
#### 2. Solve for $x$: $\quad 3^{2x-1} = 27$
**Solution**
$$
\begin{align}
3^{2x-1} &= 3^3 \\[1em]
2x-1 &= 3 \\[1em]
x = \frac{3+1}{2} &= 2
\end{align}
$$
#### 3. Simplify: $\quad \left(\frac{2^3 \cdot x^{-2}}{4 \cdot x}\right)^2$
**Solution**
$$
\begin{align}
\left(\frac{2^3 \cdot x^{-2}}{4 \cdot x}\right)^2 &= \left(\frac{2^3 \cdot x^{-2}}{2^2 \cdot x}\right)^2 \\[1em]
&= \left(2^{3-2} \cdot x^{-2-1}\right)^2 \\[1em]
&= 2^2 \cdot x^{-6} \\[1em]
&= 4x^{-6}
\end{align}
$$
#### 4. Solve for $x$: $\quad 2^{x+1} = 8^{2x-3}$
**Solution**
$$
\begin{align}
2^{x+1} &= 2^{3(2x-3)} \\[1em]
x+1 &= 6x-9 \\[1em]
5x &= 10 \\[1em]
x &= 2
\end{align}
$$
#### 5. Simplify: $\quad \left(\left(x^\frac{1}{2}\right)^3\right)^4$
**Solution**
$$
\begin{align}
\left(\left(x^\frac{1}{2}\right)^3\right)^4 = \left(x^\frac{3}{2}\right)^4 = x^\frac{3 \cdot 4}{2} = x^6
\end{align}
$$