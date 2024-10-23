- stuff about mapping traits to categories
- we see big jumps in material conditions over small jumps in trait for heirarchies
- ... anything else?
	- violce is necessary to maintain seperation of categories


$$|\mathcal{T} = \{\tau \mid M'(\mu(\tau))^2 > \delta\}| > 0 \rightarrow \exists h_c, \;C = \mu(\mathcal{T})$$for some "significant" $\delta$. (Make this more rigorous!)

More rigorous definition:
Let $\rho(f)$ denote the set of the local maxima of $f$ (this has been rigorously defined elsewhere in the literature). We will then construct a new set, $\sigma(f)$, of the "significant" local maxima. We define $\sigma(f)$ to be the smallest subset of $\rho(f)$ such that 
$$0 < \frac{\sum \rho_i - \sum \sigma_i}{\sum \rho_i} \ll 1$$
In other words, it is the smallest subset of $\rho(f)$ such that the difference between the total sum of the local maxima and this subset is very close to 0. 

Then, we can state the first theorem as
$$\exists \sigma(M'(\mu(\tau))^2) \rightarrow \exists h_c$$

Where $$C_1 = \arg\max \frac{-1}{\min \sigma^{-1}(f) - \tau_{0}}, C_{i+1} = \arg\max \frac{1}{\sigma^{-1}(f)_i - \tau_{0}}$$
Where $\sigma^{-1}$ denotes the set of significant argmaxima, and $\tau_0 \in \{\tau \mid M'(\mu(\tau))^2 = 0\}$ 

The above is unfortunately not adequate, as it operates incorrectly on a $M$ with no significant changes
