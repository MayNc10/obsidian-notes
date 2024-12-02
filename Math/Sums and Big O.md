$$\sum_{i=a}^n f(i) = \mathcal{O}(\int_a^n f(x) \mathop{dx})$$

$$f(x) = \mathcal{O}(g(x)) \implies \exists x_0, M: \forall x \ge x_0, \left|f(x)\right| \le M\left| g(x)\right|$$
We have a left Riemann sum, so we have that

$$\left|\int_a^n f(x) \mathop{dx} - \sum_{i=a}^n f(i) \right| \le \frac{f(M)(n-a)^2}{2n} $$where $f(M)$ gives the maximum value for $\left|f\right|$ within the domain.

Since we especially care about monotonically decreasing functions, let's use those properties

$$\sum_{i=a}^n f(i) - \int_a^n f(x) \mathop{dx} \le \frac{f(a)(n-a)^2}{2n} $$
From this general formula, we can't make much progress

However, if we also enforce that $f$ approaches an asymptote, we can do better

Specifically, what we enforce is that
- $f(i + \alpha) \le f(i)$
- $f(i + \beta) - f(i + \alpha) \le f(i + 1) - f(i)$
- $\alpha, \beta > 0$
Essentially, the difference between consecutive values decreases
For our left-hand sum, we always have that
$$f(i) - \int_i^{i+1} f(x)\mathop{dx} \le f(i) - f(i+1)  $$
$$\sum_{i=a}^n f(i) - \int_a^n f(x) \mathop{dx} = \sum_{i=a}^n \left( f(i) - \int_i^{i+1}f(x)\mathop{dx} \right) \le \sum_{i=a}^n \left(f(i) - f(i+1)\right) = 
f(a) - f(n+1)$$

$$\sum_{i=a}^n f(i) \le \int_a^n f(x) \mathop{dx} + f(a) - f(n+1)$$
We already said that $f$ was asymptotic, we can specify that

$$\lim_{x \rightarrow \infty} f(x) = \kappa$$

$$\sum_{i=a}^n f(i) \le \int_a^n f(x) \mathop{dx} + f(a) - f(n+1) \le \int_a^n f(x) \mathop{dx} + f(a) - \kappa$$
A standard identity that will not be proves here is that $\mathcal{O}(g(x) + c) = \mathcal{O}(g(x))$
Therefore, we have that

$$\sum_{i=a}^n f(i) \le \int_a^n f(x) \mathop{dx} + f(a) - \kappa \implies f(n) = \mathcal{O}(\int_a^n f(x)\mathop{dx} - \kappa) = \mathcal{O}\left(\int_a^n f(x)\mathop{dx}\right)$$

This holds for any monotonically decreasing, asymptotic function


