Let $X$ be a random variable under distribution $P$.

Thoughts

Let $A = \{a_1, a_2, a_3, \dots\}$, where $a$ is a random variable drawn from a probability distribution $\mathcal{A}$.  Let there also be a function $g: \mathbb{R} -> [0, 1] \subseteq \mathbb{R}$
What is $P(g(a) = X)$ for $a \in A$?
Well, lets answer a superset of this question
What is $$ P(card(\{ a \in A \mid g(a) = X\}) = n)$$where $0 \le n \le card(A)$

this is too hard, lets make it easier

 $$ P(card(\{ a \in A \mid g(a) \le X\}) = n)$$
Because sets have no order, we can order the elements of $A$, and therefore say
 $$ P(card(\{ a \in A \mid g(a) \le X\}) = n) = \prod_{i = 1}^n P(g(a_i) \le X) \prod_{i = n + 1}^{card(A)} P(g(a_i) \gt X)$$
 $$\prod_{i = n + 1}^{card(A)} P(g(a_i) \gt X) =  \prod_{i = n + 1}^{card(A)} 1 - P(g(a_i) \le X)$$
Lets define a new probability distribution, $G$, such that $P(X_G \in E) = P(g(X_A) \in E)$, where $X_A$ is a random variable drawn $\mathcal{A}$. This means that $F_G(x) = P(g(X_A) \le x)$, where $F_G$ is the CDF of $G$. Therefore, 
$$\prod_{i = 1}^n P(g(a_i) \le X) \prod_{i = n + 1}^{card(A)} 1 - P(g(a_i) \le X) = \prod_{i = 1}^n F_G(X) \prod_{i = n + 1}^{card(A)} 1 - F_G(X)$$
Now, I'm definitely missing some nuance (i always am), but ...
$$\prod_{i = 1}^n F_G(X) \prod_{i = n + 1}^{card(A)} 1 - F_G(X) = F_G(X)^n(1 - F_G(X))^{card(A) - n}$$
Can we simplify $F_G(X)$? Or express it a different way

$F_G(x) = P(g(X_A) \le x) = P(X_A \le g^{-1}(x))$ 

Now, using the same logic, we can say
 $$ P(card(\{ a \in A \mid g(a) \gt X\}) = n) = P(card(\{ a \in A \mid g(a) \le X\}) = card(A) - n)$$
 $$P(card(\{ a \in A \mid g(a) \gt X\}) = n) = F_G(X)^{card(A) - n}(1 - F_G(X))^n$$

EXAMPLE
$P = U[0,1], \mathcal{A} = U[0,1], g(x) = x^2, n = card(A) = 10$

$$ P(card(\{ a \in A \mid g(a) \le X\}) = 10)$$

$$ P(card(\{ a \in A \mid g(a) \le X\}) = 10) = P(X_{\mathcal{A}}^2 \le X_P)^{10} $$
$$P(X_{\mathcal{A}}^2 \le X_P)^{10} = P(X_{\mathcal{A}} \le \sqrt{X_P})^{10}$$
Maybe this works?
for $x \sim U(0, 1)$, $P(X_{\mathcal{A}} \le \sqrt{x}) = F(\sqrt{x}) = \sqrt{x}$ Just evaluate for all numbers in the distribution, or $\int_0^1 \sqrt{x} dx = \frac{2}{3}$ 

THIS DOESN'T TAKE INTO ACCOUNT DISCREETNESS!!