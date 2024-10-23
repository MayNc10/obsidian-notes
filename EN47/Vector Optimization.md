In this homework, we were presented with a fairly simple problem:
Find $\arg\max \prod_i \vec{v}$ where $\vec{v} = \left[ v_1, v_2, \dots, v_i\right]$ such that $v_i \in \mathbb{N}, v_i \ge$ 1 and $\sum_i \vec{v} = n$. I investigated this problem, but first, warmed up with a simpler problem, relaxing the $v_i \in \mathbb{N}$ constraint to $v_i \in \mathbb{R}$.

## Real Elements
$$\DeclareMathOperator*{\argmax}{argmax}$$
### Element Value Equality

Firstly, we can argue that the optimal vector for a given $n$ can always be written such that all the elements are equal. We can prove this by contradiction. 

Suppose we had an optimal vector $\vec{v}$, with elements $v_a \ne v_b$. We will show that we can create a new vector $\vec{\lambda}$, which has at least the same product. et $p = \prod_i \vec{v}$. We can say that $\prod_i \vec{\lambda} = \frac{p}{v_iv_j} \cdot {\lambda_i \lambda_j}$. Therefore, $\frac{\prod_i \vec{\lambda}}{p} = \frac{\frac{p}{v_iv_j} \cdot \lambda_i \lambda_j}{p} = \frac{\lambda_i \lambda_j}{v_iv_j}$. 
To prove that $\prod_i \vec{\lambda} > \prod_i \vec{v}$, we can prove that $\frac{\lambda_i \lambda_j}{v_iv_j} > 1$.
#### Proof:
$$\frac{\lambda_i \lambda_j}{v_iv_j} > 1$$$$\frac{{(\frac{v_i+v_j}{2})}^2}{v_iv_j} > 1$$
$$\frac{{(v_i+v_j)}^2}{4v_iv_j} > 1$$
$${(v_i+v_j)}^2 > 4v_iv_j$$
$$v_i^2 + 2v_iv_j + v_j^2 > 4v_iv_j$$
$$v_i^2 -2v_iv_j + v_j^2 > 0$$
$$(v_i - v_j)^2 > 0$$
Since $v_i \ne v_j$, $v_i - v_j$ cannot be 0, therefore its square will always be greater than 0.
This proves that the optimal list has all elements equal. 

### Element Value

Since we know that every element of the optimal vector $\vec{v}$ is the same, we can solve for the value of each element
$$\sum_{k=1}^l v_k = n$$
$$\sum_{k=1}^l v_i = n$$
$$lv_i = n$$
$$v_i = \frac{n}{l}$$
### Vector Length

The final thing to determine is the optimal length. Since we know that all elements of the vector all the same, we now have a simple expression for the term we want to maximize
$$\prod_i \vec{v} = \prod_i v_i = v_i^l = \left(\frac{n}{l}\right)^l$$
To optimize this term, we can use simple calculus. Let $f(x) = \left(\frac{n}{x}\right)^x$. To find the extrema, we just find the zeroes of $f'(x)$
$$f'(x) = \frac{d}{dx} \left(\frac{n}{x}\right)^x$$$$= \frac{d}{dx}\left( e^{x\ln{\frac{n}{x}}} \right)$$
$$= e^{x\ln{\frac{n}{x}}} \cdot (\ln{\left(\frac{n}{x}\right)}-1)$$
Now we set this to $0$
$$e^{x\ln{\frac{n}{x}}} \cdot (\ln{\left(\frac{n}{x}\right)}-1) = 0$$
$$\ln{\left(\frac{n}{x}\right)}-1 = 0$$
$$\ln{\left(\frac{n}{x}\right)} = 1$$
$$\frac{n}{x} = e$$
$$x = \frac{n}{e}$$
$l$ must be an integer, so we can say that $l = \text{round}(\frac{n}{e})$
This gives us our final vector
$$\vec{v} = [v_1, v_2, \dots, v_l]$$
such that $l = \text{round}(\frac{n}{e})$ and for $i \in \mathbb{N}$ and $1 \le i \le l$, $v_i = \frac{n}{l}$

### A definition of $\text{round}(x)$

