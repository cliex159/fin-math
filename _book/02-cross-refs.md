# (PART) Risk Neutral {.unnumbered}

# Risk Neutral Pricing

## Fair value of the option

### Slide 18 {.unnumbered}

Suppose you buy a European call option written on asset paying no
dividend, with strike price $K = 50$, $T = 0.5$ (year), $r = 0.05$. If it is sure
that the asset price at expiry is $S_T = 60$. How much should be the fair
value of the option?

>The price of the call option at time T: 
$$C(S,T)=max(S_T−K;0)=max(60−50;0)=10$$

>The fair value of the option is the present value of the option at time 0: $PV=\frac{FV}{e^{r \cdot \Delta t}}=\frac{10}{e^{0.05 \cdot 0.5}}=9.753$

## Geometric Brownian

### Slide 19 {.unnumbered}

Suppose the stock price process follows a geometric Brownian motion:
$$\,d S_t = 0.1 S_t \,dt + 0.4 S_t \,dW_t$$

where $W_t$ is the standard Brownian motion on the real world probability
space, denoted by $(\omega,\mathcal{F},\mathcal{P})$.

a. Using Ito’s formula to compute $d(e^{−0.02t}S_t)$.

>$$\begin{align*}
&f(t,x)=e^{−0.02t}x \\
&f_t=−0.02e^{−0.02t}x \\ 
&f_x=e^{−0.02t} \\
&f_{tt}=0.02^2e^{−0.02t}x \\
&f_{xx}=0 \\
&f_{tx}=−0.02e^{−0.02t} \\
\end{align*}$$

>$$\begin{align*}
d(e^{−0.02t} S_t)&=−0.02e^{−0.02t}S_t \,dt + e^{−0.02t} \,dS_t + 0.02^2e^{−0.02t}S_t\,dt^2 + 0 \,dS_t^2  −0.02e^{−0.02t}\,dt \,dS_t \\
&=−0.02e^{−0.02t}S_t \,dt + e^{−0.02t} (0.1 S_t \,dt + 0.4 S_t \,dW_t) -0.02e^{-0.02t}\,dt (0.1 S_t \,dt + 0.4 S_t \,dW_t) \\
&=−0.02e^{−0.02t}S_t \,dt + 0.1 e^{−0.02t}  S_t \,dt + 0.4 e^{−0.02t}S_t \,dW_t -0.02 \cdot 0.1e^{-0.02t}S_t\,dt^2    -0.02 \cdot 0.4e^{-0.02t}S_t\,dt\,dW_t  \\
&=e^{-0.02t}S_t(0.08 e^{−0.02t}S_t \,dt + 0.4 e^{−0.02t} S_t \,dW_t)
\end{align*}$$

>Answer: $d(e^{−0.02t} S_t)=0.08 e^{−0.02t}S_t \,dt + 0.4 e^{−0.02t} S_t \,dW_t$

b. Let $\widetilde W_t = W_t + \theta t$, with $\theta$ is a constant. Find $\theta$ such that the discounted $(e^{−0.02t}S_t)_{t \ge 0}$ is a martingale process with respect to $\widetilde W_t$.

>$$\begin{align*}
d(e^{−0.02t} S_t)&=0.08 e^{−0.02t}S_t \,dt + 0.4 e^{−0.02t} S_t \,dW_t \\
&=0.08 e^{−0.02t}S_t \,dt + 0.4 e^{−0.02t} S_t (\,d \widetilde W_t - \theta \,d t) \\
&=(0.08  - 0.4 \theta)e^{−0.02t}S_t \,dt + 0.4 e^{−0.02t} S_t \,d \widetilde W_t
\end{align*}$$

>$\{e^{−0.02t} S_t \}_{t \geq 0}$ is martingale under $\mathcal{Q}$ measure then:
$$0.08  - 0.4 \theta=0 \rightarrow \theta = 0.2 $$

>Answer: $\theta = 0.2$

c. Find the expression of $\,d S_t$in terms of $\,dt$ and $\,d \widetilde W_t$.

>With $\theta = 0.2$, we have
$$\begin{align*}
\,d S_t &= 0.1 S_t \,dt + 0.4 S_t \,dW_t \\
&= 0.1 S_t \,dt + 0.4 (S_t \,d \widetilde W_t - 0.2 \,dt) \\
&= 0.02 S_t \,dt + 0.4 S_t \,d \widetilde W_t
\end{align*}$$

>Answer: $\,d S_t=0.02 S_t \,dt + 0.4 S_t \,d \widetilde W_t$

### Slide 19' {.unnumbered}

Suppose the stock price process follows a geometric Brownian motion:
$$\,d S_t = 0.05 S_t \,dt + 0.3 S_t \,dW_t$$

where $W_t$ is the standard Brownian motion on the real world probability
space, denoted by $(\omega,\mathcal{F},\mathcal{P})$.

a. Using Ito’s formula to compute $d(e^{−0.02t}S_t)$.

>$$\begin{align*}
&f(t,x)=e^{−0.02t}x \\
&f_t=−0.02e^{−0.02t}x \\ 
&f_x=e^{−0.02t} \\
&f_{tt}=0.02^2e^{−0.02t}x \\
&f_{xx}=0 \\
&f_{tx}=−0.02e^{−0.02t} \\
\end{align*}$$

>$$\begin{align*}
d(e^{−0.02t} S_t)&=−0.02e^{−0.02t}S_t \,dt + e^{−0.02t} \,dS_t + 0.02^2e^{−0.02t}S_t\,dt^2 + 0 \,dS_t^2  −0.02e^{−0.02t}\,dt \,dS_t \\
&=−0.02e^{−0.02t}S_t \,dt + e^{−0.02t} (0.05 S_t \,dt + 0.3 S_t \,dW_t) -0.02e^{-0.02t}\,dt (0.05 S_t \,dt + 0.3 S_t \,dW_t) \\
&=−0.02e^{−0.02t}S_t \,dt + 0.05 e^{−0.02t}  S_t \,dt + 0.3 e^{−0.02t}S_t \,dW_t -0.02 \cdot 0.05e^{-0.02t}S_t\,dt^2    -0.02 \cdot 0.3e^{-0.02t}S_t\,dt\,dW_t  \\
&=e^{-0.02t}S_t(0.03 e^{−0.02t}S_t \,dt + 0.3 e^{−0.02t} S_t \,dW_t)
\end{align*}$$

>Answer: $d(e^{−0.02t} S_t)=0.08 e^{−0.02t}S_t \,dt + 0.4 e^{−0.02t} S_t \,dW_t$

b. Let $\widetilde W_t = W_t + \theta t$, with $\theta$ is a constant. Find $\theta$ such that the discounted $(e^{−0.02t}S_t)_{t \ge 0}$ is a martingale process with respect to $\widetilde W_t$.

>$$\begin{align*}
d(e^{−0.02t} S_t)&=0.08 e^{−0.02t}S_t \,dt + 0.4 e^{−0.02t} S_t \,dW_t \\
&=0.08 e^{−0.02t}S_t \,dt + 0.4 e^{−0.02t} S_t (\,d \widetilde W_t - \theta \,d t) \\
&=(0.08  - 0.4 \theta)e^{−0.02t}S_t \,dt + 0.4 e^{−0.02t} S_t \,d \widetilde W_t
\end{align*}$$

>$\{e^{−0.02t} S_t \}_{t \geq 0}$ is martingale under $\mathcal{Q}$ measure then:
$$0.08  - 0.4 \theta=0 \rightarrow \theta = 0.2 $$

>Answer: $\theta = 0.2$

c. Find the expression of $\,d S_t$in terms of $\,dt$ and $\,d \widetilde W_t$.

>With $\theta = 0.2$, we have
$$\begin{align*}
\,d S_t &= 0.1 S_t \,dt + 0.4 S_t \,dW_t \\
&= 0.1 S_t \,dt + 0.4 (S_t \,d \widetilde W_t - 0.2 \,dt) \\
&= 0.02 S_t \,dt + 0.4 S_t \,d \widetilde W_t
\end{align*}$$

>Answer: $\,d S_t=0.02 S_t \,dt + 0.4 S_t \,d \widetilde W_t$

## Arithmetic Brownian

### Slide 20 {.unnumbered}

Suppose the stock price process follows an arithmetic Brownian motion:$\,d S_t = 0.1 \,dt + 0.4 \,d W_t$,
where $W_t$ is the standard Brownian motion on the real world probability space, denoted by $(\omega, \mathcal{F},\mathcal{P})$.

a. Using Ito’s formula to compute $\,d (e^{−0.02t} S_t)$.

>$$\begin{align*}
&f(t,x)=e^{−0.02t}x \\
&f_t=−0.02e^{−0.02t}x \\ 
&f_x=e^{−0.02t} \\
&f_{tt}=0.02^2e^{−0.02t} \\
&f_{xx}=0 \\
\end{align*}$$

