# (PART) Midterm Mock {.unnumbered}

# Sem 1 2021-2022 

## Question 1 (10 points) {.unnumbered}

A fair coin is flipped repeatedly. Find the expected number of flips
needed to get three consecutive tails followed by a heads (TTTH in a row)

> Let X be the expected number of flips we need to get three consecutive tails followed by a heads (TTTH in a row).
Flipping 4 coins repeatedly and observe four consecutive outcomes, we have the following cases:

><h4>Case 1 (H): A head appears on the first flip.</h4>
On the first flip of the coin, there is a 1/2 chance we get a heads. In this case, we are back at the starting point and we have wasted 1 flip thus the expected number of flips needed will be X + 1.

><h4>Case 2 (TH): A tails appears on the first flip and then a heads appears on the second flip.</h4>
The chance a tails appears on the first flip is $\frac{1}{2}$ and the chance a heads appears on the second flip is $\frac{1}{2}$ so the probability to get a tails appears on the first flip and then a heads appears on the second flip is $\frac{1}{2} \cdot \frac{1}{2} = \frac{1}{4}$. In this case, we are back at the starting point and we have wasted 2 flips thus the expected number of flips needed will be X + 2.

><h4>Case 3 (TTH): Two tails appear on the first and the second flips and one heads appear on the third flip.  </h4>
The chance a tails appears on the first flip is $\frac{1}{2}$ and the chance a tails appears on the second flip is $\frac{1}{2}$ and the chance a heads appears on the third flip is $\frac{1}{2}$ so two tails appear on the first and the second flips and one heads appear on the third flip is $\frac{1}{2} \cdot \frac{1}{2} \cdot \frac{1}{2} = \frac{1}{8}$. In this case, we are back at the starting point and we have wasted 3 flips thus the expected number of flips needed will be X + 3.

><h4>Case 4 (TTTT): Four tails appear on 4 flips. </h4>
The chance a tails appears on the first flip is $\frac{1}{2}$ and the chance a tails appears on the second flip is $\frac{1}{2}$ and the chance a tails appears on the third flip is $\frac{1}{2}$ and the chance a tails appear on the fourth flip is $\frac{1}{2}$ so the probability to get four tails appear on 4 flips is $\frac{1}{2} \cdot \frac{1}{2} \cdot \frac{1}{2} \cdot \frac{1}{2}= \frac{1}{16}$. In this case, we are back at the starting point and we have wasted 4 flips thus the expected number of flips needed will be X + 4.

><h4>Case 5 (TTTH): Three consecutive tails followed by a heads.  </h4>
The chance a tails appears on the first flip is $\frac{1}{2}$ and the chance a tails appears on the second flip is $\frac{1}{2}$ and the chance a tails appears on the third flip is $\frac{1}{2}$ and the chance a heads appear on the fourth flip is $\frac{1}{2}$ so the probability to get three consecutive tails followed by a heads is $\frac{1}{2} \cdot \frac{1}{2} \cdot \frac{1}{2}\cdot \frac{1}{2} = \frac{1}{16}$. In this case, the expected flips needed will be 4.

> Framing the above three cases in the form of equations and adding we will get:
$$\begin{align*}
X&=(1+X)\frac{1}{2}+(2+X)\frac{1}{4}+(3+X)\frac{1}{8}+(4+X)\frac{1}{16}+(4) \frac{1}{16} \\
    \rightarrow X&=30
    \end{align*}$$

> Answer: On average, the coin needs flipping 30 times to get three consecutive tails followed by a heads (TTTH in a row).

## Question 2 (20 points) {.unnumbered}

Consider the asset price process $(S_t)_{t \geq 0}$ follows an equation:
$$ \,dS_t = (0.04t + 0.08t^3)\,dt + 0.3 \,dW_t $$
where $(W_t)_{t \geq 0}$ is a standard Brownian motion on a filtered probability space $(\omega,\mathcal{F},(\mathcal{F}_t)_{t \geq 0}$. Suppose the asset price is now 10.

### a. (10 points)  {.unnumbered}

What is the probability that the asset price after 3 years from now (i.e $S_3$) will be less than 13?

>$$\begin{align*}
\,dS_t &= (0.04t + 0.08t^3)\,dt + 0.3 \,dW_t \\
\int_0^3 \,dS_t &= \int_0^3 (0.04t + 0.08t^3)\,dt + \int_0^3 0.3 \,dW_t \\
S_3 - S_0 &= 1.8 + 0.3 (W_3-W_0) \\
S_3 &= 11.8 + 0.3W_3 \\
\end{align*}$$

>$$\begin{align*}
\mathcal{P}(S_3 < 13) &= \mathcal{P}(11.8 + 0.3W_3 < 13) \\
&= \mathcal{P} \left(W_3 < \frac{13-11.8}{0.3}\right) \\
&= \mathcal{P} \left(\mathcal{Z} < \frac{13-11.8}{0.3\sqrt{3}}\right) \\
&= \Phi(2.31) \\
&= 0.98954
\end{align*}$$

>Answer: The probability that the asset price after 3 years from now (i.e $S_3$) will be less than 13 is $98.954\%$.

### b. (10 points)  {.unnumbered}

What is the expected price after 3 years from now?

>$$\begin{align*}
W_3 &\sim \mathcal{N}(0,3) \\
11.8+ 0.3W_3 &\sim \mathcal{N}(11.8,0.3^2 \cdot3) \\
(S_3|S_0 = 10) &\sim \mathcal{N}(11.8,0.27)
\end{align*}$$

>Answer: The expected price after 3 years from now is 11.8.

### b'. (0 points)  {.unnumbered}

What is the expected value and variance of the exponential price after 3 years from now?

>$$\begin{align*}
(S_3|S_0 = 10) &\sim \mathcal{N}(11.8,0.27) \\
e^{(S_3|S_0 = 10)} &\sim \log \mathcal{N}(11.8,0.27)
\end{align*}$$

>$$\begin{align*}
E[e^{(S_3|S_0 = 10)}] &= e^{\mu+\frac{1}{2}\sigma^2} \\
&= e^{11.8+\frac{1}{2}0.27} \\ 
&\approx e^{11.935}
\end{align*}$$

>$$\begin{align*}
Var(e^{(S_3|S_0 = 10)})&= e^{2\mu+\sigma^2}(e^{\sigma^2}-1)\\
&=e^{\left(2 \cdot 11.8+0.27 \right)}\left(e^{0.27}-1\right)  \\
&\approx e^{23.87}\left(e^{0.27}-1\right)
\end{align*}$$

>Answer: the expected value and variance of the exponential price after 3 years from now are $E[e^{(S_3|S_0 = 10)}]=e^{11.935}$ and $Var(e^{(S_3|S_0 = 10)})=e^{23.87}\left(e^{0.27}-1\right)$

## Question 3 (20 points) {.unnumbered}

Let $\{(W_t)_t \geq 0\}$ be a standard Brownian motion on the probability space $(\Omega,\mathcal{F},\mathcal{P})$. Suppose that the process $(X_t)_t \geq 0$ is governed by the equation:
$\,d X_t =4tX_t\,dt+(3t^2-2t)X_t\,dW_t$.
Find the distribution, the mean and variance of the random variable
$(X_5|X_2 = 3)$.

>Let $Y_t=\ln X_t$ and $f(t,x)=\ln x$, we have:
$$\begin{align*}
f_t&=0 \\
f_x&=\frac{1}{x} \\
f_{tt}&=0 \\
f_{xx}&=-\frac{1}{x^2} \\
f_{tx}&=0 \\
\end{align*}$$

>Applying Ito Doeblin formula, we have:
$$\begin{align*}
dY_t&= \frac{1}{X_t}(4tX_t\,dt+(3t^2-2t)X_t\,dW_t) - \frac{1}{2}\frac{1}{X_t^2}(4tX_t\,dt+(3t^2-2t)X_t\,dW_t)^2 \\
dY_t&= \frac{1}{X_t} \cdot 4tX_t\,dt+ \frac{1}{X_t} \cdot(3t^2-2t)X_t\,dW_t - \frac{1}{2}\frac{1}{X_t^2} \cdot (3t^2-2t)^2X_t^2\,dW_t^2 \\
dY_t&=   4t\,dt+  (3t^2-2t)\,dW_t - \frac{1}{2}  (3t^2-2t)^2\,dt \\
dY_t&=   \left(4t-\frac{1}{2}  (3t^2-2t)^2 \right)\,dt+  (3t^2-2t)\,dW_t \\
\rightarrow \int_2^5 dY_t&=   \int_2^5 \left(4t-\frac{1}{2}  (3t^2-2t)^2 \right)\,dt+  \int_2^5(3t^2-2t)\,dW_t \\
\rightarrow  Y_5-Y_2  &= -1906.2 +  \int_2^5(3t^2-2t)\,dW_t \\
\rightarrow  \ln X_5-\ln X_2  &= -1906.2 +  \int_2^5(3t^2-2t)\,dW_t \\
\rightarrow  X_5  &= e^{\ln X_2-1906.2 +  \int_2^5(3t^2-2t)\,dW_t \\} \\
\end{align*}$$

>$$\begin{align*}
\int_2^5(3t^2-2t)\,dW_t &\sim \mathcal{N} \left(0,\int_2^5 (3t^2-2t)^2 \,d t \right) \\
&\sim \mathcal{N}\left(0,3896.4 \right) \\
\end{align*}$$

>$$\begin{align*}
\rightarrow \ln X_2-1906.2+\int_2^5(3t^2-2t)\,dW_t &\sim \mathcal{N} \left(\ln X_2-1906.2,3896.4 \right) \\
\rightarrow e^{\ln X_2-1906.2+\int_2^5(3t^2-2t)\,dW_t} &\sim \log\mathcal{N} \left(\ln X_2-1906.2,3896.4 \right) \\
\rightarrow X_5 &\sim \log\mathcal{N} \left(\ln X_2-1906.2,3896.4 \right) \\
\end{align*}$$

>$$\begin{align*}
(X_5|X_2=3) &\sim \log\mathcal{N} \left(\ln 3-1906.2,3896.4 \right) \\
\end{align*}$$

>
$$\begin{align*}
E[X_5|X_2=3]&= e^{\mu+\frac{1}{2}\sigma^2} \\
&=e^{\ln 3-1906.2+ \frac{1}{2} \cdot 3896.4} \\
&\approx e^{43} \\
Var(X_5|X_2=3)&= e^{2\mu+\sigma^2}(e^{\sigma^2}-1)\\
&=e^{\left(2(\ln 3-1906.2)+3896.4 \right)}\left(e^{3896.4}-1\right)  \\
&\approx e^{86}\left(e^{3896}-1\right)
\end{align*}$$

>Answer: The mean and variance of $(X_5|X_2=3)$ are $e^{43}$ and $e^{86}\left(e^{3896}-1\right)$

## Question 4 (50 points) {.unnumbered}

Suppose the stochastic process of the asset price $S_t$ follows a geometric
Brownian motion:
$$\,d S_t = 0.2 S_t \,dt + 0.3 S_t \,dW_t^\mathcal{P}$$
where $W_t^P$
is a standard Brownian motion on the real world probability
space, denoted by $(\omega, \mathcal{F},\mathcal{P})$. A European put option written on the stock
with parameters: exercise price $K = 15$, maturity time $T=2$, $t=0.5$ (year), the
risk-free interest rate is $r = 0.06$, $S_t=12$.

### a. (15 points)  {.unnumbered}

Let $\widetilde W_t = W_t + \theta t$, with $\theta$ being a constant is an adapted process with respect to the filtration $()\mathcal{F}_t)_{t \geq 0}$. Find $\theta$ such that the discounted $(e^{???0.07t}S_t)_{t \ge 0}$ is a martingale process with respect to $\widetilde W_t$.

