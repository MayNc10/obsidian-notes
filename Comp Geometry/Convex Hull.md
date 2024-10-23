$$E[h] = ?$$

Assume $X, Y \sim U[0,1]$
$$h \approx \log(n) \approx \sum_{n=1}^x \frac{1}{n} \approx \sum_{n=1}^x \left(1 - \left(1 - \frac{2}{n}\right)^2\right)$$
$$E[h] = \sum_{i=1}^n P(p_i \notin \mathcal{H})$$
$$P(p_i \notin \mathcal{H}) = \text{supp}(U)^2 - E[A_{i-1}] = 1 - E[A_{i-1}]$$
Estimate the shape of the convex hull as a square (why is this valid?)

Then we have
$$E[A_{i-1}] = E[l_{i-1}]^2$$

So what is the estimated value of the side length?
Well, the lengths of the box span the minimum and maximum of the distribution. After $n$ points, $E[\max(\{p_i\})] = \frac{n}{n+1}$, so the area not covered is $\frac{1}{n+1}$, and this is also true for the minimum (just the other way), so we have 
$$E[l] = 1 - E[\min] - E[\max] = 1 - \frac{2}{i+1}$$
This is then squared to calculate the final area
$$E[A] = \left(1-\frac{2}{i+1}\right)^2$$
Plugging this all in, we get

$$P(p_i \notin \mathcal{H}) = 1 - \left(1-\frac{2}{i}\right)^2$$
Then, we get our final result

$$E[h] = \sum_{i=1}^n 1 - \left(1-\frac{2}{i}\right)^2$$

We can also simply this a little more

$$E[h] = n - \sum_{i=1}^n \left(1-\frac{2}{i}\right)^2$$
$$E[h] = n - \sum_{i=1}^n \left(1 - \frac{4}{i} + \frac{4}{i^2}\right)$$
$$E[h] = n - n - \sum_{i=1}^n \left(-\frac{4}{i} + \frac{4}{i^2}\right)$$
$$E[h] = 4\sum_{i=1}^n \left(\frac{1}{i} - \frac{1}{i^2}\right)$$
$$E[h] = 4\left(\sum_{i=1}^n \frac{1}{i} - \sum_{i=1}^n  \frac{1}{i^2} \right)$$

$$E[h] = 4\left(H_n - \sum_{i=1}^n  \frac{1}{i^2} \right)$$

$\sum_{n=1}^x \frac{1}{n^2} \approx \frac{\pi^2}{12}\left(2-\frac{1}{x}\right)$, so

$$E[h] = 4\left(H_n - \frac{\pi^2}{12}\left(2-\frac{1}{n}\right)\right)$$
$$E[h] = 4H_n - \frac{\pi^2}{3}\left(2-\frac{1}{n}\right)$$
Experimentally, we find that this function needs some linear scaling and shifting, but the general formula is the same. 
If we decide to take out the convergent reciprocal, we get $E[h] \approx H_n$. The interesting thing about this is that 
$$H_n = \mathcal{O}(\log{n})$$
This demonstrates why our initial approximation of $E[h]$ was based on a logarithm - the logarithm is an acceptable estimate for the $n$th harmonic number. 