>$$\begin{align*}
d(e^{−0.02t} S_t)&=(−0.02e^{−0.02t}S_t )\,dt + (e^{−0.02t}) \,dS_t + (0.02^2e^{−0.02t})\,dt^2 + (0) \,dS_t^2 \\
&=(−0.02e^{−0.02t}S_t )\,dt + (e^{−0.02t}) (0.1 \,dt + 0.4 \,dW_t) \\
&= e^{−0.02t}(-0.02 S_t +0.1) \,dt + 0.4 e^{−0.02t} \,dW_t
\end{align*}$$

>Answer: $d(e^{−0.02t} S_t)=e^{−0.02t}(-0.02 S_t +0.1) \,dt + 0.4 e^{−0.02t} \,dW_t$

b. Let $\widehat W_t = W_t + \int_0^t \theta_s \,d s$, with $(\theta_t)_{t \geq 0}$ is an adapted process with
respect to the filter $\mathcal{F}$. Find $\theta$ such that the discounted $(e^{−0.02t} S_t)_{t \geq 0}$ is a
martingale process with respect to $\widetilde W_t$.

>$$\begin{align*}
d(e^{−0.02t} S_t)&=e^{−0.02t}(-0.02 S_t +0.1) \,dt + 0.4 e^{−0.02t} \,dW_t \\
&=e^{−0.02t}(-0.02 S_t +0.1) \,dt + 0.4 e^{−0.02t} (\,d \widetilde W_t - \theta \,d t) \\
&=(-0.02 S_t +0.1  - 0.4 \theta)e^{−0.02t} \,dt + 0.4 e^{−0.02t} \,d \widetilde W_t
\end{align*}$$

>$\{e^{−0.02t} S_t \}_{t \geq 0}$ is martingale under $\mathcal{Q}$ measure then:
$$-0.02 S_t +0.1  - 0.4 \theta=0 \rightarrow \theta = -0.05 S_t+0.25 $$

>Answer: $\theta = -0.05 S_t+0.25$

c. Find the expression of $\,d S_t$in terms of $\,dt$ and $\,d \widetilde W_t$.

>With $\theta = -0.05 S_t+0.25$, we have
$$\begin{align*}
\,d S_t &= 0.1 S_t \,dt + 0.4 S_t \,dW_t \\
&= 0.1 S_t \,dt + 0.4 (S_t \,d \widetilde W_t - (-0.05 S_t+0.25) \,dt) \\
&=  (0.1 S_t+0.4(0.05S_t-0.25))\,dt + 0.4 S_t \,d \widetilde W_t \\
&=  (0.105 S_t-0.1)\,dt + 0.4 S_t \,d \widetilde W_t
\end{align*}$$

>Answer: $\,d S_t=(0.105 S_t-0.1)\,dt + 0.4 S_t \,d \widetilde W_t$

# Risk Neutral Pricing BS

### Slide 23' {.unnumbered}

Consider the asset price process $S_t$ follows a geometric Brownian motion: $\,d S_t = 0.25S_t \,dt+0.4St\,dW_t$,
where $W_t$ is a standard Brownian motion on the real world probability space, denoted by $(\omega, \mathcal{F}, \mathcal{P})$. Suppose the asset price is $10$.
What is the probability that the asset price will be greater than $10.4$ after $2$ year from now?
What is the expected price after $2$ year from now?

>Let $Y_t=\ln S_t$ and $f(t,x)=\ln x$, we have:
$$\begin{align*}
f_t&=0 \\
f_x&=\frac{1}{x} \\
f_{tt}&=0 \\
f_{xx}&=-\frac{1}{x^2} \\
f_{tx}&=0 \\
\end{align*}$$

>Applying Ito Doeblin formula, we have:

>$$\begin{align*}
\,d(Y_t)&=\frac{1}{S_t} \,dS_t-\frac{1}{2}\frac{1}{S_t^2}\,dS_t^2 \\
&=\frac{1}{S_t} (0.25S_t\,dt + 0.4S_t\,dW_t)-\frac{1}{2}\frac{1}{S_t^2}(0.25S_t\,dt + 0.4S_t\,dW_t)^2 \\
&=\frac{1}{S_t}\cdot0.25S_t\,dt + \frac{1}{S_t} \cdot 0.4S_t\,dW_t-\frac{1}{2}\frac{1}{S_t^2} \cdot 0.4^2S_t^2\,dW_t^2 \\
&=0.25\,dt + 0.4\,dW_t-\frac{0.4^2}{2}\,dt \\
&=0.17\,dt + 0.4\,dW_t \\
\,d \ln S_t&=0.17\,dt + 0.4\,dW_t \\
\int_0^2 \,d \ln S_s&= \int_0^2 0.17\,ds +\int_0^2 0.4\,dW_s \\
\ln S_s\Biggr|_{0}^{2} &= 0.17\Biggr|_{0}^{2}+0.4W_s\Biggr|_{0}^{2} \\
\ln \left( \frac{S_2}{S_0} \right) &= 0.34+0.4W_2 \\
S_2 &= S_0e^{0.34+0.4W_2} \\
S_2 &= 10e^{0.34+0.4W_2} \\
\end{align*}$$

>The probability that the asset price will be less than 10.4 after 2 year from now is:
$$\begin{align*}
P(S_2) <10.4 &= P \left(W_2 < \frac{\ln \left(\frac{10.4}{10} \right)-0.34}{0.4} \right) \\
&=P \left(W_1 < \frac{\ln \left(\frac{10.4}{10} \right)-0.34}{0.4 \cdot \sqrt{2}} \right) \\
&= \Phi(-0.53) \\
&=0.29746
\end{align*}$$

>$$ \ln 10 +0.34+0.4W_2 \sim \mathcal{N}(\ln 10 +0.34,0.4 \sqrt{2}) \\
e^{\ln 10 +0.34+0.4W_2} \sim \log\mathcal{N}(\ln 10 +0.34,0.4 \sqrt{2}) \\
(S_2|S_0=10) \sim \log\mathcal{N}(\ln 10 +0.34,0.4 \sqrt{2})
$$
The expected price after 2 year from now is:
$$\begin{align*}
\mathbb{E}[S_2]&=e^{\mu+\frac{1}{2}\sigma^2} \\
&=e^{\ln 10 +0.34+\frac{1}{2}(0.4 \sqrt{2})^2} \\
&=16.49
\end{align*}$$

>Answer: The probability that the asset price will be less than 10.4 after 2 year from now is $29.47\%$. The expected price after 2 year from now is $16.49$.

### Slide 34 {.unnumbered}

>$$\begin{align*}
I_1 &=S_t \cdot \frac{1}{\sqrt{2\pi}} \int_{u_K}^\infty e^{-\frac{1}{2} u^2+\sigma u\sqrt{T-t}-r(T-t)+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}\,du \\
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

### Slide 27 {.unnumbered}

Suppose the stochastic process of the asset price $S_t$ follows a geometric Brownian motion:
$\,d S_t = 0.1 S_t \,dt+0.3 S_t \,dW_t^\mathcal{P}$,
where W_t^\mathcal{P} is a standard Brownian motion on the real world probability space, denoted by $(\omega, \mathcal{F}, \mathcal{P})$. A European call option written on the stock with parameters: exercise price $K = 10$, maturity time $T > t$ (year), the risk-free interest rate is $r = 0.07$.

Compute the fair price when $t = 0.5$, $T = 1$, $S_t = 11$ using Binomial pricing approach.

>$$\begin{align*}
u&=e^{\sigma \sqrt{\frac{T-t}{N}}} \\
&=e^{0.3\sqrt{\frac{1-0.5}{3}}} \\
&=1.13 \\
d&=e^{-\sigma \sqrt{\frac{T-t}{N}}} \\
&=e^{-0.3\sqrt{\frac{1-0.5}{3}}} \\
&=0.88 \\
p &= \frac{e^{r \cdot \frac{T-t}{N}}-d}{u-d} \\
&= \frac{e^{0.07 \cdot \frac{1-0.5}{3}}-0.88}{1.13-0.88} \\
&=0.52 \\
q &= \frac{u-e^{r \cdot \frac{T-t}{N}}}{u-d} \\
&= \frac{1.13-e^{0.07 \cdot \frac{1-0.5}{3}}}{1.13-0.88} \\
&=0.48 \\
\end{align*}$$