>Let $\mathcal{P}$ and $\mathcal{Q}$ be the physical and risk neutral measures on $(\omega,\mathcal{F})$ respectively. Let $\{W_t^\mathcal{P}\}_{t \geq 0}$ be the standard Brownian motion on $\mathcal{P}$. For $\{S_t\}_{t \geq 0}$ be the process of asset price, we have:
$$dSt = 0.2S_t \,dt + 0.3 S_t \,dW_t^\mathcal{P}$$

>With $f(t,x)=e^{-0.07t}x$ then we can calculate:
$$\begin{align*} 
f_t&=-0.07e^{-0.07t}x \\
f_x&=e^{-0.07t} \\
f_{tt}&=0.07^2e^{-0.07t}x \\
f_{xx}&=0 \\
f_{tx}&=-0.07e^{-0.07t}
\end{align*}$$

>Applying Ito-Doeblin formula, we have:
$$\begin{align*}
d(e^{-0.07t}S_t) &= -0.07e^{-0.07t}S_t\,dt+e^{-0.07t}\,dS_t -0.07e^{-0.07t}\,dt \,dS_t \\
&= -0.07e^{-0.07t}S_t\,dt+e^{-0.07t}(0.2 S_t \,dt + 0.3 S_t \,dW_t^\mathcal{P}) \\
&-0.07e^{-0.07t}\,dt(0.2 S_t \,dt + 0.3 S_t \,dW_t^\mathcal{P}) \\
&= e^{-0.07t}S_t[(0.2-0.07) \,dt+0.3 \,d W_t^{\mathcal{P}}] \\
&-0.07 \cdot 0.2 e^{-0.07t}St\,dt^2 - 0.07 \cdot 0.3 S_t \,dt\,dW_t^\mathcal{P})\\
&= e^{-0.07t}S_t[(0.2-0.07) \,dt+0.3 (\,d W_t^{\mathcal{Q}}-\theta_t) \,dt] \\
&= e^{-0.07t}S_t[(0.2-0.07-0.3 \theta_t) \,dt+0.3 \,d W_t^{\mathcal{Q}} \,dt]
\end{align*}$$

>In order to have the process $\{e^{-0.07t}S_t\}_{t \geq 0}$ be the martigale process, we choose $\theta_t$ such that:
$$-0.07+0.2-0.3 \theta_t=0 \rightarrow \theta_t=\frac{-0.07+0.2}{0.3}=0.434 $$
then $$E^\mathcal{P}[e^{\frac{1}{2} \int_0^T \theta_t^2\,dt}]<\infty$$

### b'. (0 points) CALL {.unnumbered}

Derive the Black-Scholes-Merton formula and then compute the option price.

>Let $\mathcal{P}$ and $\mathcal{Q}$ be the physical and risk neutral measures on $(\omega,\mathcal{F})$ respectively. Let $\{W_t^\mathcal{P}\}_{t \geq 0}$ be the standard Brownian motion on $\mathcal{P}$. For $\{S_t\}_{t \geq 0}$ be the process of asset price, we have:
$$dSt = \mu S_t \,dt + \sigma S_t \,dW_t^\mathcal{P}$$

>With $f(t,x)=e^{-rt}x$ then we can calculate:
$$\begin{align*} 
f_t&=-re^{-rt}x \\
f_x&=e^{-rt} \\
f_{tt}&=r^2e^{-rt}x \\
f_{xx}&=0 \\
f_{tx}&=-re^{-rt}
\end{align*}$$

>Applying Ito-Doeblin formula, we have:
$$\begin{align*}
d(e^{-rt}S_t) &= -re^{-rt}S_t\,dt+e^{-rt}\,dS_t -re^{-rt}\,dt \,dS_t \\
&= -re^{-rt}S_t\,dt+e^{-rt}(\mu S_t \,dt + \sigma S_t \,dW_t^\mathcal{P}) -re^{-rt}\,dt(\mu S_t \,dt + \sigma S_t \,dW_t^\mathcal{P}) \\
&= e^{-rt}S_t[(\mu-r) \,dt+\sigma \,d W_t^{\mathcal{P}}] -\mu re^{-rt}St\,dt^2 + \sigma S_t \,dt\,dW_t^\mathcal{P})\\
&= e^{-rt}S_t[\mu-r \,dt+\sigma (\,d W_t^{\mathcal{Q}}-\theta_t) \,dt] \\
&= e^{-rt}S_t[(\mu-r-\sigma \theta_t) \,dt+\sigma \,d W_t^{\mathcal{Q}} \,dt]
\end{align*}$$

>In order to have the process $\{e^{???rt}S_t\}_{t \geq 0}$ be the martigale process, we choose $\theta_t$ such that:
$$\mu-r-\sigma \theta_t=0 \rightarrow \theta_t=\frac{\mu-r}{\sigma} $$
then $$E^\mathcal{P}[e^{\frac{1}{2} \int_0^T \theta_t^2\,dt}]<\infty$$

>By the Girsanov???s theorem, there is a risk neutral measure $\mathcal{Q}$ defined by the Radon-Nykodym $$E \left[\frac{\,d \mathcal{Q}}{\,d \mathcal{P}} |\mathcal{F}_t\right]=Z_t=e^{-\int_0^t \theta_s \,d W_s^\mathcal{P}-\frac{1}{2} \theta_s^2 \,ds}$$ such that $W_t^\mathcal{Q}=W_t^\mathcal{P}+\int_0^t\theta_s \,ds$  
is the standard Brownian motion under $\mathcal{Q}$.
$$W_t^\mathcal{Q}=W_t^\mathcal{P}+\int_0^t\theta_s \,ds \\
\rightarrow \,dW_t^\mathcal{Q}=\,dW_t^\mathcal{P}+\theta_t\,dt$$

