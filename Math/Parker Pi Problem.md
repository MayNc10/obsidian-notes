- How many digits of $\pi$ do you need to know in order to compute $\pi^{\pi^{\pi^\pi}}$ to an integer?

How much precision do you lose?
If we have a value $\alpha$, we can approximate it to $n$ decimal places with
$$\alpha = a + \epsilon$$
$\epsilon < 10^{-n}$

So if we have $\alpha = 1.95622$, and we approximate to the third decimal place, we have $1.95622 = 1.956 + 0.00022$, where $0.00022 < 10^{-3} < 0.001$

We're asking for the number of accurate decimal places in $a^a \approx \alpha^{\alpha}$ 
To start, we can ask about $a^k \approx \alpha^k$ for an integer $k$

$$E = \alpha^k - a^k = \sum_{i=1}^k {k \choose i}a^{k-i}\epsilon^k$$
This gives the exact error between the two expressions. We can get the number of correct decimals by
$$n' = \lfloor -\log_{10}{E} \rfloor$$
Conjecture:
This can be computed exactly by 

$$n' = \left\lfloor -\log\left({(a+10^{-n})^k-a^k}\right)\right\rfloor$$
in order to have an integer approximation, we need $n'$ to be at least 0. We want to know how many digits we need initially, so we solve for $n$
$$n = -\log{\left(\sqrt[k]{a^k+1} -a\right)}$$
Is there any good approximation of this function?
According to Wolfram Alpha (needs proof tho), 
$$\lim_{k\rightarrow\infty} \frac{-\log{\left(\sqrt[k]{a^k+1} -a\right)}}{k} = \frac{\ln(a)}{\ln(10)}$$
$\forall a > 0, \ln(a) > 0$
This implies that $n = \mathcal{O}(x)$, but we want a function that is always greater than n
We want to find constants $m$ and $c$ such that $\forall k$,
$$\frac{m\ln(\pi)}{\ln(10)} + c \ge n$$
Something we can do to make this tractable is to ask for 
$$\max_{k_1>c} \frac{d}{dk}\left[n\right](k_1)$$
Or in other words, we limit the domain of our function to some range that hopefully makes it easier to find this maximum. We then set $m = \max$, and $c = n(k_1)$
Since this function's derivative is always decreasing, an arbitrarily precise approximation can be found by evaluating this function and its derivative anywhere. 