>$$\begin{align*}
V_{03}&=\max(S_0 \cdot 1.13^3-10,0) \\
&=\max(11 \cdot 1.13^3-10,0) \\
&= 5.88 \\
V_{13}&=\max(S_0 \cdot u^2 d-10,0) \\
&=\max(11 \cdot 1.13^2 \cdot 0.88-10,0) \\
&=2.43 \\
V_{23}&=\max(S_0 \cdot u d^2-10,0) \\
&=\max(11 \cdot 1.13 \cdot 0.88^2-10,0) \\
&=0 \\
V_{33}&=\max(S_0 \cdot d^3-10,0) \\
&=\max(11 \cdot 0.88^3-10,0) \\
&=0
\end{align*}$$

>$$\begin{align*}
V_{02}&=e^{-r \cdot \frac{T-t}{N}}(V_{03} \cdot p + V_{13} \cdot q) \\
&=e^{-0.07 \cdot \frac{1-0.5}{3}}(5.88 \cdot 0.52 + 2.43 \cdot 0.48) \\
&=4.17 \\
V_{12}&=e^{-r \cdot \frac{T-t}{N}}(V_{13} \cdot p + V_{23} \cdot q) \\
&=e^{-0.07 \cdot \frac{1-0.5}{3}}(2.43 \cdot 0.52 + 0 \cdot 0.48) \\
&=1.24 \\
V_{22}&=e^{-r \cdot \frac{T-t}{N}}(V_{23} \cdot p + V_{33} \cdot q) \\
&=e^{-0.07 \cdot \frac{1-0.5}{3}}(0 \cdot 0.52 + 0 \cdot 0.48) \\
&=0 \\
\end{align*}$$

>$$\begin{align*}
V_{01}&=e^{-r \cdot \frac{T-t}{N}}(V_{02} \cdot p + V_{12} \cdot q) \\
&=e^{-0.07 \cdot \frac{1-0.5}{3}}(4.17 \cdot 0.52 + 1.24 \cdot 0.48) \\
&=2.72 \\
V_{11}&=e^{-r \cdot \frac{T-t}{N}}(V_{12} \cdot p + V_{22} \cdot q) \\
&=e^{-0.07 \cdot \frac{1-0.5}{3}}(1.24 \cdot 0.52 + 0 \cdot 0.48) \\
&=0.64 \\
\end{align*}$$

>$$\begin{align*}
V_{0}&=e^{-r \cdot \frac{T-t}{N}}(V_{01} \cdot p + V_{11} \cdot q) \\
&=e^{-0.07 \cdot \frac{1-0.5}{3}}(2.72 \cdot 0.52 + 0.64 \cdot 0.48) \\
&=1.7 
\end{align*}$$

>Answer: The fair price of the option is $1.7$


```r
European_call_binomial=function( T, t,r, X,N,S0,sigma){
  delta_t=(T-t)/N
  u = exp(sigma*sqrt(delta_t))
  d = exp(-sigma*sqrt(delta_t))
  p = (exp(r * delta_t) - d)/(u - d) ### probability of up move
  Df = exp(-r * (T-t)) ### discounting factor
  Ce=0;
  for (i in 1:(N+1)){
    Ce =Ce+choose(N,i-1)*p^{i-1}*(1-p)^{N+1-i}*max(S0*u^{i-1}*d^{N-i+1}-X,0)
    }
  return(Df*Ce)
}

European_call_binomial(1,0.5,0.07,10,3,11,0.3)
```

```
#> [1] 1.696403
```

## Log-normal Distribution

### Slide 46 {.unnumbered}

Let X be a normal random variable with mean 1 and variance 3 and
$Y = e^X$.
What is the probability density function of $X$?

>$$\begin{align*}
f_X(x) &= \frac{1}{\sigma\sqrt{2\pi}} e^{-\frac{1}{2} \left( \frac{x - \mu}{\sigma} \right)^2}\\
&= \frac{1}{\sqrt{3}\sqrt{2\pi}} e^{-\frac{1}{2} \left( \frac{x - 1}{\sqrt{3}} \right)^2}\\
&=  \frac{1}{\sqrt{6 \pi}}e^{- \frac{(x-1)^2}{6}} 
\end{align*}$$

>Answer: $f_X(x)=\frac{1}{\sqrt{6 \pi}}e^{- \frac{(x-1)^2}{6}}$

What is the probability density function of $Y$?

>$$\begin{align*}
f_Y(x) &=\frac{1}{x\sigma\sqrt{2\pi}}e^{-\frac{1}{2} \left( \frac{\ln x - \mu}{\sigma} \right)^2} \\
&=\frac{1}{x\sqrt{3}\sqrt{2\pi}}e^{-\frac{1}{2} \left( \frac{\ln x - 1}{\sqrt{3}} \right)^2} \\
&=\frac{1}{x\sqrt{6\pi}}e^{- \frac{(\ln x - 1)^2}{6} }   
\end{align*}$$

>Answer: $f_Y(x)=\frac{1}{x\sqrt{6\pi}}e^{- \frac{(\ln x - 1)^2}{6} }$

## Black–Scholes Call formula

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

>Aply Ito-Doeblin formula, we have:
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
e^{\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t)+\sigma(W_T^{\mathcal{Q}}-W_t^{\mathcal{Q}})} &\sim \log\mathcal{N}(\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t),\sigma^2(T-t)) \\
 (S_T|S_t) &\sim \log\mathcal{N}(\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t),\sigma^2(T-t)) \\
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

>The value of the put option becomes:
$$\begin{align*}
C(S_t,t)&=\frac{e^{-r(T-t)}}{\sigma \sqrt{2\pi} \sqrt{T-t}} \int_K^\infty (x-K)e^{-\frac{1}{2} \frac{(\ln x-\ln S_t -(r-\frac{1}{2} \cdot \sigma^2)(T-t)))^2}{\sigma^2(T-t)}} \frac{1}{x}\,dx \\
&=\frac{e^{-r(T-t)}}{\sigma \sqrt{2\pi}\sqrt{T-t}} \int_{u_K}^\infty (S_te^{\sigma u\sqrt{T-t}+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}-K)e^{-\frac{1}{2} u^2} \sigma\sqrt{T-t}\,du \\
&=\frac{e^{-r(T-t)}}{\sigma\sqrt{2\pi}\sqrt{T-t}} \sigma\sqrt{T-t} \int_{u_K}^\infty (S_te^{\sigma u\sqrt{T-t}+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}e^{-\frac{1}{2} u^2}-Ke^{-\frac{1}{2} u^2}) \,du \\
&=\frac{e^{-r(T-t)}}{\sqrt{2\pi}} \int_{u_K}^\infty (S_te^{\sigma u\sqrt{T-t}+(r-\frac{1}{2} \cdot \sigma^2)(T-t)-\frac{1}{2} u^2}-Ke^{-\frac{1}{2} u^2}) \,du \\
&=\frac{e^{-r(T-t)}}{\sqrt{2\pi}} \int_{u_K}^\infty S_te^{\sigma u\sqrt{T-t}+(r-\frac{1}{2} \cdot \sigma^2)(T-t)-\frac{1}{2} u^2}\,du \\
&-\frac{e^{-r(T-t)}}{\sqrt{2\pi}} \int_{u_K}^\infty Ke^{-\frac{1}{2} u^2} \,du \\
&=I_1 \\ 
&-  I_2 \\
\end{align*}$$

>$$\begin{align*}
I_1 &=S_t \cdot \frac{1}{\sqrt{2\pi}} \int_{u_K}^\infty e^{-\frac{1}{2} u^2+\sigma u\sqrt{T-t}-r(T-t)+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}\,du \\
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

