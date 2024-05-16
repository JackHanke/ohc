# Optimal Harvest Constants
When should you harvest your crops in Minecraft, if you were to do so periodically? This turns out to be reliant on the number of "growth stages" a crop has, which we will call $n$. Then, answering our questions for all $n$ is the same as the following optimization problem. 

Let $X_{m,p} \sim B(tm,p)$ be a discrete random variable with parameters $m$ and $p$. Define the following function
$$\Lambda_{m,p}(n) = \max_{t} \frac{1}{t}\mathbb{P}(X_{m,p} \geq n) = \max_{t} \frac{1}{t}\left(1-(1-p)^{mt-n+1}\sum_{k=0}^{n-1}p^k  \binom{mt}{k}\right).$$

Then $\Lambda_{3,2^{-12}}(n)$ is the optimal time to harvest a crop with $n$ growth stages. 

For this problem approximating $X_{m,p}$ with a Poisson random variable  $Y \sim \text{Poisson}(t)$ is appropriate. We then define the corresponding function for $Y$, namely 

$$\lambda(n) = \max_t \frac{1}{t}\mathbb{P}(Y \geq n) = \max_t \frac{1}{t}\left(1-e^{-t}\sum_{k=0}^{n-1}\frac{t^k}{k!}\right)$$

We then have for large $n$ and small $p$

$$\Lambda_{m,p}(n) \approx \frac{1}{mp}\lambda(n).$$

In this project I produce numerical results for solutions, as well as exact expressions for $n=2$ and $n=3$. A video summary of this work can be found [here](https://www.youtube.com/watch?v=p9B3f4fpmwc&t=608s). A shoutout of my work can be found [here](https://www.youtube.com/channel/UCJ8CoXrSZPIVF2nl7Hjn1Pg/community?lb=Ugkxao9J1il0Mg9nF58JjxoNQRgmaNzHjijP). 
