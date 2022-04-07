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

a. (10 points) What is the probability that the asset price after 3 years from now (i.e $S_3$) will be less than 13?

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

b. (10 points) What is the expected price after 3 years from now?

>$$\begin{align*}
W_3 &\sim \mathcal{N}(0,3) \\
11.8+ 0.3W_3 &\sim \mathcal{N}(11.8,0.3^2 \cdot3) \\
(S_3|S_0 = 10) &\sim \mathcal{N}(11.8,0.27)
\end{align*}$$

>Answer: The expected price after 3 years from now is 11.8.

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
\rightarrow e^{\ln X_2-1906.2+\int_2^5(3t^2-2t)\,dW_t} &\sim \ln\mathcal{N} \left(\ln X_2-1906.2,3896.4 \right) \\
\rightarrow X_5 &\sim \ln\mathcal{N} \left(\ln X_2-1906.2,3896.4 \right) \\
\end{align*}$$

>$$\begin{align*}
(X_5|X_2=3) &\sim \ln\mathcal{N} \left(\ln 3-1906.2,3896.4 \right) \\
\end{align*}$$

>$$\begin{align*}
E[X_4|X_2=3]&=e^{\ln 3-1906.2+ \frac{1}{2} \cdot 3896.4} \\
&\approx e^{43} \\
Var(X_4|X_2=3)&=\left(e^{3896.4}-1\right)e^{\left(2(\ln 3-1906.2)+3896.4 \right)}  \\
\end{align*}$$

>Answer: The mean and variance of $(X_4|X_2=3)$ are $e^{43}$ and $\left(e^{3896.4}-1\right)e^{\left(2(\ln 3-1906.2)+3896.4 \right)}$

## Question 4 (50 points) {.unnumbered}

Suppose the stochastic process of the asset price $S_t$ follows a geometric
Brownian motion:
$$\,d S_t = 0.2 S_t \,dt + 0.3 S_t \,dW_t^\mathcal{P}$$
where $W_t^P$
is a standard Brownian motion on the real world probability
space, denoted by $(\omega, \mathcal{F},\mathcal{P})$. A European put option written on the stock
with parameters: exercise price $K = 15$, maturity time $T=2$, $t=0.5$ (year), the
risk-free interest rate is $r = 0.06$, $S_t=12$.

a. (15 points) Let $\widetilde W_t = W_t + \theta t$, with $\theta$ being a constant is an adapted process with respect to the filtration $()\mathcal{F}_t)_{t \geq 0}$. Find $\theta$ such that the discounted $(e^{−0.07t}S_t)_{t \ge 0}$ is a martingale process with respect to $\widetilde W_t$.

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

b. (20 points) Derive the Black-Scholes-Merton formula and then compute the option price.

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

>In order to have the process $\{e^{−rt}S_t\}_{t \geq 0}$ be the martigale process, we choose $\theta_t$ such that:
$$\mu-r-\sigma \theta_t=0 \rightarrow \theta_t=\frac{\mu-r}{\sigma} $$
then $$E^\mathcal{P}[e^{\frac{1}{2} \int_0^T \theta_t^2\,dt}]<\infty$$

>By the Girsanov’s theorem, there is a risk neutral measure $\mathcal{Q}$ defined by the Radon-Nykodym $$E \left[\frac{\,d \mathcal{Q}}{\,d \mathcal{P}} |\mathcal{F}_t\right]=Z_t=e^{-\int_0^t \theta_s \,d W_s^\mathcal{P}-\frac{1}{2} \theta_s^2 \,ds}$$ such that $W_t^\mathcal{Q}=W_t^\mathcal{P}+\int_0^t\theta_s \,ds$  
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
 ln \left( \frac{S_T}{S_t} \right)&=(r-\frac{1}{2} \cdot \sigma^2)(T-t)+\sigma(W_T^\mathcal{Q}-W_t^\mathcal{Q}) \\
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
$$ P(S_t,t)=e^{-r(T-t)} \mathbb{E}^\mathcal{Q}[max(K-S_T,0)|\mathcal{F}_t] $$

>Applying the moment generating function, we have:

