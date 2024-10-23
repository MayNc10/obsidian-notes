$$n \in \mathbb{Z} > 1 = 3i \cdot 2j$$
$$3^i \cdot 2^j \ge n, \;\; i, j \in \mathbb{Z}$$
So what are $i$ and $j$?
Well, we have two options - maximize $i$ by computing it first, or maximize $j$ in the same way
### Maximize $i$
What is the maximum value that $i$ can take? 
First, let's express $n$ in terms of how $3$ divides it
$$n = 3\bigg\lfloor\frac{n}{3}\bigg\rfloor + n \mod_3$$
We can now calculate $i$ by consider the 3 different options for $n$:
$$n \mod_3 = 0\rightarrow i = \bigg\lfloor\frac{n}{3}\bigg\rfloor= \frac{n}{3}, j = 0$$
$$n = 3\bigg\lfloor\frac{n}{3}\bigg\rfloor + n \mod_3 = 3\bigg\lfloor\frac{n}{3}\bigg\rfloor + 0 = 3\bigg\lfloor\frac{n}{3}\bigg\rfloor$$
$$$$
$$\frac{n}{3} = \bigg\lfloor\frac{n}{3}\bigg\rfloor$$
$$n = 3\bigg\lfloor\frac{n}{3}\bigg\rfloor = 3\frac{n}{3} = 3i, \; i = \frac{n}{3}$$
The next case:

$$n \mod_3 = 2\rightarrow i = \bigg\lfloor\frac{n}{3}\bigg\rfloor, j = 1$$
$$n = 3\bigg\lfloor\frac{n}{3}\bigg\rfloor + (n \mod_3) = 3\bigg\lfloor\frac{n}{3}\bigg\rfloor + 2, \; i = \bigg\lfloor\frac{n}{3}\bigg\rfloor, j=1$$
The final case:
$$n \mod_3 = 1\rightarrow i = \bigg\lfloor\frac{n}{3}\bigg\rfloor - 1, j = 2$$
$$n = 3\bigg\lfloor\frac{n}{3}\bigg\rfloor + (n \mod_3) = 3\bigg\lfloor\frac{n}{3}\bigg\rfloor + 1$$
$$= 3\bigg(\bigg\lfloor\frac{n}{3}\bigg\rfloor - 1\bigg) + 3 +1$$
$$ = 3\bigg(\bigg\lfloor\frac{n}{3}\bigg\rfloor - 1\bigg) + 4$$
$$ = 3\bigg(\bigg\lfloor\frac{n}{3}\bigg\rfloor - 1\bigg) + 2\cdot2 \rightarrow i = \bigg\lfloor\frac{n}{3}\bigg\rfloor - 1, j=2$$
To create a combined formula, we will use a few facts about these cases
Firstly, $i + j = \bigg\lfloor\frac{n}{3}\bigg\rfloor + [(n \mod_3) > 0]$, where the brackets are Iverson brackets.
Secondly, $i = \bigg\lfloor\frac{n}{3}\bigg\rfloor - [(n \mod_3) = 1]$, again using Iverson brackets
We can also write these rules using the Heaverside step function

$$i + j = \bigg\lfloor\frac{n}{3}\bigg\rfloor + H((n \mod_3) - 1)$$
$$i = \bigg\lfloor\frac{n}{3}\bigg\rfloor - H((n \mod_3) - 1) \cdot H(1 - (n \mod_3) )$$
We can also solve for $j$:
$$j = \bigg\lfloor\frac{n}{3}\bigg\rfloor + H((n \mod_3) - 1) - i$$
$$j = \bigg\lfloor\frac{n}{3}\bigg\rfloor + H((n \mod_3) - 1) - (\bigg\lfloor\frac{n}{3}\bigg\rfloor - H((n \mod_3) - 1) \cdot H(1 - (n \mod_3) ))$$$$j = \bigg\lfloor\frac{n}{3}\bigg\rfloor + H((n \mod_3) - 1) - \bigg\lfloor\frac{n}{3}\bigg\rfloor + H((n \mod_3) - 1) \cdot H(1 - (n \mod_3) )$$
$$j = H((n \mod_3) - 1) + H((n \mod_3) - 1) \cdot H(1 - (n \mod_3) )$$
$$j = H((n \mod_3) - 1) \cdot (1 + H(1 - (n \mod_3) ))  $$

Now, what if we calculated $j$ first?
Well, if our goal is to optimize $3^i \cdot 2^j$, we can just prove that having $i > j$ is better than $j > i$
Lets define four powers, $i, j, a, b$ such that
$$3i + 2j = 3a + 2b = n, i > a, b > j$$
$$3(i - a) = 2(b-j), \frac{3}{2}(i - a) = (b-j)$$
Theorem:
$$3^i \cdot 2^j > 3^a \cdot 2^b$$
Proof:
$$3^i \cdot 2^j > 3^a \cdot 2^b$$
$$2^{i\log_2(3)} \cdot 2^j > 2^{a\log_2(3)} \cdot 2^b$$
$$2^{i\log_2(3) + j}> 2^{a\log_2(3) + b}$$
$$i\log_2(3) + j> a\log_2(3) + b$$