>Answer:
$$\begin{align*}
C(S_t,t) &=S_t \cdot N \left({\frac{\ln \left( \frac{S_t}{K} \right)+(r+\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}}\right) \\
&- Ke^{-r(T-t)} \cdot N \left({\frac{\ln \left( \frac{S_t}{K} \right)+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}}\right)
\end{align*}$$

### Slide 47 {.unnumbered}

Suppose the stochastic process of the asset price $S_t$ follows a geometric
Brownian motion:

$$dSt = 0.15S_t \,dt + 0.4 S_t \,dW_t^\mathcal{P}$$
where $W_t^P$ is a standard Brownian motion on the real world probability
space, denoted by $(\omega, \mathcal{F},\mathcal{P})$. A European call option written on the stock
with parameters: exercise price $K = 8$, maturity time $T > t$ (year), the
risk-free interest rate is $r = 0.06$.

1. Under the Black-Scholes framework, using the probabilistic approach to
derive the formula in terms of $t,T$ and $S_t$ for the fair price of the option?

>Let $\mathcal{P}$ and $\mathcal{Q}$ be the physical and risk neutral measures on $(\omega,\mathcal{F})$ respectively. Let $\{W_t^\mathcal{P}\}_{t \geq 0}$ be the standard Brownian motion on $\mathcal{P}$. For $\{S_t\}_{t \geq 0}$ be the process of asset price, we have:
$$dSt = 0.15S_t \,dt + 0.4 S_t \,dW_t^\mathcal{P}$$

>With $f(t,x)=e^{-0.06t}x$ then we can calculate:
$$\begin{align*} 
f_t&=-0.06e^{-0.06t}x \\
f_x&=e^{-0.06t} \\
f_{tt}&=0.06^2e^{-0.06t}x \\
f_{xx}&=0 \\
f_{tx}&=-0.06e^{-0.06t}
\end{align*}$$

>Aply Ito-Doeblin formula, we have:
$$\begin{align*}
d(e^{-0.06t}S_t) &= -0.06e^{-0.06t}S_t\,dt+e^{-0.06t}\,dS_t -0.06e^{-0.06t}\,dt \,dS_t \\
&= -0.06e^{-0.06t}S_t\,dt+e^{-0.06t}(0.15 S_t \,dt + 0.4 S_t \,dW_t^\mathcal{P}) \\
&-0.06e^{-0.06t}\,dt(0.15 S_t \,dt + 0.4 S_t \,dW_t^\mathcal{P}) \\
&= e^{-0.06t}S_t[(0.15-0.06) \,dt+0.4 \,d W_t^{\mathcal{P}}] -0.06 \cdot 0.15 e^{-0.06t}St\,dt^2 \\
&- 0.06 \cdot 0.4 S_t \,dt\,dW_t^\mathcal{P})\\
&= e^{-0.06t}S_t[0.15-0.06 \,dt+0.4 (\,d W_t^{\mathcal{Q}}-\theta_t) \,dt] \\
&= e^{-0.06t}S_t[(0.15-0.06-0.4 \theta_t) \,dt+0.4 \,d W_t^{\mathcal{Q}} \,dt]
\end{align*}$$

>In order to have the process $\{e^{−0.06t}S_t\}_{t \geq 0}$ be the martigale process, we choose $\theta_t$ such that:
$$-0.06+0.15-0.4 \theta_t=0 \rightarrow \theta_t=\frac{-0.06+0.15}{0.4} $$
then $$E^\mathcal{P}[e^{\frac{1}{2} \int_0^T \theta_t^2\,dt}]<\infty$$

>By the Girsanov’s theorem, there is a risk neutral measure $\mathcal{Q}$ defined by the Radon-Nykodym $$E \left[\frac{\,d \mathcal{Q}}{\,d \mathcal{P}} |\mathcal{F}_t\right]=Z_t=e^{-\int_0^t \theta_s \,d W_s^\mathcal{P}-\frac{1}{2} \theta_s^2 \,ds}$$ such that $W_t^\mathcal{Q}=W_t^\mathcal{P}+\int_0^t\theta_s \,ds$  
is the standard Brownian motion under $\mathcal{Q}$.
$$W_t^\mathcal{Q}=W_t^\mathcal{P}+\int_0^t\theta_s \,ds \\
\rightarrow \,dW_t^\mathcal{Q}=\,dW_t^\mathcal{P}+\theta_t\,dt$$

>Since $e^{-rt}S_t$ is a martingale under $\mathcal{Q}$ and $\mathcal{Q}$ is an equivalent martingale measure to $\mathcal{P}$, we can write:
$$\begin{align*}
\,dS_t &= 0.15S_t \,dt + 0.4 S_t \,dW_t^\mathcal{P} \\
&=0.15S_t \,dt + 0.4 S_t (\,dW_t^\mathcal{Q}-\theta_t \,dt) \\
&=0.15S_t \,dt + 0.4 S_t (\,dW_t^\mathcal{Q}-\frac{-0.06+0.15}{0.4} \,dt) \\
&=\left(0.15-0.4\cdot\frac{-0.06+0.15}{0.4} \right)S_t \,dt + 0.4 S_t \,dW_t^\mathcal{Q} \\
&=-0.06S_t \,dt + 0.4 S_t \,dW_t^\mathcal{Q} \\
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
&=\frac{1}{S_t} (0.06S_t \,dt + 0.4 S_t \,dW_t^\mathcal{Q})-\frac{1}{2}\frac{1}{S_t^2}(0.06S_t \,dt + 0.4 S_t \,dW_t^\mathcal{Q})^2 \\
&=(0.06-\frac{1}{2} \cdot 0.4^2)\,dt + 0.4 \,dW_t^\mathcal{Q} \\
\,d(\ln S_t)&=(0.06-\frac{1}{2} \cdot 0.4^2)\,dt + 0.4 \,dW_t^\mathcal{Q} \\
 \int_t^T \,d(\ln S_s)&=\int_t^T(0.06-\frac{1}{2} \cdot 0.4^2)\,ds + \int_t^T0.4 \,dW_s^\mathcal{Q} \\
 ln \left( \frac{S_T}{S_t} \right)&=(0.06-\frac{1}{2} \cdot 0.4^2)(T-t)+0.4(W_T^\mathcal{Q}-W_t^\mathcal{Q}) \\
 S_T&=e^{\ln S_t +(0.06-\frac{1}{2} \cdot 0.4^2)(T-t)+0.4(W_T^{\mathcal{Q}}-W_t^{\mathcal{Q}})}
\end{align*}$$

>We have
$$\begin{align*}
&\ln 10 +(0.06-\frac{1}{2} \cdot 0.4^2)(1-0.5)+0.4(W_T^{\mathcal{Q}}-W_t^{\mathcal{Q}}) \\
&\sim \mathcal{N}(\ln 10 +(0.06-\frac{1}{2} \cdot 0.4^2)(1-0.5),0.4^2(1-0.5)) \\
\\
&e^{\ln 10 +(0.06-\frac{1}{2} \cdot 0.4^2)(1-0.5)+0.4(W_T^{\mathcal{Q}}-W_t^{\mathcal{Q}})} \\
&\sim \log\mathcal{N}(\ln 10 +(0.06-\frac{1}{2} \cdot 0.4^2)(1-0.5),0.4^2(1-0.5)) \\
\\
&(S_T|10) \sim \log\mathcal{N}(\ln 10 +(0.06-\frac{1}{2} \cdot 0.4^2)(1-0.5),0.4^2(1-0.5)) \\
\end{align*}$$

>The probability density function of $(S_T|10)$ is
$$f_{S_T|10}(x)=\frac{1}{0.4 x\sqrt{2\pi(1-0.5)}}e^{-\frac{1}{2} \frac{(\ln x-(\ln 10 +(0.06-\frac{1}{2} \cdot 0.4^2)(1-0.5)))^2}{0.4^2(1-0.5)}} $$

2. Compute the fair price when $t = 0.5,T = 1, S_t = 10$.

>$$\begin{align*}
S_t &=10 \\ K&=8 \\ r&=0.06 \\ \sigma &=0.4 \\ T&=1 \\ t&=0.5 
\end{align*}$$

>We calculate $d_1$ and $d_2$
$$\begin{align*}
d_1&=\frac{\ln\left(\frac{S_t}{K} \right)+(r+\frac{1}{2}\sigma^2)(T-t)}{\sigma \sqrt{T-t}} \\ 
&=\frac{\ln\left(\frac{10}{8} \right)+(0.06+\frac{1}{2} \cdot 0.4^2) \cdot (1-0.5)}{0.4 \cdot \sqrt{(1-0.5)}} \\ 
&=1.03 \\
d_2&=\frac{\ln\left(\frac{S_t}{K} \right)+(r-\frac{1}{2}\sigma^2)(T-t)}{\sigma \sqrt{T-t}} \\ 
&=\frac{\ln\left(\frac{10}{8} \right)+(0.06-\frac{1}{2} \cdot 0.4^2) \cdot (1-0.5)}{0.4 \cdot \sqrt{(1-0.5)}} \\ 
&=0.75 \\
\end{align*}$$

>The value of the call option is:
$$\begin{align*}
C&=S_t \cdot N(d_1) - K \cdot N(d_2) \cdot e^{-r(T-t)} \\
&=10 \cdot N(0.91) - 8 \cdot N(0.51) \cdot e^{-0.06 \cdot (1-0.5)} \\
&=2.49
\end{align*}$$

## Black–Scholes Put formula

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

>Aply Ito-Doeblin formula, we have:
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
e^{\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t)+\sigma(W_T^{\mathcal{Q}}-W_t^{\mathcal{Q}})} &\sim \log\mathcal{N}(\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t),\sigma^2(T-t)) \\
 (S_T|S_t) &\sim \log\mathcal{N}(\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t),\sigma^2(T-t)) \\
\end{align*}$$

>The probability density function of $(S_T|S_t)$ is
$$f_{S_T|S_t}(x)=\frac{1}{\sigma x\sqrt{2\pi(T-t)}}e^{-\frac{1}{2} \frac{(\ln x-(\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t)))^2}{\sigma^2(T-t)}} $$