>Since $e^{-rt}S_t$ is a martingale under $\mathcal{Q}$ and $\mathcal{Q}$ is an equivalent martingale measure to $\mathcal{P}$, we can write:
$$\begin{align*}
\,dS_t &= \mu S_t \,dt + \sigma S_t \,dW_t^\mathcal{P} \\
&=\mu S_t \,dt + \sigma S_t (\,dW_t^\mathcal{Q}-\theta_t \,dt) \\
&=\mu S_t \,dt + \sigma S_t (\,dW_t^\mathcal{Q}-\frac{\mu-r}{\sigma} \,dt) \\
&=\left(\mu-\sigma\cdot\frac{\mu-r}{\sigma} \right)S_t \,dt + \sigma S_t \,dW_t^\mathcal{Q} \\
&=rS_t \,dt + \sigma S_t \,dW_t^\mathcal{Q} \\
\end{align*}$$

>Let $Y_t=\ln S_t$ and $f(t,x)=\ln x$, we have:
$$\begin{align*}
f_t&=0 \\
f_x&=\frac{1}{x} \\
f_{tt}&=0 \\
f_{xx}&=-\frac{1}{x^2} \\
f_{tx}&=0 \\
\end{align*}$$

>Applying Ito Doeblin formula, we have:
$$\begin{align*}
\,d(Y_t)&=\frac{1}{S_t} \,dS_t-\frac{1}{2}\frac{1}{S_t^2}\,dS_t^2 \\
&=\frac{1}{S_t} (rS_t \,dt + \sigma S_t \,dW_t^\mathcal{Q})-\frac{1}{2}\frac{1}{S_t^2}(rS_t \,dt + \sigma S_t \,dW_t^\mathcal{Q})^2 \\
&=(r-\frac{1}{2} \cdot \sigma^2)\,dt + \sigma \,dW_t^\mathcal{Q} \\
\,d(\ln S_t)&=(r-\frac{1}{2} \cdot \sigma^2)\,dt + \sigma \,dW_t^\mathcal{Q} \\
 \int_t^T \,d(\ln S_s)&=\int_t^T(r-\frac{1}{2} \cdot \sigma^2)\,ds + \int_t^T\sigma \,dW_s^\mathcal{Q} \\
 \ln \left( \frac{S_T}{S_t} \right)&=(r-\frac{1}{2} \cdot \sigma^2)(T-t)+\sigma(W_T^\mathcal{Q}-W_t^\mathcal{Q}) \\
 S_T&=e^{\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t)+\sigma(W_T^{\mathcal{Q}}-W_t^{\mathcal{Q}})}
\end{align*}$$

>We have
$$\begin{align*}
\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t)+\sigma(W_T^{\mathcal{Q}}-W_t^{\mathcal{Q}}) &\sim \mathcal{N}(\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t),\sigma^2(T-t)) \\
e^{\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t)+\sigma(W_T^{\mathcal{Q}}-W_t^{\mathcal{Q}})} &\sim \ln \mathcal{N}(\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t),\sigma^2(T-t)) \\
 (S_T|S_t) &\sim \ln \mathcal{N}(\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t),\sigma^2(T-t)) \\
\end{align*}$$

>The probability density function of $(S_T|S_t)$ is
$$f_{S_T|S_t}(x)=\frac{1}{\sigma x\sqrt{2\pi(T-t)}}e^{-\frac{1}{2} \frac{(\ln x-(\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t)))^2}{\sigma^2(T-t)}} $$

>From Feyman-Kac formula we have:
$$ C(S_t,t)=e^{-r(T-t)} \mathbb{E}^\mathcal{Q}[max(S_T-K,0)|\mathcal{F}_t] $$

>Applying the moment generating function, we have:
$$\begin{align*} 
C(S_t,t)&=e^{-r(T-t)}\int_{-\infty}^\infty \max(x-K,0) f_{S_T|S_t}(x) \,dx \\
&=e^{-r(T-t)}\int_K^\infty (x-K) \frac{1}{\sigma x\sqrt{2\pi}\sqrt{(T-t)}}e^{-\frac{1}{2} \frac{(\ln x-(\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t)))^2}{\sigma^2(T-t)}} \,dx
\end{align*}$$

>
$$\begin{align*}
C(S_t,t)&=e^{-r(T-t)}\int_K^\infty (x-K) \frac{1}{\sigma x\sqrt{2\pi}\sqrt{(T-t)}}e^{-\frac{1}{2} \frac{(\ln x-(\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t)))^2}{\sigma^2(T-t)}} \,dx \\
&=\frac{e^{-r(T-t)}}{\sigma \sqrt{2\pi}\sqrt{(T-t)}} \int_K^\infty (x-K)e^{-\frac{1}{2} \frac{(\ln x-\ln S_t -(r-\frac{1}{2} \cdot \sigma^2)(T-t)))^2}{\sigma^2(T-t)}} \frac{1}{x}\,dx
\end{align*}$$

>Let $u=\frac{\ln x-\ln S_t -(r-\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}$, we have
$$\begin{align*}
\ln \left( \frac{x}{S_t} \right)&=\sigma u\sqrt{T-t}+(r-\frac{1}{2} \cdot \sigma^2)(T-t) \\
x&=S_te^{\sigma u\sqrt{T-t}+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}
\end{align*}$$ 

>
$$\begin{align*}
\,du&=\frac{1}{\sigma x\sqrt{T-t}}\,dx \\
\sigma\sqrt{T-t}\,du&=\frac{1}{x}\,dx
\end{align*}$$

>$$\begin{align*}
u_K&=\frac{\ln K-\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}} \\
&=\frac{\ln \left( \frac{K}{S_t} \right)+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}
\end{align*}$$

>The value of the call option becomes:
$$\begin{align*}
C(S_t,t)&=\frac{e^{-r(T-t)}}{\sigma \sqrt{2\pi} \sqrt{T-t}} \int_K^\infty (x-K)e^{-\frac{1}{2} \frac{(\ln x-\ln S_t -(r-\frac{1}{2} \cdot \sigma^2)(T-t)))^2}{\sigma^2(T-t)}} \frac{1}{x}\,dx \\
&=\frac{e^{-r(T-t)}}{\sigma \sqrt{2\pi}\sqrt{T-t}} \int_{u_K}^\infty (S_te^{\sigma u\sqrt{T-t}+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}-K)e^{-\frac{1}{2} u^2} \sigma\sqrt{T-t}\,du \\
&=\frac{e^{-r(T-t)}}{\sigma\sqrt{2\pi}\sqrt{T-t}} \sigma\sqrt{T-t} \int_{u_K}^\infty (S_te^{\sigma u\sqrt{T-t}+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}e^{-\frac{1}{2} u^2}-Ke^{-\frac{1}{2} u^2}) \,du \\
&=\frac{e^{-r(T-t)}}{\sqrt{2\pi}} \int_{u_K}^\infty (S_te^{\sigma u\sqrt{T-t}+(r-\frac{1}{2} \cdot \sigma^2)(T-t)-\frac{1}{2} u^2}-Ke^{-\frac{1}{2} u^2}) \,du \\
&=\frac{1}{\sqrt{2\pi}} \int_{u_K}^\infty S_te^{\sigma u\sqrt{T-t}-\frac{1}{2} \cdot \sigma^2(T-t)-\frac{1}{2} u^2}\,du \\
&-\frac{e^{-r(T-t)}}{\sqrt{2\pi}} \int_{u_K}^\infty Ke^{-\frac{1}{2} u^2} \,du \\
&=I_1 \\ 
&-  I_2 \\
\end{align*}$$