$$i\log_2(3) - a\log_2(3) > b - j$$
$$\log_2(3)(i - a) > b - j$$$$\log_2(3)(i - a) > \frac{3}{2}(i-a)$$
$$\log_2(3) > \frac{3}{2}$$
Which is true ($\frac{3}{2} = 1.5, \log_2(3) \approx 1.58$)
Finally, we have to prove that $3^i \cdot 2^j \ge n$

$$3^i \cdot 2^j \ge n$$
$$3^{\frac{n - 2j}{3}} \cdot 2^j \ge n$$
$$3^{n - 2j} \cdot 3^{\frac{1}{3}} \cdot 2^j \ge n$$
$$3^{n - 2j} \cdot \sqrt[3]{3} \cdot 2^j \ge n$$
$$3^{n - 2j} \cdot 2^j \ge \frac{n}{\sqrt[3]{3}}$$
$$3^n \cdot \frac{1}{3^{2j}} \cdot 2^j \ge \frac{n}{\sqrt[3]{3}}$$
$$3^n \cdot \frac{1}{9} \cdot \frac{1}{3^{j}} \cdot 2^j \ge \frac{n}{\sqrt[3]{3}}$$
$$3^n \cdot \frac{1}{9} \cdot \frac{2^j}{3^{j}} \ge \frac{n}{\sqrt[3]{3}}$$
$$3^n \cdot \frac{1}{9} \cdot \frac{2}{3}^j \ge \frac{n}{\sqrt[3]{3}}$$
$$3^n \cdot \frac{2}{3}^j \ge \frac{9n}{\sqrt[3]{3}}$$
The maximum $j$ can be is 2, so we can substitute that in, since it still obeys the inequality
$$3^n \cdot \frac{2}{3}^2 \ge \frac{9n}{\sqrt[3]{3}}$$
$$3^n \ge \frac{3}{2}^2 \cdot \frac{9n}{\sqrt[3]{3}}$$
$$3^n - \frac{3}{2}^2 \cdot \frac{9n}{\sqrt[3]{3}} \ge 0$$
Let us define the above LHS expression to be the function $N(x)$
$$N(x) = 3^x - \frac{3}{2}^2 \cdot \frac{9x}{\sqrt[3]{3}}$$
To prove that the inequality holds for $n>3$, we will prove that $N(4) > 0$ and $N'(x \ge 4) > 0$. Those two facts imply that $N(x \ge 4) > 0$, and so the inequality holds. We will then prove the cases $n = 2$ and $n = 3$, although they are trivial.

First, proving that $N(4) > 0$ is as simple as calculating it
$$N(4) > 0$$
$$N(4) = 3^4 - \frac{3}{2}^2 \cdot \frac{9 \cdot 4}{\sqrt[3]{3}} \approx 24.84$$

$$24.84 > 0$$
Next, we will prove that $N'(x \ge 4) > 0$
$$N'(x) = \frac{d}{dx}\left( 3^x - \frac{3}{2}^2 \cdot \frac{9x}{\sqrt[3]{3}} \right)$$
$$=  \ln(3)3^x - \frac{3}{2}^2 \cdot \frac{9}{\sqrt[3]{3}}$$
Because $3^x$ is a monotonic increasing function, $N'(x)$ is as well, and so if $N'(4) > 0$ then $N'(x \ge 4) > 0$. $N'(4) = \ln(3)3^4 - \frac{3}{2}^2 \cdot \frac{9}{\sqrt[3]{3}} \approx 74.95$, so this is true. Therefore, $N(x \ge 4) > 0$, and so for all $n \ge 4$, $3^i \cdot 2^j \ge n$. For $n = 2$ we clearly have $i = 0, j=1 \rightarrow 3^0 \cdot 2^1 \ge 2 \rightarrow 2 \ge 2$, which is true. Similarly, for $n=3$, we have $i = 1, j = 0 \rightarrow 3^1 \cdot 2^0 \ge 3 \rightarrow 3 \ge 3$, which is again true. Therefore, for all $n \in \mathbb{Z} > 1$, $3^i \cdot 2^j \ge n$.   