>From Feyman-Kac formula we have:
$$ P(S_t,t)=e^{-r(T-t)} \mathbb{E}^\mathcal{Q}[max(K-S_T,0)|\mathcal{F}_t] $$

>Applying the moment generating function, we have:
$$\begin{align*} 
P(S_t,t)&=e^{-r(T-t)}\int_{-\infty}^\infty \max(K-x,0) f_{S_T|S_t}(x) \,dx \\
&=e^{-r(T-t)}\int_{-\infty}^K (K-x) \frac{1}{\sigma x\sqrt{2\pi}\sqrt{(T-t)}}e^{-\frac{1}{2} \frac{(\ln x-(\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t)))^2}{\sigma^2(T-t)}} \,dx
\end{align*}$$

>$$\begin{align*}
P(S_t,t)&=e^{-r(T-t)}\int_{-\infty}^K (K-x) \frac{1}{\sigma x\sqrt{2\pi}\sqrt{(T-t)}}e^{-\frac{1}{2} \frac{(\ln x-(\ln S_t +(r-\frac{1}{2} \cdot \sigma^2)(T-t)))^2}{\sigma^2(T-t)}} \,dx \\
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

>Answer: 
$$\begin{align*}
P(S_t,t) &= -S_t \cdot N \left({-\frac{\ln \left( \frac{S_t}{K} \right)+(r+\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}}\right)  \\
&+ Ke^{-r(T-t)} \cdot N \left(-{\frac{\ln \left( \frac{S_t}{K} \right)+(r-\frac{1}{2} \cdot \sigma^2)(T-t)}{\sigma\sqrt{T-t}}}\right)\\
\end{align*}$$

### Slide 48 {.unnumbered}

Suppose the stochastic process of the asset price $S_t$ follows a geometric
Brownian motion:
$$\,d S_t = 0.1 S_t \,dt + 0.3 S_t \,dW_t^\mathcal{P}$$
where $W_t^P$
is a standard Brownian motion on the real world probability
space, denoted by $(\omega, \mathcal{F},\mathcal{P})$. A European put option written on the stock
with parameters: exercise price $K = 10$, maturity time $T > t$ (year), the
risk-free interest rate is $r = 0.07$.

1. Under the Black-Scholes framework, using the probabilistic approach to
derive the formula in terms of $t,T$ and $S_t$ for the fair price of the option?

>Let $\mathcal{P}$ and $\mathcal{Q}$ be the physical and risk neutral measures on $(\omega,\mathcal{F})$ respectively. Let $\{W_t^\mathcal{P}\}_{t \geq 0}$ be the standard Brownian motion on $\mathcal{P}$. For $\{S_t\}_{t \geq 0}$ be the process of asset price, we have:
$$dSt = 0.1S_t \,dt + 0.3 S_t \,dW_t^\mathcal{P}$$

>With $f(t,x)=e^{-0.07t}x$ then we can calculate:
$$\begin{align*} 
f_t&=-0.07e^{-0.07t}x \\
f_x&=e^{-0.07t} \\
f_{tt}&=0.07^2e^{-0.07t}x \\
f_{xx}&=0 \\
f_{tx}&=0
\end{align*}$$

>Aply Ito-Doeblin formula, we have:
$$\begin{align*}
d(e^{-0.07t}S_t) &= -0.07e^{-0.07t}S_t\,dt+e^{-0.07t}\,dS_t -0.07e^{-0.07t}\,dt \,dS_t \\
&= -0.07e^{-0.07t}S_t\,dt+e^{-0.07t}(0.1 S_t \,dt + 0.3 S_t \,dW_t^\mathcal{P}) \\
&-0.07e^{-0.07t}\,dt(0.1 S_t \,dt + 0.3 S_t \,dW_t^\mathcal{P}) \\
&= e^{-0.07t}S_t[(0.1-0.07) \,dt+0.3 \,d W_t^{\mathcal{P}}] \\
&-0.07 \cdot 0.1 e^{-0.07t}St\,dt^2 - 0.07 \cdot 0.3 S_t \,dt\,dW_t^\mathcal{P})\\
&= e^{-0.07t}S_t[0.1-0.07 \,dt+0.3 (\,d W_t^{\mathcal{Q}}-\theta_t) \,dt] \\
&= e^{-0.07t}S_t[(0.1-0.07-0.3 \theta_t) \,dt+0.3 \,d W_t^{\mathcal{Q}} \,dt]
\end{align*}$$

>In order to have the process $\{e^{−0.07t}S_t\}_{t \geq 0}$ be the martigale process, we choose $\theta_t$ such that:
$$-0.07+0.1-0.3 \theta_t=0 \rightarrow \theta_t=\frac{-0.07+0.1}{0.3} $$
then $$E^\mathcal{P}[e^{\frac{1}{2} \int_0^T \theta_t^2\,dt}]<\infty$$

>By the Girsanov’s theorem, there is a risk neutral measure $\mathcal{Q}$ defined by the Radon-Nykodym $$E \left[\frac{\,d \mathcal{Q}}{\,d \mathcal{P}} |\mathcal{F}_t\right]=Z_t=e^{-\int_0^t \theta_s \,d W_s^\mathcal{P}-\frac{1}{2} \theta_s^2 \,ds}$$ such that $W_t^\mathcal{Q}=W_t^\mathcal{P}+\int_0^t\theta_s \,ds$  
is the standard Brownian motion under $\mathcal{Q}$.
$$W_t^\mathcal{Q}=W_t^\mathcal{P}+\int_0^t\theta_s \,ds \\
\rightarrow \,dW_t^\mathcal{Q}=\,dW_t^\mathcal{P}+\theta_t\,dt$$

>Since $e^{-rt}S_t$ is a martingale under $\mathcal{Q}$ and $\mathcal{Q}$ is an equivalent martingale measure to $\mathcal{P}$, we can write:
$$\begin{align*}
\,dS_t &= 0.1S_t \,dt + 0.3 S_t \,dW_t^\mathcal{P} \\
&=0.1S_t \,dt + 0.3 S_t (\,dW_t^\mathcal{Q}-\theta_t \,dt) \\
&=0.1S_t \,dt + 0.3 S_t (\,dW_t^\mathcal{Q}-\frac{-0.07+0.1}{0.3} \,dt) \\
&=\left(0.1-0.3\cdot\frac{-0.07+0.1}{0.3} \right)S_t \,dt + 0.3 S_t \,dW_t^\mathcal{Q} \\
&=-0.07S_t \,dt + 0.3 S_t \,dW_t^\mathcal{Q} \\
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
&=\frac{1}{S_t} (0.07S_t \,dt + 0.3 S_t \,dW_t^\mathcal{Q})-\frac{1}{2}\frac{1}{S_t^2}(0.07S_t \,dt + 0.3 S_t \,dW_t^\mathcal{Q})^2 \\
&=(0.07-\frac{1}{2} \cdot 0.3^2)\,dt + 0.3 \,dW_t^\mathcal{Q} \\
\,d(\ln S_t)&=(0.07-\frac{1}{2} \cdot 0.3^2)\,dt + 0.3 \,dW_t^\mathcal{Q} \\
 \int_t^T \,d(\ln S_s)&=\int_t^T(0.07-\frac{1}{2} \cdot 0.3^2)\,ds + \int_t^T0.3 \,dW_s^\mathcal{Q} \\
 ln \left( \frac{S_T}{S_t} \right)&=(0.07-\frac{1}{2} \cdot 0.3^2)(T-t)+0.3(W_T^\mathcal{Q}-W_t^\mathcal{Q}) \\
 S_T&=e^{\ln S_t +(0.07-\frac{1}{2} \cdot 0.3^2)(T-t)+0.3(W_T^{\mathcal{Q}}-W_t^{\mathcal{Q}})}
\end{align*}$$

>We have
$$\begin{align*}
&\ln S_t +(0.07-\frac{1}{2} \cdot 0.3^2)(T-t)+0.3(W_T^{\mathcal{Q}}-W_t^{\mathcal{Q}}) \\
&\sim \mathcal{N}(\ln S_t +(0.07-\frac{1}{2} \cdot 0.3^2)(T-t),0.3^2(T-t)) \\
\\
&e^{\ln S_t +(0.07-\frac{1}{2} \cdot 0.3^2)(T-t)+0.3(W_T^{\mathcal{Q}}-W_t^{\mathcal{Q}})} \\
&\sim \log\mathcal{N}(\ln S_t +(0.07-\frac{1}{2} \cdot 0.3^2)(T-t),0.3^2(T-t)) \\
\\
&(S_T|S_t) \sim \log\mathcal{N}(\ln S_t +(0.07-\frac{1}{2} \cdot 0.3^2)(T-t),0.3^2(T-t)) \\
\end{align*}$$