$$\begin{align*} 
P(S_t,t)&=e^{-r(T-t)}\int_{-\infty}^\infty \max(K-x,0) f_{S_T|S_t}(x) \,dx \\
&=e^{-r(T-t)}\int_{-\infty}^K (K-x) \frac{1}{\sigma x\sqrt{2\pi}\sqrt{(T-t)}}e^{-\frac{1}{2} \frac{(\ln x-(\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t)))^2}{\sigma^2(T-t)}} \,dx \\
&=e^{-r(T-t)}\int_{-\infty}^K (K-x) \frac{1}{\sigma x\sqrt{2\pi}\sqrt{(T-t)}}e^{-\frac{1}{2} \frac{(\ln x-(\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t)))^2}{\sigma^2(T-t)}} \,dx \\
&=\frac{e^{-r(T-t)}}{\sigma \sqrt{2\pi}\sqrt{(T-t)}} \int_{-\infty}^K (K-x)e^{-\frac{1}{2} \frac{(\ln x-\ln S_t -(r-\frac{1}{2} \cdot \sigma^2)(T-t)))^2}{\sigma^2(T-t)}} \frac{1}{x}\,dx
\end{align*}$$

>Let $u=\frac{\ln x-\ln S_t -(r-\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}$, we have
$$\begin{align*}
\ln \left( \frac{x}{S_t} \right)&=\sigma u\sqrt{T-t}+(r-\frac{1}{2} \cdot \sigma^2)(T-t) \\
x&=S_te^{\sigma u\sqrt{T-t}+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}
\end{align*}$$ 

>$$\begin{align*}
\,du&=\frac{1}{\sigma x\sqrt{T-t}}\,dx \\
\sigma\sqrt{T-t}\,du&=\frac{1}{x}\,dx
\end{align*}$$

>$$\begin{align*}
u_K&=\frac{\ln K-\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}} \\
&=\frac{\ln \left( \frac{K}{S_t} \right)+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}
\end{align*}$$

>The value of the put option becomes:
$$\begin{align*}
P(S_t,t)&=\frac{e^{-r(T-t)}}{\sigma \sqrt{2\pi} \sqrt{T-t}} \int_{-\infty}^K (K-x)e^{-\frac{1}{2} \frac{(\ln x-\ln S_t -(r-\frac{1}{2} \cdot \sigma^2)(T-t)))^2}{\sigma^2(T-t)}} \frac{1}{x}\,dx \\
&=\frac{e^{-r(T-t)}}{\sigma \sqrt{2\pi}\sqrt{T-t}} \int_{-\infty}^{u_K} (-S_te^{\sigma u\sqrt{T-t}+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}+K)e^{-\frac{1}{2} u^2} \sigma\sqrt{T-t}\,du \\
&=\frac{e^{-r(T-t)}\sqrt{T-t}}{\sqrt{2\pi}\sqrt{T-t}} \int_{-\infty}^{u_K} (-S_te^{\sigma u\sqrt{T-t}+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}e^{-\frac{1}{2} u^2}+Ke^{-\frac{1}{2} u^2}) \,du \\
&=\frac{e^{-r(T-t)}}{\sqrt{2\pi}} \int_{-\infty}^{u_K} (-S_te^{\sigma u\sqrt{T-t}+(r-\frac{1}{2} \cdot \sigma^2)(T-t)-\frac{1}{2} u^2}+Ke^{-\frac{1}{2} u^2}) \,du \\
&=\frac{e^{-r(T-t)}}{\sqrt{2\pi}} \int_{-\infty}^{u_K} -S_te^{\sigma u\sqrt{T-t}+(r-\frac{1}{2} \cdot \sigma^2)(T-t)-\frac{1}{2} u^2}\,du \\
&+\frac{e^{-r(T-t)}}{\sqrt{2\pi}} \int_{-\infty}^{u_K} Ke^{-\frac{1}{2} u^2} \,du \\
&= I_1 \\
&+I_2
\end{align*}$$

