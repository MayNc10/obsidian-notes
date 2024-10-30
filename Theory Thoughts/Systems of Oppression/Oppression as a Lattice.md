## Definitions

Let $H$ be a set of hierarchies $h \in H$. Each $h$ is a set $c \in h$. Let there be a general measuring function $\mu(c)$, and a function measuring average material conditions $M(\mu(c))$. For clarity, we also define 
$$h^{-1}(c) = h: c \in h$$
For simplicity, define the following notation
$$c_1 > c_2 \implies M(\mu(c_1)) > M(\mu(c_2))$$
$$c_1 = c_2 \implies M(\mu(c_1)) = M(\mu(c_2))$$
And the rest of the ordering notation, using those definitions
## Lattice

A lattice is an algebraic structure $(L, \lor, \land)$. $L$ is a partially set. In our case, $L$ is a set of $\{c \dots\}$ sets, representing a certain "type" of individual, described in terms of their oppression categories. We omit a category $c$ from the oppression set $C$ if $\forall \kappa \in h^{-1}(c) - \{c\}, c > \kappa$. Additionally, there is only one category in any hierarchy present in $C$. 
We also have the functions $\lor$ and $\land$, which much satisfy certain properties described below

### Properties of $\lor$ and $\land$

$$a \lor b = b \lor a$$
$$a \land b = b \land a$$
$$(a \lor b) \lor c = a \lor (b \lor c)$$
$$(a \land b) \land c = a \land (b \land c)$$
$$a \lor (a \land b) = a$$
$$a \land (a \lor b) = a$$
$$a \lor a = a$$
$$a \land a = a$$
### Satisfactory functions

We define $C_1 \lor C_2$ as such:

$$C_1 \lor C_2 = \{c \in h^{-1}(C_1) \cap h^{-1}(C_2) :  \forall \kappa \in (C_1 \cup C_2) \cap h^{-1}(c), c \ge \kappa \}$$where $+$ denotes the symmetric difference

We define $C_1 \land C_2$ as such:
$$C_1 \land C_2 = \{c \in h^{-1}(C_1) + h^{-1}(C_2)\}\cup \{c \in h^{-1}(C_1) \cap h^{-1}(C_2) :  \forall \kappa \in (C_1 \cup C_2) \cap h^{-1}(c), c \le \kappa \}$$

Informally, $C_1 \lor C_2$ is the set of oppression categories applicable to both $C_1$ and $C_2$, picking the higher-ranked oppression when the categories aren't equal, while $C_1 \land C_2$ is the set of oppression categories applicable to either $C_1$ or $C_2$, picking the lower-ranked oppression when the categories aren't equal. 

Now we set out to prove that these operations satisfy the requirements for $\lor$ and $\land$. The first four requirements are obviously satisfied; they encode the properties of associativity and commutativity, and all operations in the definitions satisfy these properties. The last two requirements are implied from 5 and 6, so we set out to prove those requirements.

$$a \lor (a \land b) = a$$
Firstly, it is easy to see that the left hand side contains all $c \in a - b$, and contains no $c \in b - a$. The first comes from the fact that $(a \land b)$ contains all $c \in a - b$ (by the union of the symmetric difference). That difference is then intersected with $a$ in the definition of $c$ in the set builder notation, which leaves the difference unchanged. All $c$ in this difference satisfy the requirement function on the right hand side of the set builder notation, since all $\kappa \in a - b$, and there exists only one $c \in h$ in $a - b$. Therefore, $\kappa = c$. 
Next, we must show that the left hand side contains all categories with hierarchies in both sets, and all those categories are in $a$. More clearly, if we let $\mathcal{L} = a \lor (a \land b)$,
$$\forall c \in h^{-1}(a) \cap h^{-1}(b): c \in \mathcal{L}, c \in a$$
Consider any one $c \in h^{-1}(a) \cap h^{-1}(b) \cap a$. Clearly, because $c \in h^{-1}(b), \exists c' \in b: c' \in h^{-1}(a)$ (essentially, because $c$ is in the intersection of the hierarchies of both sets, there is a complementary $c'$ in $b$, also in the hierarchies of both sets). It is also clear that $a \land b$ contains one of $c, c'$. If $c = c'$, then $c \in a \land b$ and $c \in a$, so $c \in \mathcal{L}$. Now, if $c \ne c'$, then $c > c'$ because of the requirement function .This means $c' \in a \land b$  and $c \notin a \land b$. When we go to test whether $c$ should be in $\mathcal{L}$, we compare it to $c'$. We just supposed that $c \gt c'$, so this means that $c$ will satisfy our test. 

$$a \land (a \lor b) = a$$The proof is much the same, with the difference that $c \ne c'$ implies $c < c'$, but the consequences are the same, 