>The probability density function of $(S_T|S_t)$ is
$$f_{S_T|S_t}(x)=\frac{1}{0.3x\sqrt{2\pi(T-t)}}e^{-\frac{1}{2} \frac{(\ln x-(\ln S_t +(0.07-\frac{1}{2} \cdot 0.3^2)(T-t)))^2}{0.3^2(T-t)}} $$

2. Compute the fair price when $t = 0.5,T = 1, S_t = 11$.

>$$\begin{align*}
S_t &=11 \\ K&=10 \\ r&=0.07 \\ \sigma &=0.3 \\ T&=1 \\ t&=0.5 
\end{align*}$$

>We calculate $d_1$ and $d_2$
$$\begin{align*}
d_1&=\frac{\ln\left(\frac{S_t}{K} \right)+(r+\frac{1}{2}\sigma^2)(T-t)}{\sigma \sqrt{T-t}} \\ 
&=\frac{\ln\left(\frac{11}{10} \right)+(0.07+\frac{1}{2} \cdot 0.3^2) \cdot (1-0.5)}{0.3 \cdot \sqrt{(1-0.5)}} \\ 
&=0.72 \\
d_2&=\frac{\ln\left(\frac{S_t}{K} \right)+(r-\frac{1}{2}\sigma^2)(T-t)}{\sigma \sqrt{T-t}} \\ 
&=\frac{\ln\left(\frac{11}{10} \right)+(0.07-\frac{1}{2} \cdot 0.3^2) \cdot (1-0.5)}{0.3 \cdot \sqrt{(1-0.5)}} \\ 
&=0.51 \\
\end{align*}$$

>The value of the put option is:
$$\begin{align*}
P&= K \cdot N(-d_2) \cdot e^{-r(T-t)} - S_t \cdot N(-d_1) \\
&=10 \cdot N(-0.51) \cdot e^{-0.06 \cdot (1-0.5)} - 11 \cdot N(-0.72) \\
&=0.37
\end{align*}$$

## Integrand

### Slide 49 {.unnumbered}

Let $$\begin{align*}
d_1(S_t,t)&=\frac{\ln S_t - \ln K+\left(r-\delta+\frac{1}{2} \sigma^2\right)(T-t)}{\sigma \sqrt{T-t}} \\ 
d_2(S_t,t)&=d_1(S_t,t)-\sigma \sqrt{T-t} \\
N(x)&=\int_{-\infty}^{x} \frac{1}{\sqrt{2\pi}}e^{-\frac{1}{2}y^2} \,dy \\
m&= \ln S_t+\left(r−\delta− \frac{1}{2}\sigma^2 \right)(T−t)
\end{align*}$$
Prove that

a. $e^{-r(T-t)} \int_K^\infty \frac{1}{\sigma \sqrt{2\pi(T-t)}}e^{-\frac{(\ln y -m)^2}{2\sigma^2(T-t)}} \,dy=S_t e^{-\delta(T-t)}N(d_1(S_t,t))$

>$$ 
RHS = e^{-r(T-t)} \frac{1}{\sqrt{2\pi}}\int_K^\infty e^{-\frac{(\ln y -m)^2}{2\sigma^2(T-t)}} \frac{1}{\sigma \sqrt{(T-t)}}\,dy
$$

>Let $u=\frac{\ln y -m}{\sigma\sqrt{T-t}}$ then
$$y=e^{m+u\sigma \sqrt{T-t}} $$
$$\,d u = \frac{1}{y\sigma\sqrt{T-t}} \,dy \rightarrow e^{m+u\sigma \sqrt{T-t}}\,d u = \frac{1}{\sigma\sqrt{T-t}} \,dy$$

>From $u_K= \frac{\ln K -m}{\sigma\sqrt{T-t}}$, we have
$$\begin{align*}
\sigma \sqrt{T-t}-u_K &= \sigma \sqrt{T-t}-\frac{\ln K -m}{\sigma\sqrt{T-t}} \\
&=\frac{\sigma^2(T-t)- \ln K +(\ln S_t+\left(r−\delta− \frac{1}{2}\sigma^2 \right)(T−t))}{\sigma\sqrt{T-t}} \\
&=\frac{\ln S_t - \ln K+\left(r-\delta+\frac{1}{2} \sigma^2\right)(T-t)}{\sigma \sqrt{T-t}} \\
&=d_1(S_t,t) \\
\end{align*}$$

>$$\begin{align*}
RHS &=e^{-r(T-t)} \frac{1}{\sqrt{2\pi}}\int_{u_K}^\infty e^{-\frac{1}{2}u^2} e^{m+u\sigma \sqrt{T-t}}\,d u \\
&= e^{-r(T-t)} \frac{1}{\sqrt{2\pi}}\int_{u_K}^\infty e^{-\frac{1}{2}u^2} e^{m+u\sigma \sqrt{T-t}}\,d u \\
&=e^{-r(T-t)+m} \frac{1}{\sqrt{2\pi}}\int_{u_K}^\infty e^{-\frac{1}{2}u^2+u\sigma \sqrt{T-t}}\,d u \\
&=e^{-r(T-t)+m} \frac{1}{\sqrt{2\pi}}\int_{u_K}^\infty e^{-\frac{1}{2}(u^2-2u\sigma \sqrt{T-t}+\sigma^2(T-t))+\frac{1}{2}\sigma^2(T-t)}\,d u \\
&=e^{-r(T-t)+m+\frac{1}{2}\sigma^2(T-t)} \frac{1}{\sqrt{2\pi}}\int_{u_K}^\infty e^{-\frac{1}{2}(u-\sigma \sqrt{T-t})^2}\,d (u-\sigma \sqrt{T-t}) \\
&=e^{-r(T-t)+\ln S_t+\left(r−\delta− \frac{1}{2}\sigma^2 \right)(T−t)+\frac{1}{2}\sigma^2(T-t)} \frac{1}{\sqrt{2\pi}}\int_{u_K-\sigma \sqrt{T-t}}^\infty e^{-\frac{1}{2}u^2}\,d u \\
&=S_te^{−\delta(T−t)} \frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\sigma \sqrt{T-t}-u_K} e^{-\frac{1}{2}u^2}\,d u \\
&=S_te^{−\delta(T−t)} N(\sigma \sqrt{T-t}-u_K) \\
&=S_te^{−\delta(T−t)} N(d_1(S_t,t)) \\
\end{align*}$$

b. $e^{-r(T-t)} \int_K^\infty \frac{1}{y\sigma \sqrt{2\pi(T-t)}}e^{-\frac{(\ln y -m)^2}{2\sigma^2(T-t)}} \,dy=K e^{-r(T-t)}N(d_2(S_t,t))$

>$$RHS = Ke^{-r(T-t)} \frac{1}{\sqrt{2\pi}}\int_K^\infty e^{-\frac{(\ln y -m)^2}{2\sigma^2(T-t)}} \frac{1}{y\sigma \sqrt{(T-t)}}\,dy$$

>Let $u=\frac{\ln y -m}{\sigma\sqrt{T-t}}$ then
$$\,d u = \frac{1}{y\sigma\sqrt{T-t}} \,dy$$

>From $u_K= \frac{\ln K -m}{\sigma\sqrt{T-t}}$, we have
$$\begin{align*}
\sigma \sqrt{T-t}-u_K &=d_1(S_t,t) \\ \rightarrow -u_K&=d_1(S_t,t)-\sigma \sqrt{T-t} \\
&=d_2(S_t,t)
\end{align*}$$

>$$\begin{align*}
RHS &=Ke^{-r(T-t)} \frac{1}{\sqrt{2\pi}} \int_{u_K}^{\infty}e^{-\frac{1}{2}u^2}\,du \\
&=Ke^{-r(T-t)} \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{-u_K}e^{-\frac{1}{2}u^2}\,du \\
&=Ke^{-r(T-t)} \frac{1}{\sqrt{2\pi}} N(d_2(S_t,t))
\end{align*}$$

### Slide 50 {.unnumbered}

Let $$\begin{align*}
d_1(S_t,t)&=\frac{\ln S_t - \ln K+\left(r-\delta+\frac{1}{2} \sigma^2\right)(T-t)}{\sigma \sqrt{T-t}} \\ 
d_2(S_t,t)&=d_1(S_t,t)-\sigma \sqrt{T-t} \\
N(x)&=\int_{-\infty}^{x} \frac{1}{\sqrt{2\pi}}e^{-\frac{1}{2}y^2} \,dy \end{align*}$$
Prove that

c. $e^{-r(T-t)} \int_{-\infty}^K \frac{1}{\sigma \sqrt{2\pi(T-t)}}e^{-\frac{(\ln y -m)^2}{2\sigma^2(T-t)}} \,dy=S_t e^{-\delta(T-t)}N(d_1(S_t,t))$