>$$\begin{align*}
I_1&=-S_t \cdot \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{u_K} e^{-\frac{1}{2} u^2+\sigma u\sqrt{T-t}-r(T-t)+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}\,du \\
&=-S_t \cdot \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{u_K} e^{-\frac{1}{2} (u-\sigma\sqrt{T-t})^2}\,du \\
&=-S_t \cdot \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{u_K} e^{-\frac{1}{2} (u-\sigma\sqrt{T-t})^2}\,d(u-\sigma\sqrt{T-t}) \\
&=-S_t \cdot \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{u_K-\sigma\sqrt{T-t}} e^{-\frac{1}{2} u^2}\,du \\
&=-S_t\cdot \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{\frac{\ln \left( \frac{K}{S_t} \right)-(r-\frac{1}{2} \cdot \sigma^2)(T-t)-\sigma^2(T-t)}{\sigma\sqrt{T-t}}} e^{-\frac{1}{2} u^2}\,du \\
&=-S_t\cdot \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{-\frac{\ln \left( \frac{S_t}{K} \right)+(r+\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}} e^{-\frac{1}{2} u^2}\,du \\
&=-S_t \cdot N \left({-\frac{\ln \left( \frac{S_t}{K} \right)+(r+\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}}\right)  \\
\end{align*}$$

>$\begin{align*}
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

>The value of the put option is:
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

c. (15 points) Compute the option price using the 3-step CRR binomial tree.

>
$$\begin{align*}
u&=e^{\sigma \sqrt{\frac{T-t}{N}}} \\
&=e^{0.4\sqrt{\frac{2-0.5}{3}}} \\
&=1.33 \\
d&=e^{-\sigma \sqrt{\frac{T-t}{N}}} \\
&=e^{-0.4\sqrt{\frac{2-0.5}{3}}} \\
&=0.75 \\
p &= \frac{e^{r \cdot \frac{T-t}{N}-d}}{u-d} \\
&= \frac{e^{0.06 \cdot \frac{2-0.5}{3}-0.75}}{1.33-0.75} \\
&=0.48 \\
q &= \frac{u-e^{r \cdot \frac{T-t}{N}}}{u-d} \\
&= \frac{1.33-e^{0.06 \cdot \frac{2-0.5}{3}}}{1.33-0.75} \\
&=0.52 \\
\end{align*}$$

>
$$\begin{align*}
V_{03}&=\max(-12 \cdot 1.33^3+15,0) \\
&=\max(-12 \cdot 1.33^3+15,0) \\
&= 0 \\
V_{13}&=\max(-S_0 \cdot u^2 d+15,0) \\
&=\max(-12 \cdot 1.33^2 \cdot 0.75+15,0) \\
&= 0 \\
V_{23}&=\max(-S_0 \cdot u d^2+15,0) \\
&=\max(-12 \cdot 1.33 \cdot 0.75^2+15,0) \\
&= 5.96 \\
V_{33}&=\max(-S_0 \cdot d^3+15,0) \\
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
  p = (exp(r * delta_t) - d)/(u - d) ### probability of up move 
  Df = exp(-r * (T-t)) ### discounting factor
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

# Sem 2 2020-2021 

## Question 1 (20 points) {.unnumbered}

Let $\{(W_t)_t \geq 0\}$ be a standard Brownian motion on the probability space $(\Omega,\mathcal{F},\mathcal{P})$. Suppose that the process $(X_t)_t \geq 0$ is governed by the equation:
$\,d X_t =2X_t\,dt+1X_t\,dW_t$.
Find the distribution, the mean and variance of the random variable
$(X_3|X_1 = 10)$.

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
dY_t&= \frac{1}{X_t}(2X_t\,dt+X_t\,dW_t) - \frac{1}{2}\frac{1}{X_t^2}(2X_t\,dt+X_t\,dW_t)^2 \\
dY_t&= \frac{1}{X_t} \cdot 2X_t\,dt+ \frac{1}{X_t} \cdot X_t\,dW_t - \frac{1}{2}\frac{1}{X_t^2} \cdot X_t^2\,dW_t^2 \\
dY_t&=   2\,dt+  \,dW_t - \frac{1}{2}  \,dt \\
dY_t&=   \left(2-\frac{1}{2} \right)\,dt+  \,dW_t \\
\rightarrow \int_1^3 dY_t&=   \int_1^3 \left(2-\frac{1}{2} \right)\,dt+  \int_1^3 \,dW_t \\
\rightarrow  Y_3-Y_1  &= 3 +  \int_1^3\,dW_t \\
\rightarrow  \ln X_3-\ln X_1  &= 3 +  W_3-W_1 \\
\rightarrow  X_3  &= e^{\ln X_1+3 +  W_3-W_1} \\
\end{align*}$$

>
$$\begin{align*}
W_3-W_1 &\sim \mathcal{N} \left(0,2 \right) \\
\ln X_1+3 +  W_3-W_1 &\sim \mathcal{N} \left(\ln X_1+3,2 \right) \\
e^{\ln X_1+3 +  W_3-W_1} &\sim \log\mathcal{N} \left(\ln X_1+3,2 \right) \\
(X_3|X_1 = 10) &\sim \log\mathcal{N} \left(\ln 10+3,2 \right) \\
\end{align*}$$

>
$$\begin{align*}
E[X_3|X_1 = 10]&=e^{\ln 10+3+ \frac{1}{2} \cdot 2} \\
&\approx e^{6.3} \\
Var(X_3|X_1=3)&=\left(e^{2^2}-1\right)e^{2(\ln 10+3)+2}  \\
\end{align*}$$

>Answer: The distribution, mean and variance of $(X_3|X_1=10)$ are $\log\mathcal{N} \left(\ln 10+3,2 \right)$, $e^{6.3}$ and $\left(e^{2^2}-1\right)e^{2(\ln 10+3)+2}$, respectively.

## Question 2 (25 points) {.unnumbered}

Consider the asset price process $(S_t)_{t \geq 0}$ follows an equation:
$$ \,dS_t = (0.2 + t^3)\,dt + 0.3 \,dW_t $$
where $(W_t)_{t \geq 0}$ is a standard Brownian motion on a filtered probability space $(\omega,\mathcal{F},(\mathcal{F}_t)_{t \geq 0}$. Suppose the asset price is now 10.

a. (15 points) What is the probability that the asset price after 4 years from now (i.e $S_4$) will be less than 14?

>
$$\begin{align*}
\,dS_t &= (0.2 + t^3)\,dt + 0.3 \,dW_t \\
\int_0^4 \,dS_t &= \int_0^4 (0.2 + t^3)\,dt + \int_0^4 0.3 \,dW_t \\
S_4 - S_0 &= 64.8 + 0.3 (W_4-W_0) \\
S_4 &= 74.8 + 0.3W_4 \\
\end{align*}$$

>
$$\begin{align*}
\mathcal{P}(S_4 < 14) &= \mathcal{P}(74.8 + 0.3W_4 < 14) \\
&= \mathcal{P} \left(W_4 < \frac{14-74.8}{0.3}\right) \\
&= \mathcal{P} \left(\mathcal{Z} < \frac{14-74.8}{0.3\sqrt{4}}\right) \\
&= \Phi(-101.3) \\
&= 0
\end{align*}$$

>Answer: The probability that the asset price after 3 years from now (i.e $S_3$) will be less than 13 is $0\%$.

b. (10 points) What is the expected price after 4 years from now?

>$$\begin{align*}
W_4 &\sim \mathcal{N}(0,4) \\
74.8+ 0.3W_4 &\sim \mathcal{N}(74.8,0.3^2 \cdot4) \\
(S_4|S_0) &\sim \mathcal{N}(74.8,0.36)
\end{align*}$$

>Answer: The expected price after 4 years from now is 74.8.

## Question 3 (55 points) {.unnumbered}

Suppose the stochastic process of the asset price $S_t$ follows a geometric
Brownian motion:
$$\,d S_t = 0.1 S_t \,dt + 0.3 S_t \,dW_t^\mathcal{P}$$
where $W_t^P$
is a standard Brownian motion on the real world probability
space, denoted by $(\omega, \mathcal{F},\mathcal{P})$. A European put option written on the stock
with parameters: exercise price $K = 10$, maturity time $T=1$, $t=0.3$ (year), the
risk-free interest rate is $r = 0.1$, $S_t=10$.

a. (10 points) Let $\widetilde W_t = W_t + \theta t$, with $\theta$ being a constant is an adapted process with respect to the filtration $()\mathcal{F}_t)_{t \geq 0}$. Find $\theta$ such that the discounted $(e^{−0.07t}S_t)_{t \ge 0}$ is a martingale process with respect to $\widetilde W_t$.

>Let $\mathcal{P}$ and $\mathcal{Q}$ be the physical and risk neutral measures on $(\omega,\mathcal{F})$ respectively. Let $\{W_t^\mathcal{P}\}_{t \geq 0}$ be the standard Brownian motion on $\mathcal{P}$. For $\{S_t\}_{t \geq 0}$ be the process of asset price, we have:
$$dSt = 0.1S_t \,dt + 0.3 S_t \,dW_t^\mathcal{P}$$

>With $f(t,x)=e^{-0.1t}x$ then we can calculate:
$$\begin{align*} 
f_t&=-0.1e^{-0.1t}x \\
f_x&=e^{-0.1t} \\
f_{tt}&=0.1^2e^{-0.1t}x \\
f_{xx}&=0 \\
f_{tx}&=-0.1e^{-0.1t}
\end{align*}$$

>Applying Ito-Doeblin formula, we have:
$$\begin{align*}
d(e^{-0.1t}S_t) &= -0.1e^{-0.1t}S_t\,dt+e^{-0.1t}\,dS_t -0.1e^{-0.1t}\,dt \,dS_t \\
&= -0.1e^{-0.1t}S_t\,dt+e^{-0.1t}(0.1 S_t \,dt + 0.3 S_t \,dW_t^\mathcal{P}) \\
&-0.1e^{-0.1t}\,dt(0.1 S_t \,dt + 0.3 S_t \,dW_t^\mathcal{P}) \\
&= e^{-0.1t}S_t[(0.1-0.1) \,dt+0.3 \,d W_t^{\mathcal{P}}] \\
&-0.1 \cdot 0.1 e^{-0.1t}St\,dt^2 - 0.1 \cdot 0.3 S_t \,dt\,dW_t^\mathcal{P})\\
&= e^{-0.1t}S_t[(0.1-0.1) \,dt+0.3 (\,d W_t^{\mathcal{Q}}-\theta_t) \,dt] \\
&= e^{-0.1t}S_t[(0.1-0.1-0.3 \theta_t) \,dt+0.3 \,d W_t^{\mathcal{Q}} \,dt]
\end{align*}$$

>In order to have the process $\{e^{-0.1t}S_t\}_{t \geq 0}$ be the martigale process, we choose $\theta_t$ such that:
$$-0.1+0.1-0.3 \theta_t=0 \rightarrow \theta_t=\frac{-0.1+0.1}{0.3}=0 $$
then $$E^\mathcal{P}[e^{\frac{1}{2} \int_0^T \theta_t^2\,dt}]<\infty$$

b. (20 points) Derive the Black-Scholes-Merton formula and then compute the option price.

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

>In order to have the process $\{e^{−rt}S_t\}_{t \geq 0}$ be the martigale process, we choose $\theta_t$ such that:
$$\mu-r-\sigma \theta_t=0 \rightarrow \theta_t=\frac{\mu-r}{\sigma} $$
then $$E^\mathcal{P}[e^{\frac{1}{2} \int_0^T \theta_t^2\,dt}]<\infty$$

>By the Girsanov’s theorem, there is a risk neutral measure $\mathcal{Q}$ defined by the Radon-Nykodym $$E \left[\frac{\,d \mathcal{Q}}{\,d \mathcal{P}} |\mathcal{F}_t\right]=Z_t=e^{-\int_0^t \theta_s \,d W_s^\mathcal{P}-\frac{1}{2} \theta_s^2 \,ds}$$ such that $W_t^\mathcal{Q}=W_t^\mathcal{P}+\int_0^t\theta_s \,ds$  
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
 ln \left( \frac{S_T}{S_t} \right)&=(r-\frac{1}{2} \cdot \sigma^2)(T-t)+\sigma(W_T^\mathcal{Q}-W_t^\mathcal{Q}) \\
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
$$ P(S_t,t)=e^{-r(T-t)} \mathbb{E}^\mathcal{Q}[max(K-S_T,0)|\mathcal{F}_t] $$

>Applying the moment generating function, we have:
$$\begin{align*} 
P(S_t,t)&=e^{-r(T-t)}\int_{-\infty}^\infty \max(K-x,0) f_{S_T|S_t}(x) \,dx \\
&=e^{-r(T-t)}\int_{-\infty}^K (K-x) \frac{1}{\sigma x\sqrt{2\pi}\sqrt{(T-t)}}e^{-\frac{1}{2} \frac{(\ln x-(\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t)))^2}{\sigma^2(T-t)}} \,dx \\
&=e^{-r(T-t)}\int_{-\infty}^K (K-x) \frac{1}{\sigma x\sqrt{2\pi}\sqrt{(T-t)}}e^{-\frac{1}{2} \frac{(\ln x-(\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t)))^2}{\sigma^2(T-t)}} \,dx \\
&=\frac{e^{-r(T-t)}}{\sigma \sqrt{2\pi}\sqrt{(T-t)}} \int_{-\infty}^K (K-x)e^{-\frac{1}{2} \frac{(\ln x-\ln S_t -(r-\frac{1}{2} \cdot \sigma^2)(T-t)))^2}{\sigma^2(T-t)}} \frac{1}{x}\,dx
\end{align*}$$

