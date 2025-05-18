interest is calculated on the Principal plus any accommodated interest from prev periods. It increases each year because it compounds.
$$
\begin{align}
CI &= P\left(1+\frac{R}{100}\right)^T -P \\[1em]
&= P\left(\left(1+\frac{R}{100}\right)^T-1\right) \\[1em]
TotalAmount(A) &= P\left(1+\frac{R}{100}\right)^T
\end{align}
$$
- P $\quad$ principal (initial amount)
- R $\quad$ Rate of interest per year ($\%$)
- T $\quad$ Time period (in years)

**Example:** you took a loan of $10000$ for $3$ years compounded annually at $5\%$.
- Interest after $1st$ year: $\quad \frac{5}{100} \cdot 10000 = 500$
- Interest after $2nd$ year: $\quad \frac{5}{100} \cdot (10000 + 500) = 525$
- Interest after $3rd$ year: $\quad \frac{5}{100} + (10500 + 525) = 551.25$
- So, $\quad CI = 500 + 525 + 551.25 = 1576.25$
- Total Amount, $\quad A = P + CI = 10000 + 1576.25 = 11576.25$

or better we can just use the formula,
$$
\begin{align}
CI &= 10000\left(\left(1+\frac{5}{100}\right)^3 - 1\right) \\[1em]
&= 10000\left(1.05^3 - 1\right) \\[1em]
&= 10000 \cdot 0.157625 \\[1em]
&= 1576.25 \\[1em]
TotalAmount(A) &= P + CI = 10000 + 1576.25 = 11576.25 
\end{align}
$$
### Derivation of Compound Interest Formula
Let `P` be Principal and `R` be the rate.
- Amount after $1st$ year -
$$
P + \frac{P \cdot R}{100} = P\left(1+\frac{R}{100}\right) 
$$
- Amount after $2nd$ year -
$$
\begin{align}
&P\left(1+\frac{R}{100}\right) + P\left(1+\frac{R}{100}\right)\cdot \frac{R}{100} \\[1em]
&P\left(1+\frac{R}{100}\right)\left(1+\frac{R}{100}\right) = P\left(1+\frac{R}{100}\right)^2
\end{align}
$$
- Amount after $3rd$ year -
$$
\begin{align}
&P\left(1+\frac{R}{100}\right)^2 + P\left(1+\frac{R}{100}\right)^2\cdot \frac{R}{100} \\[1em]
&P\left(1+\frac{R}{100}\right)^2\left(1+\frac{R}{100}\right) = P\left(1+\frac{R}{100}\right)^3
\end{align}
$$
- So, Amount after $T$  years -
$$
A = P\left(1+\frac{R}{100}\right)^T
$$
### Basic Problems
#### 1. Invested ₹$3000$ for $2$ years at $5\%$ rate compounded annually. Find Compound Interest?
$$
\begin{align}
CI &= P\left( \left(1 + \frac{R}{100} \right)^T - 1\right) \\[1em]
CI &= 3000 \left( \left( 1 + \frac{5}{100} \right)^2 - 1\right) \\[1em]
CI &= 3000(1.1025 - 1) \Longleftrightarrow \text{₹}307.5
\end{align}
$$
#### 2. You gave a loan of ₹$10000$ for $3$ years compounded annually and earned ₹$600$ extra. Find the rate of interest?
Here we are using $R$ instead of $\frac{R}{100}$, $R$ means $R\%$.
$$
\begin{align}
A &= P + CI \Longleftrightarrow 10000 + 600 = 10600 \\[1em]
A &= P(1+R)^T \\[1em]
10600 &= 10000(1 + R)^3 \\[1em]
(1+R)^3 &= \frac{10600}{10000} = 1.06 \\[1em]
1+r &= \sqrt[3]{1.06} \approx 1.01957 \\[1em]
r &\approx 1.01957 - 1 \approx 1.96\%
\end{align}
$$
#### 3. You invested ₹$1200$ compounded annually at $3\%$ for $5$ years. What is the Total Amount you get?
$$
\begin{align}
A &= P\left( 1 + \frac{R}{100} \right)^T \\[1em]
A &= 1200\left( 1 + \frac{3}{100} \right)^5 \\[1em]
A &\approx 1200 \cdot 1.15927 \approx \text{₹}1391.128
\end{align}
$$
#### 4. You invested ₹$8000$ for $11$ months compounded annually at an interest rate of $3\%$. Find Total Amount?
$$
\begin{align}
A &= P\left( 1 + \frac{R}{100} \right)^T \\[1em]
A &= 8000\left( 1 + \frac{3}{100} \right)^\frac{11}{12} \\[1em]
A &= 8000 \times \sqrt[12]{1.03^{11}} \\[1em]
A &\approx 8000 \times 1.0272 \approx \text{₹}8217.60
\end{align}
$$
#### 5. You get a total of ₹$12000$ after $2$ years compounded annually at an interest rate of $5\%. What was your initial amount?
$$
\begin{align}
A &= P\left( 1 + \frac{R}{100} \right)^T \\[1em]
12000 &= P\left( 1 + \frac{5}{100} \right)^2 \\[1em]
12000 &= P \times 1.1025 \\[1em]
P &= \frac{12000}{1.1025} \approx 10884.3537
\end{align}
$$