>$$ 
RHS = e^{-r(T-t)} \frac{1}{\sqrt{2\pi}}\int_{-\infty}^K e^{-\frac{(\ln y -m)^2}{2\sigma^2(T-t)}} \frac{1}{\sigma \sqrt{(T-t)}}\,dy
$$

>Let $u=\frac{\ln y -m}{\sigma\sqrt{T-t}}$ then
$$y=e^{m+u\sigma \sqrt{T-t}} $$
$$\,d u = \frac{1}{y\sigma\sqrt{T-t}} \,dy \rightarrow e^{m+u\sigma \sqrt{T-t}}\,d u = \frac{1}{\sigma\sqrt{T-t}} \,dy$$

>From $u_K= \frac{\ln K -m}{\sigma\sqrt{T-t}}$, we have
$$\begin{align*}
u_K-\sigma \sqrt{T-t} &= -\sigma \sqrt{T-t}+\frac{\ln K -m}{\sigma\sqrt{T-t}} \\
&=-\frac{\sigma^2(T-t)- \ln K +(\ln S_t+\left(r−\delta− \frac{1}{2}\sigma^2 \right)(T−t))}{\sigma\sqrt{T-t}} \\
&=-\frac{\ln S_t - \ln K+\left(r-\delta+\frac{1}{2} \sigma^2\right)(T-t)}{\sigma \sqrt{T-t}} \\
&=-d_1(S_t,t) \\
\end{align*}$$

>$$\begin{align*}
RHS &=e^{-r(T-t)} \frac{1}{\sqrt{2\pi}}\int_{-\infty}^{u_K} e^{-\frac{1}{2}u^2} e^{m+u\sigma \sqrt{T-t}}\,d u \\
&= e^{-r(T-t)} \frac{1}{\sqrt{2\pi}}\int_{-\infty}^{u_K} e^{-\frac{1}{2}u^2} e^{m+u\sigma \sqrt{T-t}}\,d u \\
&=e^{-r(T-t)+m} \frac{1}{\sqrt{2\pi}}\int_{-\infty}^{u_K} e^{-\frac{1}{2}u^2+u\sigma \sqrt{T-t}}\,d u \\
&=e^{-r(T-t)+m} \frac{1}{\sqrt{2\pi}}\int_{-\infty}^{u_K} e^{-\frac{1}{2}(u^2-2u\sigma \sqrt{T-t}+\sigma^2(T-t))+\frac{1}{2}\sigma^2(T-t)}\,d u \\
&=e^{-r(T-t)+m+\frac{1}{2}\sigma^2(T-t)} \frac{1}{\sqrt{2\pi}}\int_{-\infty}^{u_K} e^{-\frac{1}{2}(u-\sigma \sqrt{T-t})^2}\,d (u-\sigma \sqrt{T-t}) \\
&=e^{-r(T-t)+\ln S_t+\left(r−\delta− \frac{1}{2}\sigma^2 \right)(T−t)+\frac{1}{2}\sigma^2(T-t)} \frac{1}{\sqrt{2\pi}}\int_{-\infty}^{u_K-\sigma \sqrt{T-t}} e^{-\frac{1}{2}u^2}\,d u \\
&=S_te^{−\delta(T−t)} \frac{1}{\sqrt{2\pi}}\int_{-\infty}^{u_K-\sigma \sqrt{T-t}} e^{-\frac{1}{2}u^2}\,d u \\
&=S_te^{−\delta(T−t)} N(u_K-\sigma \sqrt{T-t}) \\
&=S_te^{−\delta(T−t)} N(-d_1(S_t,t)) \\
\end{align*}$$

d. $e^{-r(T-t)} \int_{-\infty}^K \frac{K}{y\sigma \sqrt{2\pi(T-t)}}e^{-\frac{(\ln y -m)^2}{2\sigma^2(T-t)}} \,dy=K e^{-r(T-t)}N(-d_2(S_t,t))$

>
$$RHS = Ke^{-r(T-t)} \frac{1}{\sqrt{2\pi}}\int_{-\infty}^K e^{-\frac{(\ln y -m)^2}{2\sigma^2(T-t)}} \frac{1}{y\sigma \sqrt{(T-t)}}\,dy$$

>Let $u=\frac{\ln y -m}{\sigma\sqrt{T-t}}$ then
$$\,d u = \frac{1}{y\sigma\sqrt{T-t}} \,dy$$

>From $u_K= \frac{\ln K -m}{\sigma\sqrt{T-t}}$, we have
$$\begin{align*}
\sigma \sqrt{T-t}-u_K &=d_1(S_t,t) \\ 
\rightarrow -u_K&=d_1(S_t,t)-\sigma \sqrt{T-t} \\
&=d_2(S_t,t)
\end{align*}$$

>$$\begin{align*}
RHS &=Ke^{-r(T-t)} \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{u_K}e^{-\frac{1}{2}u^2}\,du \\
&=Ke^{-r(T-t)} \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{u_K}e^{-\frac{1}{2}u^2}\,du \\
&=Ke^{-r(T-t)} \frac{1}{\sqrt{2\pi}} N(-d_2(S_t,t))
\end{align*}$$

## R programming

### Slide 51 {.unnumbered}

Suppose each of 30 stocks in VN30 are governed by a geometric Brownian motion. Write a R code to find the corresponding parameters for each stock.


```r
library(dplyr)
library(tidyverse)
library(lubridate)
library(tidyquant)
library(tseries)
library(timetk)
library(plotly)
require(stats4)
require(sde)
library(xts)
library(broom)
library(httr)
library(rvest)

new=NULL
id_list=c("ACB","BID","BVH","CTG","FPT","GAS","GVR","HDB","HPG","KDH","MBB","MSN","MWG","NVL","PDR","PLX","PNJ","POW","SAB","SSI","STB","TCB","TPB","VCB","VHM","VIC","VJC","VNM","VPB","VRE")
for (j in id_list){
  for (i in 1:2){ #################################
    query_params <- list(currentPage=i,id = j)
    parameter_response <- GET("https://www.cophieu68.vn/historyprice.php", query = query_params)
    stock_share =read_html(parameter_response)
    new1=html_nodes(stock_share, xpath="//table[@class='stock']") %>%
      html_table(header = TRUE,fill=TRUE) %>% as.data.frame()
    new1=new1[,2:13]
    new1$symbol=j
    new=rbind(new,new1)
  }
}

stock=new
colnames(stock)=c("date","Last_closed_price","absolute_price_change",
                  "Percentage_price_change", "Closed_price",
                  "Trading_Volume","Open_price","Highest_price",
                  "Lowest_price","Exchange_volume", "Foregin_buy_volume", "Foreign_sell_volume","symbol")
stock$date=as.Date(stock$date, format="%d-%m-%Y")
for (i in 2:12){stock[,i]=as.numeric(gsub(',', '', stock[,i]))}
stock$Trading_Volume=as.numeric(gsub(',', '', stock$Trading_Volume))
stock$Percentage_price_change=stock$absolute_price_change/stock$Last_closed_price

prices = stock %>% 
  dplyr::filter(!is.na(date), date >= "2022-01-01") %>% 
  mutate(close=as.numeric(Closed_price)) %>% 
  dplyr::filter(symbol == "VIC") %>%
  dplyr::select(date,close)
X <- prices$close

# Estimate parameters using maximum likelihood
dcBS <- function(x, t, x0, theta, log = TRUE){
  ml <- log(x0) + (theta[1]-theta[2]^2/2)*t
  sl <- sqrt(t)*theta[2]
  lik <- dlnorm(x, meanlog = ml, sdlog = sl, log=TRUE) 
  if(!log)
    lik <- exp(lik)
  return(lik)
}
BS.lik <- function(theta1,theta2) {
  n <- length(X)
  dt <- deltat(X)
  -sum(dcBS(x=X[2:n], t=dt, x0=X[1:(n-1)], theta=c(theta1,theta2), log=TRUE))
}
fit=mle(BS.lik,start=list(theta1=1,theta2=1),method="L-BFGS-B",lower=c(0.00001 ,0.000001))
mu=tidy(coef(fit))$x[1]
sigma=tidy(coef(fit))$x[2]

# Estimating parameters using historical mean and volatility of daily stock log-return
X <- prices$close
X <- diff(log(X)) ## compute the log return from the closing adjust price
alpha <- mean(X)
sigma <- sqrt(var(X))
mu <- alpha +0.5*sigma^2

# Estimating parameters using quasi-maximum likelihood
library(yuima)
X <- prices$close
Delta <- 1/252
gBm <- setModel(drift="mu*x", diffusion="sigma*x")
mod <- setYuima(model=gBm, data=setData(X, delta=Delta))
fit <- qmle(mod, start=list(mu=0.01, sigma=0.01), lower=list(mu=0, sigma=0),
            upper=list(mu=100, sigma=100))
summary(fit)
```