>Let $u=\frac{\ln x-\ln S_t -(r-\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}$, we have
$$\begin{align*}
\ln \left( \frac{x}{S_t} \right)&=\sigma u\sqrt{T-t}+(r-\frac{1}{2} \cdot \sigma^2)(T-t) \\
x&=S_te^{\sigma u\sqrt{T-t}+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}
\end{align*}$$ 

>$$\begin{align*}
\,du&=\frac{1}{\sigma x\sqrt{T-t}}\,dx \\
\sigma\sqrt{T-t}\,du&=\frac{1}{x}\,dx
\end{align*}$$

>$$\begin{align*}
u_K&=\frac{\ln K-\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}} \\
&=\frac{\ln \left( \frac{K}{S_t} \right)+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}
\end{align*}$$

>The value of the put option becomes:
$$\begin{align*}
P(S_t,t)&=\frac{e^{-r(T-t)}}{\sigma \sqrt{2\pi} \sqrt{T-t}} \int_{-\infty}^K (K-x)e^{-\frac{1}{2} \frac{(\ln x-\ln S_t -(r-\frac{1}{2} \cdot \sigma^2)(T-t)))^2}{\sigma^2(T-t)}} \frac{1}{x}\,dx \\
&=\frac{e^{-r(T-t)}}{\sigma \sqrt{2\pi}\sqrt{T-t}} \int_{-\infty}^{u_K} (-S_te^{\sigma u\sqrt{T-t}+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}+K)e^{-\frac{1}{2} u^2} \sigma\sqrt{T-t}\,du \\
&=\frac{e^{-r(T-t)}\sqrt{T-t}}{\sqrt{2\pi}\sqrt{T-t}} \int_{-\infty}^{u_K} (-S_te^{\sigma u\sqrt{T-t}+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}e^{-\frac{1}{2} u^2}+Ke^{-\frac{1}{2} u^2}) \,du \\
&=\frac{e^{-r(T-t)}}{\sqrt{2\pi}} \int_{-\infty}^{u_K} (-S_te^{\sigma u\sqrt{T-t}+(r-\frac{1}{2} \cdot \sigma^2)(T-t)-\frac{1}{2} u^2}+Ke^{-\frac{1}{2} u^2}) \,du \\
&=\frac{e^{-r(T-t)}}{\sqrt{2\pi}} \int_{-\infty}^{u_K} -S_te^{\sigma u\sqrt{T-t}+(r-\frac{1}{2} \cdot \sigma^2)(T-t)-\frac{1}{2} u^2}\,du \\
&+\frac{e^{-r(T-t)}}{\sqrt{2\pi}} \int_{-\infty}^{u_K} Ke^{-\frac{1}{2} u^2} \,du \\
&= I_1 \\
&+I_2
\end{align*}$$

