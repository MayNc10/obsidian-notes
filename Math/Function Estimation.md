We have a function $f(x)$ which is continuous

Point version:
We are given a set of observations $O = {(x_i, f(x_i))}$. How can we best estimate $f(x)$?
Lets call our estimation function $E(x)$

## Estimators: 

### Pi Estimator
$$E(x) = \prod_i (\prod_{j \ne i} (x - x_j))(x - x_i + y_i)$$

### Distance Exponent Estimator
$$ E(x) = \sum_i \frac{f(x_i)}{a^{(x-x_i)^2}}$$
$a \ge 1$

### Closest Value Estimator
$$E(x) = f(x_m)$$
$m = \arg\min_O \left| x - x_i\right|$

