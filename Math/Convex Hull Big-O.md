
New strategy
$$E[h] = \sum_{i=1}^n \mathbb{P}(p_i \notin \mathcal{H}_{i-1})$$
This probability is always decreasing and has an asymptote of 0, so by [[Sums and Big O]],

$$E[h] = \sum_{i=1}^n \mathbb{P}(p_i \notin \mathcal{H}_{i-1}) = \mathcal{O}\left(\int_1^n \mathbb{P}(p_x \notin \mathcal{H}_{x-1}) \mathop{dx}\right)$$

This is still hard, but much more tractable

By the result from normal distributions that $E[h] = \mathcal{O}(\sqrt{\ln{n}})$, we can work our what this looks like for normal distributions
We have (i think)

$$\mathbb{P}(p_x \notin \mathcal{H}_{x-1}) = \mathcal{O}\left(\frac{d}{dn} \sqrt{\ln{n}}\right)$$

$$\mathbb{P}(p_x \notin \mathcal{H}_{x-1}) = \mathcal{O}\left(\frac{1}{x\sqrt{\ln{x}}}\right)$$