>$$\begin{align*}
I_1&=-S_t \cdot \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{u_K} e^{-\frac{1}{2} u^2+\sigma u\sqrt{T-t}-r(T-t)+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}\,du \\
&=-S_t \cdot \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{u_K} e^{-\frac{1}{2} (u-\sigma\sqrt{T-t})^2}\,du \\
&=-S_t \cdot \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{u_K} e^{-\frac{1}{2} (u-\sigma\sqrt{T-t})^2}\,d(u-\sigma\sqrt{T-t}) \\
&=-S_t \cdot \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{u_K-\sigma\sqrt{T-t}} e^{-\frac{1}{2} u^2}\,du \\
&=-S_t\cdot \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{\frac{\ln \left( \frac{K}{S_t} \right)-(r-\frac{1}{2} \cdot \sigma^2)(T-t)-\sigma^2(T-t)}{\sigma\sqrt{T-t}}} e^{-\frac{1}{2} u^2}\,du \\
&=-S_t\cdot \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{-\frac{\ln \left( \frac{S_t}{K} \right)+(r+\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}} e^{-\frac{1}{2} u^2}\,du \\
&=-S_t \cdot N \left({-\frac{\ln \left( \frac{S_t}{K} \right)+(r+\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}}\right)  \\
\end{align*}$$

>$$\begin{align*}
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

>
$$\begin{align*}
S_t &=10 \\ K&=10 \\ r&=0.1 \\ \sigma &=0.3 \\ T&=1 \\ t&=0.3
\end{align*}$$

>We calculate $d_1$ and $d_2$
$$\begin{align*}
d_1&=\frac{\ln\left(\frac{S_t}{K} \right)+(r+\frac{1}{2}\sigma^2)(T-t)}{\sigma \sqrt{T-t}} \\ 
&=\frac{\ln\left(\frac{10}{10} \right)+(0.1+\frac{1}{2} \cdot 0.3^2) \cdot (1-0.3)}{0.3 \cdot \sqrt{(1-0.3)}} \\ 
&=0.4044 \\
d_2&=\frac{\ln\left(\frac{S_t}{K} \right)+(r-\frac{1}{2}\sigma^2)(T-t)}{\sigma \sqrt{T-t}} \\ 
&=\frac{\ln\left(\frac{10}{10} \right)+(0.1-\frac{1}{2} \cdot 0.3^2) \cdot (1-0.3)}{0.3 \cdot \sqrt{(1-0.3)}} \\ 
&=0.1534 \\
\end{align*}$$

>The value of the put option is:
$$\begin{align*}
P&= K \cdot N(-d_2) \cdot e^{-r(T-t)} - S_t \cdot N(-d_1) \\
&=10 \cdot N(-0.1534) \cdot e^{-0.1 \cdot (1-0.3)} - 10 \cdot N(-0.4044) \\
&=0.6640
\end{align*}$$


```r
BS_call <- function (S0,K,T,r,sigma){
  d1 <- (log(S0/K)+(r+0.5*sigma^2)*T)/(sigma*sqrt(T)) 
  d2 <- d1- sigma*sqrt(T)
  opt.val <- -S0*pnorm(-d1)+K*exp(-r*T)*pnorm(-d2) 
  return(opt.val)
}

BS_call(S0=10,K=10,T=1-0.3,r=0.1,sigma=0.3)
```

```
#> [1] 0.6639948
```

c. (10 points) Compute the option price using the 3-step CRR binomial tree.

>
$$\begin{align*}
u&=e^{\sigma \sqrt{\frac{T-t}{N}}} \\
&=e^{0.3\sqrt{\frac{1-0.3}{3}}} \\
&=1.1559 \\
d&=e^{-\sigma \sqrt{\frac{T-t}{N}}} \\
&=e^{-0.3\sqrt{\frac{1-0.3}{3}}} \\
&=0.8651 \\
p &= \frac{e^{r \cdot \frac{T-t}{N}-d}}{u-d} \\
&= \frac{e^{0.1 \cdot \frac{1-0.3}{3}-0.8651}}{1.1559-0.8651} \\
&=0.5450 \\
q &= \frac{u-e^{r \cdot \frac{T-t}{N}}}{u-d} \\
&= \frac{1.1559-e^{0.1 \cdot \frac{1-0.3}{3}}}{1.1559-0.8651} \\
&=0.4550 \\
\end{align*}$$

>
$$\begin{align*}
V_{03}&=\max(-10 \cdot 1.1559^3+10,0) \\
&=\max(-10 \cdot 1.1559^3+10,0) \\
&= 0 \\
V_{13}&=\max(-S_0 \cdot u^2 d+10,0) \\
&=\max(-10 \cdot 1.1559^2 \cdot 0.8651+10,0) \\
&= 0 \\
V_{23}&=\max(-S_0 \cdot u d^2+10,0) \\
&=\max(-10 \cdot 1.1559 \cdot 0.8651^2+10,0) \\
&= 0.27 \\
V_{33}&=\max(-S_0 \cdot d^3+10,0) \\
&=\max(-10 \cdot 0.8651^3+10,0) \\
&= 1.34
\end{align*}$$

>$$\begin{align*}
V_{02}&=e^{-r \cdot \frac{T-t}{N}}(V_{03} \cdot p + V_{13} \cdot q) \\
&=e^{-0.1 \cdot \frac{1-0.3}{3}}(0 \cdot 0.5450 + 0 \cdot 0.4550) \\
&=0 \\
V_{10}&=e^{-r \cdot \frac{T-t}{N}}(V_{13} \cdot p + V_{23} \cdot q) \\
&=e^{-0.1 \cdot \frac{1-0.3}{3}}(0 \cdot 0.5450 + 0.27 \cdot 0.4550) \\
&=0.60 \\
V_{22}&=e^{-r \cdot \frac{T-t}{N}}(V_{23} \cdot p + V_{33} \cdot q) \\
&=e^{-0.1 \cdot \frac{1-0.3}{3}}(0.27 \cdot 0.5450 + 1.34 \cdot 0.4550) \\
&=2.29 \\
\end{align*}$$

>$$\begin{align*}
V_{01}&=e^{-r \cdot \frac{T-t}{N}}(V_{02} \cdot p + V_{10} \cdot q) \\
&=e^{-0.1 \cdot \frac{1-0.3}{3}}(0 \cdot 0.5450 + 2.99 \cdot 0.4550) \\
&=0.27 \\
V_{11}&=e^{-r \cdot \frac{T-t}{N}}(V_{10} \cdot p + V_{22} \cdot q) \\
&=e^{-0.1 \cdot \frac{1-0.3}{3}}(2.99 \cdot 0.5450 + 7.74 \cdot 0.4550) \\
&=1.34 \\
\end{align*}$$

>$$\begin{align*}
V_{0}&=e^{-r \cdot \frac{T-t}{N}}(V_{01} \cdot p + V_{11} \cdot q) \\
&=e^{-0.1 \cdot \frac{1-0.3}{3}}(0.60 \cdot 0.5450 + 2.29 \cdot 0.4550) \\
&=0.74
\end{align*}$$

>Answer: The fair price of the option is $0.74$


```r
European_call_binomial=function(T, t,r, X,N,S0,sigma){ 
  delta_t=(T-t)/N
  u = exp(sigma*sqrt(delta_t))
  d = exp(-sigma*sqrt(delta_t))
  p = (exp(r * delta_t) - d)/(u - d) ### probability of up move 
  Df = exp(-r * (T-t)) ### discounting factor
  Ce=0;
  for (i in 1:(N+1)){
    Ce =Ce+choose(N,i-1)*p^{i-1}*(1-p)^{N+1-i}*max(X-S0*u^{i-1}*d^{N-i+1},0)
    }
return(Df*Ce)
}
European_call_binomial(T=1, t=0.3,r=0.1, X=10,N=3,S0=10,sigma=0.3)
```

```
#> [1] 0.7353961
```
