
$$\newcommand{\EX}[1]{\mathbb{E}\left[{#1}\right]}$$
$$\newcommand{\Prob}[1]{\mathbb{P}\left({#1}\right)}$$
Consider a set of points distributed along the x and y axes with PDFs $f_X(x)$ and $f_Y(y)$, CDFs $F_X(x)$ and $F_Y(y)$, centers $\mu_X$ and $\mu_Y$, and scaling factors $\sigma_X$ and $\sigma_Y$

$$\EX{h} = \sum_{k=1}^n \Prob{p_k \notin \mathcal{H}_{k-1}} $$


$$\Prob{p_k \notin \mathcal{H}_{k-1}} = 1 - \Prob{p_k \in \mathcal{H}_{k-1}}$$
$$\Prob{p_k \in \mathcal{H}_{k-1}} = \frac{1}{2\pi}\int_0^{2\pi} \Prob{p < \max P_\theta} \mathop{d\theta}$$
$$\Prob{p_k \in \mathcal{H}_{k-1}} = \frac{1}{2\pi}\int_0^{2\pi} \frac{\EX{\max(\{P_1, P_2, \dots, P_n\})}}{\sigma_\theta} \mathop{d\theta}$$

$$F_\theta(r) = F_X(x)F_Y(y)$$
$$\Prob{p_k \in \mathcal{H}_{k-1}} = \frac{1}{2\pi}\int_0^{2\pi} \frac{\EX{\max(\{\frac{X_n-\mu_Y}{\sigma_Y}\})} \EX{\max(\{\frac{Y_n-\mu_Y}{\sigma_Y}\})}}{\sigma_X\sigma_Y} \mathop{d\theta}$$
Above feels a little suspect
### Example:

Let $\mathbf{X}, \mathbf{Y} \sim U[0,1]$

$$\EX{\max(\{\frac{X_n - \mu_X}{\sigma_X}\})} = \int_{-\infty}^\infty x\frac{n}{\sigma_X}F_X(\frac{X_n - \mu_X}{\sigma_X})^{n-1}f(\frac{X_n - \mu_X}{\sigma_X})\mathop{dx}$$

This can be made a definite integral, by noting that before $x = \mu_X$, $f(x + \mu_X) = 0$, and same with $x = \sigma_X + \mu_X$. Therefore, 

$$\int_{\mu_X}^{\sigma_X + \mu_X} x\frac{n}{\sigma_X}F_X(\frac{X_n + \mu_X}{\sigma_X})^{n-1}f(\frac{X_n + \mu_X}{\sigma_X})\mathop{dx} = \left. \left( xF_X(\frac{X_n + \mu_X}{\sigma_X})^n - \frac{\sigma_XF(\frac{X_n + \mu_X}{\sigma_X})^{n+1}}{n+1} \right) \right\rvert_{\mu_X}^{\sigma_X + \mu_X}$$
$$\left. \left( xF_X(\frac{X_n + \mu_X}{\sigma_X})^n - \frac{\sigma_XF(\frac{X_n + \mu_X}{\sigma_X})^{n+1}}{n+1} \right) \right\rvert_{\mu_X}^{\sigma_X + \mu_X} = \sigma_X + \mu_X - \frac{\sigma_X}{n+1}$$
Since this value doesn't depend on the value of $x$, it equals $\EX{\max(\{\frac{Y_n+\mu_Y}{\sigma_Y}\})}$, so we have

$$\Prob{p_k \in \mathcal{H}_{k-1}} = \frac{1}{2\pi}\int_0^{2\pi} \left( \frac{\EX{\max(\{\frac{X_n-\mu_Y}{\sigma_Y}\})} }{\sigma_X} \right)^2 \mathop{d\theta}$$
\
$$\Prob{p_k \in \mathcal{H}_{k-1}} = \frac{1}{2\pi}\int_0^{2\pi} \left( \frac{\sigma_X + \mu_X - \frac{\sigma_X}{n}}{\sigma_X} \right)^2 \mathop{d\theta}$$

$$\Prob{p_k \in \mathcal{H}_{k-1}} = \frac{1}{2\pi}\int_0^{2\pi} \left( 1 + \frac{\mu_X}{\sigma_X}- \frac{1}{n} \right)^2 \mathop{d\theta}$$
$$\Prob{p_k \in \mathcal{H}_{k-1}} = \left. \frac{\theta}{2\pi}\left( 1 + \frac{\mu_X}{\sigma_X}- \frac{1}{n}  \right)^2 \right \rvert_0^{2\pi}$$

$$\Prob{p_k \in \mathcal{H}_{k-1}} = \left( 1 + \frac{\mu_X}{\sigma_X}- \frac{1}{n}  \right)^2$$
$$\Prob{p_k \notin \mathcal{H}_{k-1}} = 1 - \left( 1  + \frac{\mu_X}{\sigma_X}- \frac{1}{n} \right)^2$$
$$\EX{h} = \sum_{k=1}^n 1 - \left( 1 + \frac{\mu_X}{\sigma_X}- \frac{1}{n} \right)^2$$



### Identities

$$\EX{\max(\{\frac{X_n - \mu_X}{\sigma_X}\})} = \left . \left( xF_X(\frac{X_n - \mu_X}{\sigma_X})^n \right) \right\rvert_{a}^b - \int_a^b F(\frac{X_n - \mu_X}{\sigma_X})^n \mathop{dx} = b - \int_a^b F(\frac{X_n - \mu_X}{\sigma_X})^n \mathop{dx}$$
Where $a = \sigma_XF^{-1}(0) + \mu_X$, and $b = \sigma_XF^{-1}(1) + \mu_X$

For $F(x) \sim U$, $F^{-1}(0) = 0$ and $F^{-1}(1) = 1$. For $F(x) \sim \mathcal{N}$, $F^{-1}(0) = -\pi\sqrt{2}$ and $F^{-1}(1) = \pi\sqrt{2}$