>
$$\begin{align*}
I_1 &=S_t \cdot \frac{1}{\sqrt{2\pi}} \int_{u_K}^\infty e^{-\frac{1}{2} u^2+\sigma u\sqrt{T-t}-\frac{1}{2} \cdot \sigma^2(T-t)}\,du \\
&=S_t \cdot \frac{1}{\sqrt{2\pi}} \int_{u_K}^\infty e^{-\frac{1}{2} (u-\sigma\sqrt{T-t})^2}\,du \\
&=S_t \cdot \frac{1}{\sqrt{2\pi}} \int_{u_K}^\infty e^{-\frac{1}{2} (u-\sigma\sqrt{T-t})^2}\,d(u-\sigma\sqrt{T-t}) \\
&=S_t \cdot \frac{1}{\sqrt{2\pi}} \int_{u_K-\sigma\sqrt{T-t}}^\infty e^{-\frac{1}{2} u^2}\,du \\
&= S_t \cdot \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{\sigma\sqrt{T-t}-u_K} e^{-\frac{1}{2} u^2}\,du \\
&=S_t\cdot \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{\sigma\sqrt{T-t}-\frac{\ln \left( \frac{K}{S_t} \right)-(r-\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}} e^{-\frac{1}{2} u^2}\,du \\
&=S_t\cdot \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{\frac{\sigma^2(T-t)-\ln \left( \frac{K}{S_t} \right)-(r-\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}} e^{-\frac{1}{2} u^2}\,du \\
&=S_t\cdot \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{\frac{\ln \left( \frac{S_t}{K} \right)+(r+\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}} e^{-\frac{1}{2} u^2}\,du \\
&=S_t \cdot N \left({\frac{\ln \left( \frac{S_t}{K} \right)+(r+\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}}\right)
\end{align*}$$

>$$\begin{align*}
I_2 &=Ke^{-r(T-t)} \cdot \frac{1}{\sqrt{2\pi}} \int_{u_K}^\infty e^{-\frac{1}{2} u^2} \,du \\
&=Ke^{-r(T-t)} \cdot \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{-u_K} e^{-\frac{1}{2} u^2} \,du \\
&=Ke^{-r(T-t)} \cdot \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{-\frac{\ln \left( \frac{K}{S_t} \right)-(r-\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}} e^{-\frac{1}{2} u^2} \,du \\
&=Ke^{-r(T-t)} \cdot \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{\frac{\ln \left( \frac{S_t}{K} \right)+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}} e^{-\frac{1}{2} u^2} \,du \\
&=Ke^{-r(T-t)} \cdot N \left({\frac{\ln \left( \frac{S_t}{K} \right)+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}}\right)
\end{align*}$$

>Answer: The value of the call option is:
$$\begin{align*}
C(S_t,t) = &S_t \cdot N \left({\frac{\ln \left( \frac{S_t}{K} \right)+(r+\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}}\right) \\
&- Ke^{-r(T-t)} \cdot N \left({\frac{\ln \left( \frac{S_t}{K} \right)+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}}\right)
\end{align*}$$


### b. (20 points) PUT {.unnumbered}

Derive the Black-Scholes-Merton formula and then compute the option price.

>Let $\mathcal{P}$ and $\mathcal{Q}$ be the physical and risk neutral measures on $(\omega,\mathcal{F})$ respectively. Let $\{W_t^\mathcal{P}\}_{t \geq 0}$ be the standard Brownian motion on $\mathcal{P}$. For $\{S_t\}_{t \geq 0}$ be the process of asset price, we have:
$$dSt = \mu S_t \,dt + \sigma S_t \,dW_t^\mathcal{P}$$

>With $f(t,x)=e^{-rt}x$ then we can calculate:
$$\begin{align*} 
f_t&=-re^{-rt}x \\
f_x&=e^{-rt} \\
f_{tt}&=r^2e^{-rt}x \\
f_{xx}&=0 \\
f_{tx}&=-re^{-rt}
\end{align*}$$

>Applying Ito-Doeblin formula, we have:
$$\begin{align*}
d(e^{-rt}S_t) &= -re^{-rt}S_t\,dt+e^{-rt}\,dS_t -re^{-rt}\,dt \,dS_t \\
&= -re^{-rt}S_t\,dt+e^{-rt}(\mu S_t \,dt + \sigma S_t \,dW_t^\mathcal{P}) -re^{-rt}\,dt(\mu S_t \,dt + \sigma S_t \,dW_t^\mathcal{P}) \\
&= e^{-rt}S_t[(\mu-r) \,dt+\sigma \,d W_t^{\mathcal{P}}] -\mu re^{-rt}St\,dt^2 + \sigma S_t \,dt\,dW_t^\mathcal{P})\\
&= e^{-rt}S_t[\mu-r \,dt+\sigma (\,d W_t^{\mathcal{Q}}-\theta_t) \,dt] \\
&= e^{-rt}S_t[(\mu-r-\sigma \theta_t) \,dt+\sigma \,d W_t^{\mathcal{Q}} \,dt]
\end{align*}$$

>In order to have the process $\{e^{???rt}S_t\}_{t \geq 0}$ be the martigale process, we choose $\theta_t$ such that:
$$\mu-r-\sigma \theta_t=0 \rightarrow \theta_t=\frac{\mu-r}{\sigma} $$
then $$E^\mathcal{P}[e^{\frac{1}{2} \int_0^T \theta_t^2\,dt}]<\infty$$

>By the Girsanov???s theorem, there is a risk neutral measure $\mathcal{Q}$ defined by the Radon-Nykodym $$E \left[\frac{\,d \mathcal{Q}}{\,d \mathcal{P}} |\mathcal{F}_t\right]=Z_t=e^{-\int_0^t \theta_s \,d W_s^\mathcal{P}-\frac{1}{2} \theta_s^2 \,ds}$$ such that $W_t^\mathcal{Q}=W_t^\mathcal{P}+\int_0^t\theta_s \,ds$  
is the standard Brownian motion under $\mathcal{Q}$.
$$W_t^\mathcal{Q}=W_t^\mathcal{P}+\int_0^t\theta_s \,ds \\
\rightarrow \,dW_t^\mathcal{Q}=\,dW_t^\mathcal{P}+\theta_t\,dt$$

>Since $e^{-rt}S_t$ is a martingale under $\mathcal{Q}$ and $\mathcal{Q}$ is an equivalent martingale measure to $\mathcal{P}$, we can write:
$$\begin{align*}
\,dS_t &= \mu S_t \,dt + \sigma S_t \,dW_t^\mathcal{P} \\
&=\mu S_t \,dt + \sigma S_t (\,dW_t^\mathcal{Q}-\theta_t \,dt) \\
&=\mu S_t \,dt + \sigma S_t (\,dW_t^\mathcal{Q}-\frac{\mu-r}{\sigma} \,dt) \\
&=\left(\mu-\sigma\cdot\frac{\mu-r}{\sigma} \right)S_t \,dt + \sigma S_t \,dW_t^\mathcal{Q} \\
&=rS_t \,dt + \sigma S_t \,dW_t^\mathcal{Q} \\
\end{align*}$$

>Let $Y_t=\ln S_t$ and $f(t,x)=\ln x$, we have:
$$\begin{align*}
f_t&=0 \\
f_x&=\frac{1}{x} \\
f_{tt}&=0 \\
f_{xx}&=-\frac{1}{x^2} \\
f_{tx}&=0 \\
\end{align*}$$

>Applying Ito Doeblin formula, we have:
$$\begin{align*}
\,d(Y_t)&=\frac{1}{S_t} \,dS_t-\frac{1}{2}\frac{1}{S_t^2}\,dS_t^2 \\
&=\frac{1}{S_t} (rS_t \,dt + \sigma S_t \,dW_t^\mathcal{Q})-\frac{1}{2}\frac{1}{S_t^2}(rS_t \,dt + \sigma S_t \,dW_t^\mathcal{Q})^2 \\
&=(r-\frac{1}{2} \cdot \sigma^2)\,dt + \sigma \,dW_t^\mathcal{Q} \\
\,d(\ln S_t)&=(r-\frac{1}{2} \cdot \sigma^2)\,dt + \sigma \,dW_t^\mathcal{Q} \\
 \int_t^T \,d(\ln S_s)&=\int_t^T(r-\frac{1}{2} \cdot \sigma^2)\,ds + \int_t^T\sigma \,dW_s^\mathcal{Q} \\
 \ln \left( \frac{S_T}{S_t} \right)&=(r-\frac{1}{2} \cdot \sigma^2)(T-t)+\sigma(W_T^\mathcal{Q}-W_t^\mathcal{Q}) \\
 S_T&=e^{\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t)+\sigma(W_T^{\mathcal{Q}}-W_t^{\mathcal{Q}})}
\end{align*}$$

>We have
$$\begin{align*}
\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t)+\sigma(W_T^{\mathcal{Q}}-W_t^{\mathcal{Q}}) &\sim \mathcal{N}(\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t),\sigma^2(T-t)) \\
e^{\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t)+\sigma(W_T^{\mathcal{Q}}-W_t^{\mathcal{Q}})} &\sim \log\mathcal{N}(\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t),\sigma^2(T-t)) \\
 (S_T|S_t) &\sim \log\mathcal{N}(\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t),\sigma^2(T-t)) \\
\end{align*}$$

>The probability density function of $(S_T|S_t)$ is
$$f_{S_T|S_t}(x)=\frac{1}{\sigma x\sqrt{2\pi(T-t)}}e^{-\frac{1}{2} \frac{(\ln x-(\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t)))^2}{\sigma^2(T-t)}} $$