In the above formula, we use a rounding function $\text{round}(x)$. We will now define this function for rigor. 
$$\text{round}(x): \mathbb{R} \rightarrow \mathbb{Z} = \begin{cases} \lfloor x \rfloor & \text{if } x - \lfloor x \rfloor < \frac{1}{2}\\ \lceil x \rceil & \text{if } x - \lfloor x \rfloor > \frac{1}{2}\end{cases}$$$\text{round}(x)$ is not defined for $x = w \in \mathbb{Z} + \frac{1}{2}$, but this is not a problem for our use case. 
Suppose we did have an undefined value for $\text{round}(x)$ in our formulas. The only use of $\text{round}(x)$ is in $l = \text{round}(\frac{n}{e})$, so that would imply that 
$$\text{round}\left(\frac{n}{e}\right) = \text{undefined}$$
$$\frac{n}{e} = \bigg\lfloor\frac{n}{e}\bigg\rfloor + \frac{1}{2}$$
$$\frac{n}{e} = \frac{2\left\lfloor\frac{n}{e}\right\rfloor + 1}{2}$$
$$n = e\frac{2\left\lfloor\frac{n}{e}\right\rfloor + 1}{2}$$
$$e = n\frac{2}{2\left\lfloor\frac{n}{e}\right\rfloor + 1}$$
This would imply that $e \in \mathbb{Q}$, since it equals the ratio of 2 whole numbers. However, $e$ is known to be transcendental, and thus $e \notin \mathbb{Q}$. Therefore, we will never run into the edge case for $\text{round}(x)$; it will always be defined for our inputs. 

## Natural Elements

While all the above is perhaps interesting (for some definitions of the the word, anyway), it isn't very relevant to the actual questioned posed, which restricts the elements to natural numbers. We will take a similar approach in our proof, but we still need to start on new ground. With that said, we will first consider some facts about natural numbers. Specifically, we will rely on the fact that 
$$\forall n \in \mathbb{Z} > 1, \exists i,j \in \mathbb{Z} \; \text{where} \; n = 3i \cdot 2j \; \text{and} \; 3^i \cdot 2^j \ge n$$
We will find formulas for $\argmax_{i,j} 3^i \cdot 2^j$.  
Firstly, we will show that to maximize this expression, we want to make $i$ as large as possible
#### Proof:

Define four natural numbers, $i, j, a, b$ such that
$$3i + 2j = 3a + 2b = n, i > a, b > j$$
Since $i > a$, we want to show that  $3^i \cdot 2^j > 3^a \cdot 2^b$

$$3^i \cdot 2^j > 3^a \cdot 2^b$$
$$2^{i\log_2(3)} \cdot 2^j > 2^{a\log_2(3)} \cdot 2^b$$
$$2^{i\log_2(3) + j}> 2^{a\log_2(3) + b}$$
$$i\log_2(3) + j> a\log_2(3) + b$$

$$i\log_2(3) - a\log_2(3) > b - j$$
$$\log_2(3)(i - a) > b - j$$$$\log_2(3)(i - a) > \frac{3}{2}(i-a)$$
$$\log_2(3) > \frac{3}{2}$$
Which is true ($\frac{3}{2} = 1.5, \log_2(3) \approx 1.58$)
This means that to optimize the product, we optimize $i$. 
Next, we need to prove that $3^i \cdot 2^j \ge n$.


#### Proof:
$$3^i \cdot 2^j \ge n$$
$$3^{\bigg\lfloor\frac{n}{3}\bigg\rfloor - H((n \mod_3) - 1) \cdot H(1 - (n \mod_3) )} \cdot 2^{H((n \mod_3) - 1) \cdot (1 + H(1 - (n \mod_3) )) } \ge n$$
$$3^{\bigg\lfloor\frac{n}{3}\bigg\rfloor} \cdot 3^{-H((n \mod_3) - 1) \cdot H(1 - (n \mod_3) )}
\cdot 2^{H((n \mod_3) - 1) \cdot (1 + H(1 - (n \mod_3) ))  } \ge n$$
$$3^{\left\lfloor\frac{n}{3}\right\rfloor} \ge \frac{3^{H((n \mod_3) - 1) \cdot H(1 - (n \mod_3) )}}{2^{H((n \mod_3) - 1) \cdot (1 + H(1 - (n \mod_3) ))  }}n$$
$\max \frac{3^{H((n \mod_3) - 1) \cdot H(1 - (n \mod_3) )}}{2^{H((n \mod_3) - 1) \cdot (1 + H(1 - (n \mod_3) ))  }} = 1$, so we can simplify our bound

$$3^{\left\lfloor\frac{n}{3}\right\rfloor} \ge n$$
$$3^{\left\lfloor\frac{n}{3}\right\rfloor} -n \ge 0$$
This is true $\forall n \ge 6$. 