```
#> Quasi-Maximum likelihood estimation
#> 
#> Call:
#> qmle(yuima = mod, start = list(mu = 0.01, sigma = 0.01), lower = list(mu = 0, 
#>     sigma = 0), upper = list(mu = 100, sigma = 100))
#> 
#> Coefficients:
#>        Estimate Std. Error
#> sigma 0.2852063 0.02869789
#> mu    1.0988913 0.61611613
#> 
#> -2 log L: 197.5591
```

```r
# The corresponding parameters for 30 stocks
parameter=function(ticker){
  prices = stock %>% 
    dplyr::filter(!is.na(date), date >= "2022-01-01") %>% 
    mutate(close=as.numeric(Closed_price)) %>% 
    dplyr::filter(symbol == ticker) %>%
    dplyr::select(date,close)
  X <- prices$close
  
  dcBS <- function(x, t, x0, theta, log = TRUE){
    ml <- log(x0) + (theta[1]-theta[2]^2/2)*t
    sl <- sqrt(t)*theta[2]
    lik <- dlnorm(x, meanlog = ml, sdlog = sl, log=TRUE) 
    if(!log)
      lik <- exp(lik)
    return(lik)
  }
  BS.lik <- function(theta1,theta2) {
    n <- length(X)
    dt <- deltat(X)
    -sum(dcBS(x=X[2:n], t=dt, x0=X[1:(n-1)], theta=c(theta1,theta2), log=TRUE))
  }
  
  fit=mle(BS.lik,start=list(theta1=1,theta2=1),method="L-BFGS-B",lower=c(0.00001 ,0.000001))
  
  mu=tidy(coef(fit))$x[1]
  sigma=tidy(coef(fit))$x[2]
  return(c(mu,sigma))
}

parameter("VIC")
```

```
#> [1] 0.004353308 0.017347305
```

```r
parameters=lapply(id_list,parameter)
names(parameters)=id_list
parameters
```

```
#> $ACB
#> [1] 0.001238712 0.014204725
#> 
#> $BID
#> [1] 0.00001000 0.02629731
#> 
#> $BVH
#> [1] 0.00001000 0.01671762
#> 
#> $CTG
#> [1] 0.001828251 0.019238352
#> 
#> $FPT
#> [1] 0.0000100 0.0145045
#> 
#> $GAS
#> [1] 0.00001000 0.02626481
#> 
#> $GVR
#> [1] 0.002271504 0.025375340
#> 
#> $HDB
#> [1] 0.002519528 0.019288547
#> 
#> $HPG
#> [1] 0.0001983993 0.0229938249
#> 
#> $KDH
#> [1] 0.0003778093 0.0185761083
#> 
#> $MBB
#> [1] 0.00001000 0.02051371
#> 
#> $MSN
#> [1] 0.003248347 0.027512815
#> 
#> $MWG
#> [1] 0.00001000 0.01380855
#> 
#> $NVL
#> [1] 0.001519553 0.014746970
#> 
#> $PDR
#> [1] 0.000541702 0.020785023
#> 
#> $PLX
#> [1] 0.00001000 0.01984691
#> 
#> $PNJ
#> [1] 0.00001000 0.02008744
#> 
#> $POW
#> [1] 0.003387182 0.033464609
#> 
#> $SAB
#> [1] 0.00001000 0.01573738
#> 
#> $SSI
#> [1] 0.00453590 0.02563956
#> 
#> $STB
#> [1] 0.00001000 0.02337951
#> 
#> $TCB
#> [1] 0.000842588 0.013184540
#> 
#> $TPB
#> [1] 0.00179472 0.02482273
#> 
#> $VCB
#> [1] 0.00001000 0.01883966
#> 
#> $VHM
#> [1] 0.002531594 0.017684955
#> 
#> $VIC
#> [1] 0.004353308 0.017347305
#> 
#> $VJC
#> [1] 0.00001000 0.02249408
#> 
#> $VNM
#> [1] 0.002815725 0.011729500
#> 
#> $VPB
#> [1] 0.00001000 0.01893225
#> 
#> $VRE
#> [1] 0.00001000 0.02792013
```


### Slide 52 {.unnumbered}

An investor agreed to pay an amount $C_0$ to buy a European put option with the underlying VCB stock, which was priced at 56, 500 VND per share on 01/02/2019. This option entitles the investor a right, but not an obligation, to sell a VCB share with price 62,000 VND, at the end of the next 6 months. Suppose the risk-free interest rate is 8%.

a. Write a R code to find the volatility of VCB stock price, using the historical price data over 5 years.

```r
new=NULL
id_list=c("VCB")
for (j in id_list){
  for (i in 1:15){ #################################
    query_params <- list(currentPage=i,id = j)
    parameter_response <- GET("https://www.cophieu68.vn/historyprice.php", query = query_params)
    stock_share =read_html(parameter_response)
    new1=html_nodes(stock_share, xpath="//table[@class='stock']") %>%
      html_table(header = TRUE,fill=TRUE) %>% as.data.frame()
    new1=new1[,2:13]
    new1$symbol=j
    new=rbind(new,new1)
  }
}

stock=new
colnames(stock)=c("date","Last_closed_price","absolute_price_change",
                  "Percentage_price_change", "Closed_price",
                  "Trading_Volume","Open_price","Highest_price",
                  "Lowest_price","Exchange_volume", "Foregin_buy_volume", "Foreign_sell_volume","symbol")
stock$date=as.Date(stock$date, format="%d-%m-%Y")
for (i in 2:12){stock[,i]=as.numeric(gsub(',', '', stock[,i]))}
stock$Trading_Volume=as.numeric(gsub(',', '', stock$Trading_Volume))
stock$Percentage_price_change=stock$absolute_price_change/stock$Last_closed_price

prices= stock %>% mutate(close=as.numeric(Closed_price)) %>%
  dplyr::select(date,close)
prices=prices[prices$date>=Sys.Date() %m-% years(5),]
mean(prices$close %>% na.omit)
```

```
#> [1] 56.99766
```

```r
sd(prices$close %>% na.omit)
```

```
#> [1] 17.36393
```

b. Write a R code to estimate the parameters of the geometric Brownian motion governing the VCB price.

```r
X <- prices$close %>% 
  na.omit

# Estimate parameters using maximum likelihood
dcBS <- function(x, t, x0, theta, log = TRUE){
  ml <- log(x0) + (theta[1]-theta[2]^2/2)*t
  sl <- sqrt(t)*theta[2]
  lik <- dlnorm(x, meanlog = ml, sdlog = sl, log=TRUE) 
  if(!log)
    lik <- exp(lik)
  return(lik)
}
BS.lik <- function(theta1,theta2) {
  n <- length(X)
  dt <- deltat(X)
  -sum(dcBS(x=X[2:n], t=dt, x0=X[1:(n-1)], theta=c(theta1,theta2), log=TRUE))
}

fit=mle(BS.lik,start=list(theta1=1,theta2=1),method="L-BFGS-B",lower=c(0.00001 ,0.000001))
mu=coef(fit)[1]
sigma=coef(fit)[2]
```

c. According to the Black-Scholes framework and using the probabilistic approach, compute the fair value for $C_0$?

d. Write a R code to compute $C_0$ using the Black-Scholes-Merton formula.

```r
BS_call <- function (S0,K,T,r,sigma){
  d1 <- (log(S0/K)+(r+0.5*sigma^2)*T)/(sigma*sqrt(T)) 
  d2 <- d1- sigma*sqrt(T)
  opt.val <- S0*pnorm(d1)-K*exp(-r*T)*pnorm(d2) 
  return(opt.val)
}

BS_call (S0=X[1],K=62,T=5-0.5,r=0.08,sigma=sigma*sqrt(252))
```

```
#>   theta2 
#> 42.04235
```

e. Compare the obtained result with that of binomial pricing method.

```r
European_call_binomial=function(T, t,r, X,N,S0,sigma){ 
  delta_t=(T-t)/N
  u = exp(sigma*sqrt(delta_t))
  d = exp(-sigma*sqrt(delta_t))
  p = (exp(r * delta_t) - d)/(u - d) ### probability of up move 
  Df = exp(-r * (T-t)) ### discounting factor
  Ce=0;
  for (i in 1:(N+1)){
    Ce =Ce+choose(N,i-1)*p^{i-1}*(1-p)^{N+1-i}*max(S0*u^{i-1}*d^{N-i+1}-X,0)
    }
return(Df*Ce)
}

European_call_binomial(T=5, t=0.5,r=0.08, X=62,N=1000,S0=X[1],sigma=sigma*sqrt(252))
```

```
#>   theta2 
#> 42.04177
```

# Risk Neutral Pricing AR