>From Feyman-Kac formula we have:
$$P(S_t,t)=e^{-r(T-t)} \mathbb{E}^\mathcal{Q}[max(K-S_T,0)|\mathcal{F}_t] $$

>Applying the moment generating function, we have:
$$\begin{align*} 
P(S_t,t)&=e^{-r(T-t)}\int_{0}^\infty \max(K-x,0) f_{S_T|S_t}(x) \,dx \\
&=e^{-r(T-t)}\int_{-\infty}^\infty \max(K-x,0) f_{S_T|S_t}(x) \,dx \\
&=e^{-r(T-t)}\int_{-\infty}^K (K-x) \frac{1}{\sigma x\sqrt{2\pi}\sqrt{(T-t)}}e^{-\frac{1}{2} \frac{(\ln x-(\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t)))^2}{\sigma^2(T-t)}} \,dx \\
&=e^{-r(T-t)}\int_{-\infty}^K (K-x) \frac{1}{\sigma x\sqrt{2\pi}\sqrt{(T-t)}}e^{-\frac{1}{2} \frac{(\ln x-(\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t)))^2}{\sigma^2(T-t)}} \,dx \\
&=\frac{e^{-r(T-t)}}{\sigma \sqrt{2\pi}\sqrt{(T-t)}} \int_{-\infty}^K (K-x)e^{-\frac{1}{2} \frac{(\ln x-\ln S_t -(r-\frac{1}{2} \cdot \sigma^2)(T-t)))^2}{\sigma^2(T-t)}} \frac{1}{x}\,dx
\end{align*}$$

>Let 
$u=\frac{\ln x-\ln S_t -(r-\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}$, we have
$$\begin{align*}
\ln \left( \frac{x}{S_t} \right)&=\sigma u\sqrt{T-t}+(r-\frac{1}{2} \cdot \sigma^2)(T-t) \\
x&=S_te^{\sigma u\sqrt{T-t}+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}
\end{align*}$$ 

>
$$\begin{align*}
\,du&=\frac{1}{\sigma x\sqrt{T-t}}\,dx \\
\sigma\sqrt{T-t}\,du&=\frac{1}{x}\,dx
\end{align*}$$

>
$$\begin{align*}
u_K&=\frac{\ln K-\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}} \\
&=\frac{\ln \left( \frac{K}{S_t} \right)+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}
\end{align*}$$

>The value of the put option becomes:
$$\begin{align*}
P(S_t,t)&=\frac{e^{-r(T-t)}}{\sigma \sqrt{2\pi} \sqrt{T-t}} \int_{-\infty}^K (K-x)e^{-\frac{1}{2} \frac{(\ln x-\ln S_t -(r-\frac{1}{2} \cdot \sigma^2)(T-t)))^2}{\sigma^2(T-t)}} \frac{1}{x}\,dx \\
&=\frac{e^{-r(T-t)}}{\sigma \sqrt{2\pi}\sqrt{T-t}} \int_{-\infty}^{u_K} (-S_te^{\sigma u\sqrt{T-t}+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}+K)e^{-\frac{1}{2} u^2} \sigma\sqrt{T-t}\,du \\
&=\frac{e^{-r(T-t)}\sqrt{T-t}}{\sqrt{2\pi}\sqrt{T-t}} \int_{-\infty}^{u_K} (-S_te^{\sigma u\sqrt{T-t}+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}e^{-\frac{1}{2} u^2}+Ke^{-\frac{1}{2} u^2}) \,du \\
&=\frac{e^{-r(T-t)}}{\sqrt{2\pi}} \int_{-\infty}^{u_K} (-S_te^{\sigma u\sqrt{T-t}+(r-\frac{1}{2} \cdot \sigma^2)(T-t)-\frac{1}{2} u^2}+Ke^{-\frac{1}{2} u^2}) \,du \\
&=\frac{1}{\sqrt{2\pi}} \int_{-\infty}^{u_K} -S_te^{\sigma u\sqrt{T-t}-\frac{1}{2} \cdot \sigma^2(T-t)-\frac{1}{2} u^2}\,du \\
&+\frac{e^{-r(T-t)}}{\sqrt{2\pi}} \int_{-\infty}^{u_K} Ke^{-\frac{1}{2} u^2} \,du \\
&= I_1 \\
&+I_2
\end{align*}$$