Now we can reason about vectors
Suppose we have vector $\vec{v}$, with elements $v_i, v_j \notin \{2,3\}$. We could have $v_i \vert v_j = 1$, but this isn't optimal unless $n = 1$.
Proof:
Let $\vec{\lambda} = [\lambda_a = v_a, \lambda_x], a \notin \{i, j\}, \lambda_x = v_i + v_j$
$$\sum_k \lambda_k = \sum_{k \notin \{i, j\}} \lambda_a + \lambda_x$$
$$= \sum_{k \notin \{i, j\}} v_a + \lambda_x$$
$$= \sum\vec{v} - v_i - v_j + \lambda_x$$
$$= \sum\vec{v} - v_i - v_j + v_i + v_j$$
$$= \sum\vec{v}$$
So this optimization preserves the sum of the vector
Now consider the product
$$\prod_k \lambda_k = \prod_{k \notin \{i, j\}}\lambda_k \cdot \lambda_x$$
$$= \prod_{k \notin \{i, j\}}v_a \cdot \lambda_x$$
$$= \frac{\prod\vec{v}}{v_iv_j} \cdot \lambda_x$$
$$= \frac{\prod\vec{v}}{v_iv_j} \cdot (v_i + v_j)$$
Now, without loss of generality, we can say $v_i = 1$, since at least one of $v_i, v_j$ equals one, and we can re-lable variables
$$= \frac{\prod\vec{v}}{1v_j} \cdot (v_j + 1)$$
$$= \prod\vec{v} \cdot \frac{(v_j + 1)}{v_j}$$
$$= \prod\vec{v} \cdot (1 + \frac{1}{v_j})$$
$$\prod\vec{v} \cdot (1 + \frac{1}{v_j}) > \prod\vec{v}$$
$$\prod\vec{\lambda} \ge \prod\vec{v}$$
Therefore, this manipulation always at minimum  the product of the vector
Now consider a different vector $\vec{v}$ with entry $v_i \notin \{2,3\}, v_i > 1$, or $v_i > 3$
We will show that we can construct a vector $\vec{\lambda}$ with equal sum and greater product.
Let $$\vec{\lambda} = [\lambda_{1 \le k \le x} = \lambda_x, \lambda_{x < k \le y} = \lambda_y, \lambda_{k > y}=  v_{(k-y) + [k\ge i]}]$$
$$\lambda_x = 3, \lambda_y = 2$$

$$x = \bigg\lfloor\frac{v_i}{3}\bigg\rfloor - H((v_i \mod_3) - 1) \cdot H(1 - (v_i \mod_3) )$$
$$y = H((v_i \mod_3) - 1) \cdot (1 + H(1 - (v_i \mod_3) ))  $$


$$\sum_k \vec{\lambda} = \sum_{k=1}^x \lambda_x + \sum_{k=x+1}^{y+x} \lambda_y + \sum_{k>y}\lambda_a$$
$$= \sum_{k=1}^x \lambda_x + \sum_{k=x+1}^{y+x} \lambda_y + \sum_{k>y}v_{(k-y) + [k\ge i]}$$

$$= x\lambda_x + y\lambda_y + \sum\vec{v} - v_i$$
$$= 3x + 2y + \sum\vec{v} - v_i$$
$$= v_i + \sum\vec{v} - v_i$$
$$\sum\vec{v}$$
Therefore, the sum is always preserved

$$\prod_k \vec{\lambda} = \prod_{k=1}^x \lambda_x \cdot \prod_{k=x+1}^{y+x} \lambda_y \cdot \prod_{k>y}\lambda_a$$
$$= \prod_{k=1}^x \lambda_x \cdot \prod_{k=x+1}^{y+x} \lambda_y \cdot \prod_{k>y}v_{(k-y) + [k\ge i]}$$
$$= \lambda_x^x \cdot \lambda_y^y \cdot \frac{\prod\vec{v}}{v_i}$$$$\ge v_i \cdot \frac{\prod\vec{v}}{v_i}$$$$\ge \prod\vec{v}$$
Therefore, the product is always at least the original product. We can apply this to our original vector until there all the entries are either $3$ or $2$, and we can calculate $x$ and $y$ based on these formula:
$$x_\infty = \bigg\lfloor\frac{n}{3}\bigg\rfloor - H((n \mod_3) - 1) \cdot H(1 - (n \mod_3) )$$
$$y_\infty = H((n \mod_3) - 1) \cdot (1 + H(1 - (n \mod_3) )) $$
These are optimal by the above proofs. 

This all means that if you are given an optimal vector for an $n$, you can always write that vector as a sequence of 3s and 2s, and you know how many of each by the above values. This lets us calculate the product of the optimal vector $\vec{\lambda}^\infty$ summing to $n$
$$\prod_k (\lambda^\infty)_k = \prod_{k=1}^{x_\infty}\lambda_x \cdot \prod_{k=x_\infty + 1}^{y_\infty + x_\infty}\lambda_y$$
$$= \prod_{k=1}^{x_\infty}3 \cdot \prod_{k=x_\infty + 1}^{y_\infty + x_\infty}2$$
$$= 3^{x_\infty} \cdot 2^{y_\infty}$$
$$= 3^{\big\lfloor\frac{n}{3}\big\rfloor - H((n \mod_3) - 1) \cdot H(1 - (n \mod_3) )} \cdot 2^{H((n \mod_3) - 1) \cdot (1 + H(1 - (n \mod_3) ))}$$
This gives the maximum product for a vector that sums to $n$