>
$$\begin{align*}
I_1&=\frac{1}{\sqrt{2\pi}} \int_{-\infty}^{u_K} -S_te^{\sigma u\sqrt{T-t}-\frac{1}{2} \cdot \sigma^2(T-t)-\frac{1}{2} u^2}\,du \\
&=-S_t \cdot \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{u_K} e^{-\frac{1}{2} (u-\sigma\sqrt{T-t})^2}\,du \\
&=-S_t \cdot \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{u_K} e^{-\frac{1}{2} (u-\sigma\sqrt{T-t})^2}\,d(u-\sigma\sqrt{T-t}) \\
&=-S_t \cdot \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{u_K-\sigma\sqrt{T-t}} e^{-\frac{1}{2} u^2}\,du \\
&=-S_t\cdot \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{\frac{\ln \left( \frac{K}{S_t} \right)-(r-\frac{1}{2} \cdot \sigma^2)(T-t)-\sigma^2(T-t)}{\sigma\sqrt{T-t}}} e^{-\frac{1}{2} u^2}\,du \\
&=-S_t\cdot \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{-\frac{\ln \left( \frac{S_t}{K} \right)+(r+\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}} e^{-\frac{1}{2} u^2}\,du \\
&=-S_t \cdot N \left({-\frac{\ln \left( \frac{S_t}{K} \right)+(r+\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}}\right)  \\
\end{align*}$$

>
$$\begin{align*}
I_2&=Ke^{-r(T-t)} \cdot \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{u_K} e^{-\frac{1}{2} u^2} \,du \\
&=Ke^{-r(T-t)} \cdot \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{\frac{\ln \left( \frac{K}{S_t} \right)-(r-\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}} e^{-\frac{1}{2} u^2} \,du \\
&=Ke^{-r(T-t)} \cdot \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{-\left(\frac{\ln \left( \frac{S_t}{K} \right)+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}\right)} e^{-\frac{1}{2} u^2} \,du \\
&=Ke^{-r(T-t)} \cdot N \left(-{\frac{\ln \left( \frac{S_t}{K} \right)+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}}\right)
\end{align*}$$

>Therefore, the Black-Scholes-Merton formula is:
$$\begin{align*}
P(S_t,t) &= -S_t \cdot N \left({-\frac{\ln \left( \frac{S_t}{K} \right)+(r+\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}}\right)  \\
&+ Ke^{-r(T-t)} \cdot N \left(-{\frac{\ln \left( \frac{S_t}{K} \right)+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}}\right)\\
\end{align*}$$

>$$\begin{align*}
S_t &=12 \\ K&=15 \\ r&=0.06 \\ \sigma &=0.4 \\ T&=2 \\ t&=0.5 
\end{align*}$$

>We calculate $d_1$ and $d_2$
$$\begin{align*}
d_1&=\frac{\ln\left(\frac{S_t}{K} \right)+(r+\frac{1}{2}\sigma^2)(T-t)}{\sigma \sqrt{T-t}} \\ 
&=\frac{\ln\left(\frac{12}{15} \right)+(0.06+\frac{1}{2} \cdot 0.4^2) \cdot (2-0.5)}{0.4 \cdot \sqrt{(2-0.5)}} \\ 
&=-0.0268 \\
d_2&=\frac{\ln\left(\frac{S_t}{K} \right)+(r-\frac{1}{2}\sigma^2)(T-t)}{\sigma \sqrt{T-t}} \\ 
&=\frac{\ln\left(\frac{12}{15} \right)+(0.06-\frac{1}{2} \cdot 0.4^2) \cdot (2-0.5)}{0.4 \cdot \sqrt{(2-0.5)}} \\ 
&=-0.5167 \\
\end{align*}$$

>Answer: The value of the put option is:
$$\begin{align*}
P&= K \cdot N(-d_2) \cdot e^{-r(T-t)} - S_t \cdot N(-d_1) \\
&=15 \cdot N(0.5167) \cdot e^{-0.06 \cdot (2-0.5)} - 12 \cdot N(0.0268) \\
&=3.43
\end{align*}$$


```r
BS_call <- function (S0,K,T,r,sigma){
  d1 <- (log(S0/K)+(r+0.5*sigma^2)*T)/(sigma*sqrt(T)) 
  d2 <- d1- sigma*sqrt(T)
  opt.val <- -S0*pnorm(-d1)+K*exp(-r*T)*pnorm(-d2) 
  return(opt.val)
}

BS_call(S0=12,K=15,T=2-0.5,r=0.06,sigma=0.4)
```

```
#> [1] 3.431205
```

### c. (15 points)  {.unnumbered}

Compute the option price using the 3-step CRR binomial tree.

>
$$\begin{align*}
u&=e^{\sigma \sqrt{\frac{T-t}{N}}} \\
&=e^{0.4\sqrt{\frac{2-0.5}{3}}} \\
&=1.33 \\
d&=e^{-\sigma \sqrt{\frac{T-t}{N}}} \\
&=e^{-0.4\sqrt{\frac{2-0.5}{3}}} \\
&=0.75 \\
p &= \frac{e^{r \cdot \frac{T-t}{N}}-d}{u-d} \\
&= \frac{e^{0.06 \cdot \frac{2-0.5}{3}}-0.75}{1.33-0.75} \\
&=0.48 \\
q &= \frac{u-e^{r \cdot \frac{T-t}{N}}}{u-d} \\
&= \frac{1.33-e^{0.06 \cdot \frac{2-0.5}{3}}}{1.33-0.75} \\
&=0.52 \\
\end{align*}$$

>
$$\begin{align*}
V_{03}&=\max(-S_0 \cdot u^3+K,0) \\
&=\max(-12 \cdot 1.33^3+15,0) \\
&= 0 \\
V_{13}&=\max(-S_0 \cdot u^2 d+K,0) \\
&=\max(-12 \cdot 1.33^2 \cdot 0.75+15,0) \\
&= 0 \\
V_{23}&=\max(-S_0 \cdot u d^2+K,0) \\
&=\max(-12 \cdot 1.33 \cdot 0.75^2+15,0) \\
&= 5.96 \\
V_{33}&=\max(-S_0 \cdot d^3+K,0) \\
&=\max(-12 \cdot 0.75^3+15,0) \\
&= 9.86
\end{align*}$$

>$$\begin{align*}
V_{02}&=e^{-r \cdot \frac{T-t}{N}}(V_{03} \cdot p + V_{13} \cdot q) \\
&=e^{-0.06 \cdot \frac{2-0.5}{3}}(0 \cdot 0.48 + 0 \cdot 0.52) \\
&=0 \\
V_{12}&=e^{-r \cdot \frac{T-t}{N}}(V_{13} \cdot p + V_{23} \cdot q) \\
&=e^{-0.06 \cdot \frac{2-0.5}{3}}(0 \cdot 0.48 + 5.96 \cdot 0.52) \\
&=2.99 \\
V_{22}&=e^{-r \cdot \frac{T-t}{N}}(V_{23} \cdot p + V_{33} \cdot q) \\
&=e^{-0.06 \cdot \frac{2-0.5}{3}}(5.96 \cdot 0.48 + 9.86 \cdot 0.52) \\
&=7.74 \\
\end{align*}$$

>$$\begin{align*}
V_{01}&=e^{-r \cdot \frac{T-t}{N}}(V_{02} \cdot p + V_{12} \cdot q) \\
&=e^{-0.06 \cdot \frac{2-0.5}{3}}(0 \cdot 0.48 + 2.99 \cdot 0.52) \\
&=1.50 \\
V_{11}&=e^{-r \cdot \frac{T-t}{N}}(V_{12} \cdot p + V_{22} \cdot q) \\
&=e^{-0.06 \cdot \frac{2-0.5}{3}}(2.99 \cdot 0.48 + 7.74 \cdot 0.52) \\
&=5.29 \\
\end{align*}$$

>$$\begin{align*}
V_{0}&=e^{-r \cdot \frac{T-t}{N}}(V_{01} \cdot p + V_{11} \cdot q) \\
&=e^{-0.06 \cdot \frac{2-0.5}{3}}(1.50 \cdot 0.48 + 5.29 \cdot 0.52) \\
&=3.355
\end{align*}$$

>Answer: The fair price of the option is $3.355$


```r
European_call_binomial=function(T, t,r, X,N,S0,sigma){ 
  delta_t=(T-t)/N
  u = exp(sigma*sqrt(delta_t))
  d = exp(-sigma*sqrt(delta_t))
  p = (exp(r * delta_t) - d)/(u - d) ### probability of up move  {.unnumbered}
  Df = exp(-r * (T-t)) ### discounting factor {.unnumbered}
  Ce=0;
  for (i in 1:(N+1)){
    Ce =Ce+choose(N,i-1)*p^{i-1}*(1-p)^{N+1-i}*max(X-S0*u^{i-1}*d^{N-i+1},0)
    }
return(Df*Ce)
}
European_call_binomial(T=2, t=0.5,r=0.06, X=15,N=3,S0=12,sigma=0.4)
```

```
#> [1] 3.355349
```

## Question 5' (0 points) {.unnumbered}

### a. (0 points) {.unnumbered}

A gambler starts with \$3 dollars. On each play a fair coin is tossed and the gambler wins \$1 if heads occurs, or loses \$1 if tails occurs. The gambler stops when he reaches \$8 or loses all his money. Find the probability that the gambler will eventually lose.

>Let $R_n$ denote the total fortune after the $n^{th}$ gamble.
While the game proceeds, $\{R_n : n \geq 0\}$ forms a simple random walk:
$$R_n = R_0+ \Delta_1 +\Delta_2+ ?? ?? ?? + \Delta_n $$
where $\{\Delta n\}$ forms an i.i.d. random variables as $P(\Delta = 1) = p$, $P(\Delta = ???1) = q$, $p+q=1$, and represents the earnings on the succesive gambles.

>Let $P_3$ denote the probability that the gambler wins when $R_0 = 3$, we need to find $1-P_3$.
<ul>
<li>If $\Delta_1 = 1$, then the gambler???s total fortune
increases to $R_1 = 3+1$ and so the gambler will now win with probability $P_{4}$.</li>
<li>If $\Delta_1 = ???1$, then the gambler???s fortune decreases to $R_1 = 3 ??? 1$ and so the gambler will now win with probability $P_{2}$.</li>
</ul>
$$\begin{align*}
P_3&= pP_{4}+qP_{2} \\ 
pP_{3}+qP_{3}&= pP_{4}+qP_{2} \\ 
p(P_4-P_3)&=q(P_3-P_2) \\ 
P_4-P_3&=\frac{q}{p}(P_3-P_2) \\ 
&=\left( \frac{q}{p} \right)^2(P_2-P_1) \\
&=\left( \frac{q}{p} \right)^3 (P_1-P_0) \\
&=\left( \frac{q}{p} \right)^3 (P_1)
\end{align*}$$

>By induction, we can prove $P_{k+1}-P_k= \left( \frac{q}{p} \right)^k P_1$, which implies the following recursive sequence:
$$\begin{align*}
P_2-P_1&=\left( \frac{q}{p} \right)(P_1-P_0)=\left( \frac{q}{p} \right) P_1\\
P_3-P_2&=\left( \frac{q}{p} \right)(P_2-P_1)=\left( \frac{q}{p} \right)^2 P_1 \\
...\\
P_{i+1}-P_i&= \left( \frac{q}{p} \right)^i P_1
\end{align*}$$

>Adding all the above sequence and noticing that $P_N=1$ shall yield:

>$$\begin{align*}
P_{i+1}-P_1&=  \sum_{k=1}^{i} (P_{k+1}-P_k) \\
&=\sum_{k=1}^{i} \left( \frac{q}{p} \right)^k P_1 \\ 
\end{align*}$$

>
$$\begin{align*}
>P_{i+1}&=P_1+\sum_{k=1}^{i} \left( \frac{q}{p} \right)^k P_1 \\ 
&= P_1\sum_{k=0}^{i} \left( \frac{q}{p} \right)^k \\ 
&=P_1\sum_{k=0}^{i} \left( \frac{0.5}{0.5} \right)^k  \\
&=P_1\sum_{k=0}^{i} \left( 1 \right)^k  \\
&=P_1(i+1) \\
\rightarrow P_N&=P_1\cdot N \\
\rightarrow P_1&=\frac{1}{N} \\
\rightarrow P_3&=3 P_1 \\
&=3\cdot \frac{1}{N} \\ 
&=\frac{3}{N} \\
&=\frac{3}{8} \\
\rightarrow 1-P_3&=\frac{5}{8} \\
\end{align*}$$

>Answer: The probability that the gambler will eventually lose is 62.5\%.

### b. (0 points) {.unnumbered}

A gambler starts with $3 dollars. On each play an unfair coin is tossed and
the gambler wins \$1 if heads occurs, with probability 0.6, or loses \$1 if
tails occurs, with probability 0.4. The gambler stops when he reaches $8
or loses all his money. Find the probability that the gambler will eventually
lose.

>Let $R_n$ denote the total fortune after the $n^{th}$ gamble.
While the game proceeds, $\{R_n : n \geq 0\}$ forms a simple random walk:
$$R_n = R_0+ \Delta_1 +\Delta_2+ ?? ?? ?? + \Delta_n $$
where $\{\Delta n\}$ forms an i.i.d. random variables as $P(\Delta = 1) = p$, $P(\Delta = ???1) = q$, $p+q=1$, and represents the earnings on the succesive gambles.


>Let $P_3$ denote the probability that the gambler wins when $R_0 = 3$, we need to find $1-P_3$.
<ul>
<li>If $\Delta_1 = 1$, then the gambler???s total fortune
increases to $R_1 = 3+1$ and so the gambler will now win with probability $P_{4}$.</li>
<li>If $\Delta_1 = ???1$, then the gambler???s fortune decreases to $R_1 = 3 ??? 1$ and so the gambler will now win with probability $P_{2}$.</li>
</ul>
$$\begin{align*}
P_3&= pP_{4}+qP_{2} \\ 
pP_{3}+qP_{3}&= pP_{4}+qP_{2} \\ 
p(P_4-P_3)&=q(P_3-P_2) \\ 
P_4-P_3&=\frac{q}{p}(P_3-P_2) \\ 
&=\left( \frac{q}{p} \right)^2(P_2-P_1) \\
&=\left( \frac{q}{p} \right)^3 (P_1-P_0) \\
&=\left( \frac{q}{p} \right)^3 (P_1)
\end{align*}$$

>By induction, we can prove $P_{k+1}-P_k= \left( \frac{q}{p} \right)^k P_1$, which implies the following recursive sequence:
$$\begin{align*}
P_2-P_1&=\left( \frac{q}{p} \right)(P_1-P_0)=\left( \frac{q}{p} \right) P_1\\
P_3-P_2&=\left( \frac{q}{p} \right)(P_2-P_1)=\left( \frac{q}{p} \right)^2 P_1 \\
...\\
P_{i+1}-P_i&= \left( \frac{q}{p} \right)^i P_1
\end{align*}$$

>Adding all the above sequence and noticing that $P_N=1$ shall yield:

>$$\begin{align*}
P_{i+1}-P_1&=  \sum_{k=1}^{i} (P_{k+1}-P_k) \\
&=\sum_{k=1}^{i} \left( \frac{q}{p} \right)^k P_1 \\ 
\end{align*}$$

>$$\begin{align*}
>P_{i+1}&=P_1+\sum_{k=1}^{i} \left( \frac{q}{p} \right)^k P_1 \\ 
&= P_1\sum_{k=0}^{i} \left( \frac{q}{p} \right)^k \\ 
&=P_1 \cdot \frac{1-(\frac{q}{p})^{i+1}}{1-\frac{q}{p}} &(1) \\
\end{align*}$$

>$$\begin{align*}
P_N&=P_1 \cdot \frac{1-(\frac{q}{p})^N}{1-\frac{q}{p}} \\
P_1&= \frac{1-\frac{q}{p}}{1-(\frac{q}{p})^N}&(2) \\
\end{align*}$$

>$$\begin{align*}
(1),(2)\rightarrow P_{i+1}&=\frac{1-(\frac{q}{p})^{i+1}}{1-(\frac{q}{p})^N} \\ 
P_{3}&=\frac{1-(\frac{q}{p})^{3}}{1-(\frac{q}{p})^8} \\
1-P_{3}&=1-\frac{1-(\frac{q}{p})^{3}}{1-(\frac{q}{p})^8}=0.2677
\end{align*}$$

>Answer: The probability that the gambler will eventually lose is 26.77\%.

## Question 6' (0 points) {.unnumbered}

For each toss of a unfair coin, you will win $\$2$ if it lands up heads and lose $\$1$ if it lands up tails. The probability of landing up heads is 0.3 and the probability of landing up tails is 0.7. Suppose that you start the game with $\$0$ and denote $M_k$ is the amount of money you obtain after k tosses.  

- Should you play the game?  

>While the game proceeds, $(M_k)_{k\in \mathbb{N}}$ forms a simple random walk:
$$M_k = M_0+ \Delta_1 +\Delta_2+ ?? ?? ?? + \Delta_k $$
where $M_0=0$, $\{\Delta n\}$ forms an i.i.d. random variables as $P(\Delta = 2) = 0.3$, $P(\Delta = ???1) = 0.7$, and represents the earnings on the succesive games.

>Using the law of total expectation, the expected accumulated money after every play is the expected money for each toss either the coin lands up head or tail.
\begin{align*} 
E[\Delta_i] &=E[\Delta_i|\Delta_i=2]P(\Delta_i=2)+E[\Delta_i|\Delta_i=-1]P(\Delta_i=-1) \\
&=0.3(2)+0.7(-1) \\
&=-0.1
\end{align*}

>$$\begin{align*} 
E[M_k] &= E[M_0+ \Delta_1 +\Delta_2+ ?? ?? ?? + \Delta_k] = M_0+ E[\Delta_1] +E[\Delta_2]+ ?? ?? ?? + E[\Delta_k] \\
&= M_0 -0.1 -0.1 ... -0.1 \\
&=0 - 0.1k \\
&< M_0
\end{align*}$$

>Answer: The game should not be played.

## Question 7' (0 points) {.unnumbered}

For each toss of a fair coin, you will win $\$1$ if it lands up heads and lose $\$1$ if it lands up tails. Suppose that you start the game with $\$0$ and denote $M_k$ is the amount of money you obtain after k tosses. Then $(M_k)_{k\in\mathbb{N}}$ is a random walk.  

- Compute the probability of winning after playing the game 9 times.  

> We need to find the probability that $M_9$ or the amount of money after nine
plays greater than 0

>$$\begin{align*}
P(M_9>0)&=P(5H4T)+P(6H3T)+P(7H2T)+P(8H1T)+P(9H0T) \\
&= \sum_{k=5}^{9} \binom{9}{k}p^k(1-p)^{9-k} \\
&=0.5
\end{align*}$$

> Answer: The probability of winning after playing the game 9 times is  50\%

- Compute the probability of winning after playing the game 10 times.

> We need to find the probability that $M_{10}$ or the amount of money after ten
plays greater than 0

>$$\begin{align*}
P(M_{10}>0)&=P(6H4T)+P(7H3T)+P(8H2T)+P(9H1T)+P(10H0T) \\
&= \sum_{k=6}^{10} \binom{10}{k}p^k(1-p)^{10-k} \\
&=0.3769
\end{align*}$$

> Answer: The probability of winning after playing the game 10 times is  37.69\%

- Is this game fair, i.e., the chance of winning a fair game is equal for all players?

>Answer: This is a fair game when the number of k tosses is odd (9 tosses) and this is not a fair game when the number of k tosses is even (10 tosses).

## Question 8' (0 points) {.unnumbered}

Prove the following random processes are martingale:

1. Brownian motion $(B_t)$ is a martingale process.

Let $\{\mathcal{F}_t\}_{t \geq 0}$ be the natural filtration of Brownian motion $\{ B_t \}_{t \geq0}$. For all $0 \leq s <t$, we have:

>$$\begin{align*}
E[|B_t|]&= \int_{-\infty}^{\infty}|x|\frac{1}{\sqrt{2 \pi t}}e^{\frac{-x^2}{2t}}\,dx  \\
&=\int_{-\infty}^{0}|x|\frac{1}{\sqrt{2 \pi t}}e^{\frac{-x^2}{2t}}\,dx+\int_{0}^{\infty}|x|\frac{1}{\sqrt{2 \pi t}}e^{\frac{-x^2}{2t}}\,dx \\
&=\frac{1}{\sqrt{2 \pi t}}\int_{0}^{\infty}xe^{\frac{-x^2}{2t}}\,dx+\frac{1}{\sqrt{2 \pi t}}\int_{0}^{\infty}xe^{\frac{-x^2}{2t}}\,dx \\
&=\sqrt{\frac{2}{{\pi t}}}\int_{0}^{\infty}xe^{\frac{-x^2}{2t}}\,dx \\
&=\frac{1}{\sqrt{2 \pi t}}\int_{0}^{\infty}e^{\frac{-x^2}{2t}}\,dx^2 \\
&=-\sqrt{\frac{2t}{\pi}}e^{\frac{-u}{2t}}\Biggr|_{0}^{\infty} \\
&=\sqrt{\frac{2t}{\pi}} < \infty
\end{align*}$$

>$$\begin{align*}
E[B_t|\mathcal{F}_s]&=E[(B_t-B_s)+B_s|\mathcal{F}_s] \\
&=E[(B_t-B_s)|\mathcal{F}_s]+E[B_s|\mathcal{F}_s] \\ 
&=0+B_s \\
&=B_s 
\end{align*}$$

2. Let $Y_t = B_t^2 ??? t, \forall t \geq 0$. Show that $(Y_t)_{t \geq 0}$ is a martingale with respect to Brownian motion.

>Let $\{\mathcal{F}_t\}_{t \geq 0}$ be the natural filtration of $\{ Y_t=B_t^2-t \}_{t \geq0}$. For all $0 \leq s <t$, we have:

>$$\begin{align*}
E[|Y_t|]&=E[|B_t^2-t|] \\
&\leq E[B_t^2+t] \\
&=E[B_t^2]+t \\
&=t < \infty
\end{align*}$$

>$$\begin{align*}
E[Y_t|\mathcal{F}_s]&=E[B_t^2-t|\mathcal{F}_s] \\
&=E[(B_t-B_s+B_s)^2|\mathcal{F}_s]-t \\
&=E[(B_t-B_s)^2+2B_s(B_t-B_s)+B_s^2|\mathcal{F}_s]-t \\ 
&=E[(B_t-B_s)^2|\mathcal{F}_s]+E[2B_s(B_t-B_s)|\mathcal{F}_s]+E[B_s^2|\mathcal{F}_s]-t \\
&=E[(B_t-B_s)^2]+0+B_s^2-t \\
&=E[(B_t-B_s)^2]-E[B_t-B_s]^2+B_s^2-t \\
&=Var[B_t-B_s]+B_s^2-t \\
&=t-s+B_s^2-t \\
&=B_s^2-s
\end{align*}$$

3. $Z_t = e^{\sigma B_t ??? \frac{1}{2} \sigma^2 t}$ ($\sigma$ is a positive constant) is a martingale with respect to the standard Brownian motion.

>Let $\{\mathcal{F}_t\}_{t \geq 0}$ be the natural filtration of $\{ Z_t=e^{\sigma B_t ??? \frac{1}{2} \sigma^2 t}\}$. For all $0 \leq s <t$, since $B_t-B_s \sim N(0,t-s)$ we have:

>$$\sigma B_t ??? \frac{1}{2} \sigma^2 t \sim \mathcal{N} \left(-\frac{1}{2}\sigma^2t,\sigma^2t \right)$$

>
$$\begin{align*}
E[|Z_t|]&=E[|e^{\sigma B_t ??? \frac{1}{2} \sigma^2 t}|] \\
&=E[e^{\sigma B_t ??? \frac{1}{2} \sigma^2 t}] \\
&=E[Z_t] \\
&=e^{\mu_{Z_t} + \frac{1}{2}\sigma_{Z_t}^2} \\
&=e^{-\frac{1}{2}\sigma^2t + \frac{1}{2}\sigma^2t} \\
&=1
\end{align*}$$

>$$E[e^{tX}]=e^{\mu t+\frac{1}{2}\sigma^2 t^2} \rightarrow E[e^{\sigma (B_t-B_s)}]=e^{\frac{1}{2}\sigma^2 (t-s)}$$

>
$$\begin{align*}
E[Z_t|\mathcal{F}_s]&=E[e^{\sigma B_t ??? \frac{1}{2} \sigma^2 t}|\mathcal{F}_s] \\
&=E[e^{\sigma (B_t-B_s+B_s) ??? \frac{1}{2} \sigma^2 (t-s+s)}|\mathcal{F}_s] \\ 
&=e^{\sigma B_s-\frac{1}{2}\sigma^2 s} \cdot E[e^{\sigma (B_t-B_s)} \cdot e^ {??? \frac{1}{2} \sigma^2 (t-s)}|\mathcal{F}_s] \\
&=e^{\sigma B_s-\frac{1}{2}\sigma^2 s} \cdot E[e^{\sigma (B_t-B_s)}|\mathcal{F}_s] \cdot E[e^ {??? \frac{1}{2} \sigma^2 (t-s)}|\mathcal{F}_s] \\
&=e^{\sigma B_s-\frac{1}{2}\sigma^2 s} \cdot e^ {\frac{1}{2} \sigma^2 (t-s)} \cdot e^ {??? \frac{1}{2} \sigma^2 (t-s)} \\
&=e^{\sigma B_s-\frac{1}{2}\sigma^2 s}  \\
&= Z_s
\end{align*}$$

## Question 9' (0 points) {.unnumbered}

Let $(W_t)_{t???0}$ be a Brownian motion on the filtered probability space $(\omega,\mathcal{F},\mathcal{F}_t)_{t???0}$).
Compute $\,dX_t$ in terms of $\,dW_t$ and $\,dt$.

a. $X_t=t Y_t^4$ with $\,d Y_t = -6 Y_t \,dt + 2Y_t \,dW_t$

>Let $f(t,x)=tx^4$ then
$$\begin{align*}
&f_t =x^4 \\ 
&f_{tt} =0 \\
&f_x =4tx^3 \\ 
&f_{xx} =12tx^2 \\
&f_{tx} =4x^3 \\
\end{align*}$$

>Applying Ito formula to $X_t=f(t,Y_t)$, we have:

>
$$\begin{align*}
\,d(X_t) &= \,d(t Y_t^4) \\
&= Y_t^4 \,dt +  4tY_t^3 \,d Y_t + \frac{1}{2} \cdot 12tY_t^2 \,d Y_t^2 + 4Y_t^3 \,dt \,dY_t \\
&= Y_t^4 \,dt + 4tY_t^3 (-6 Y_t \,dt + 2Y_t \,dW_t) + \frac{1}{2} \cdot 12tY_t^2 (-6 Y_t \,dt + 2Y_t \,dW_t)^2 + 4Y_t^3 \,dt (-6 Y_t \,dt + 2Y_t \,dW_t) \\
&= Y_t^4 \,dt - 24tY_t^4 \,dt + 8Y_t^4 \,dW_t + \frac{1}{2} \cdot 12tY_t^2 \cdot 4Y_t^2 \,dt \\
&= Y_t^4 \,dt + 8Y_t^4 \,dW_t
\end{align*}$$

>Answer: $\,d(X_t)=Y_t^4 \,dt + 8Y_t^4 \,dW_t$

b. $X_t=\ln \frac{t}{Y_t}$ with $\,d Y_t = \frac{1}{2Y_t} \,dt + \,dW_t$

>Let $f(t,x)=\ln \frac{t}{x}$ then
$$\begin{align*}
&f_t =\frac{1}{t} \\ 
&f_{tt} =-\frac{1}{t^2} \\
&f_x =-\frac{1}{x} \\ 
&f_{xx} =\frac{1}{x^2} \\
&f_{tx} =0 \\
\end{align*}$$

>Applying Ito formula to $X_t=f(t,Y_t)$, we have:

>
$$\begin{align*}
\,d(X_t) &= \,d(\ln \frac{t}{Y_t}) \\
&= \frac{1}{t} \,dt -\frac{1}{Y_t} \,dY_t + \frac{1}{2} \frac{1}{Y_t^2} \,dY_t ^2 \\
&= \frac{1}{t} \,dt -\frac{1}{Y_t} \left(\frac{1}{2Y_t} \,dt + \,dW_t \right) + \frac{1}{2} \cdot \frac{1}{Y_t^2} \left(\frac{1}{2Y_t} \,dt + \,dW_t\right)^2 \\
&= \frac{1}{t} \,dt -\frac{1}{Y_t} \cdot\frac{1}{2Y_t} \,dt -\frac{1}{Y_t}\,dW_t +\frac{1}{2} \cdot \frac{1}{Y_t^2}\,dt \\
&= \frac{1}{t}  \,dt -\frac{1}{Y_t}\,dW_t 
\end{align*}$$

>Answer: $\frac{1}{t}  \,dt -\frac{1}{Y_t}\,dW_t$

## Question 10' (0 points) {.unnumbered}

Suppose you buy a European call option written on asset paying no
dividend, with strike price $K = 50$, $T = 0.5$ (year), $r = 0.05$. If it is sure
that the asset price at expiry is $S_T = 60$. How much should be the fair
value of the option?

>The price of the call option at time T: 
$$C(S,T)=max(S_T???K;0)=max(60???50;0)=10$$

>The fair value of the option is the present value of the option at time 0: $PV=\frac{FV}{e^{r \cdot \Delta t}}=\frac{10}{e^{0.05 \cdot 0.5}}=9.753$

>Answer: The fair value of the option should be $9.753$.
