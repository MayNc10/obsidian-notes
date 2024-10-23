$$\DeclareMathOperator*{\argmin}{argmin}$$
# Comparing Comparisons
How many comparisons does Merge sort use vs. Insertion sort?

Let $L$ represent a list of length $n$, such that $1 \le L_{1\le i\le n} \le n$, $\nexists L_i, L_{j \ne i}$ such that $= L_i = L_j$. 
$L_i$ represents the "goal" index for the element at $i$, or in other words, where in a sorted list the element at $i$ would occur. 
Add more guarantees!
Define $$f(i) = i - L_i$$
### Properties of $f$
1. 
$$\sum_{i=1}^n f(i) = 0$$
This is true as long as the list can be sorted, because a sorted list has an $f$ sum of 0, and any swapping of two elements in the list preserves the sum of their $f$ values.
2. $$i - n \le f(i) \le i-1$$
The largest possible value for $L_i$ is $n$, and the minimum is $1$, so this theorem follows. 

### Merge Sort
The number of comparisons using Merge sort is defined as
$$M(n, L) = \mu(n, L, 0, n)$$
Where $$\mu(L, s, l) = \mu(L, s, \bigg\lceil\frac{l}{2}\bigg\rceil) + \mu(L, s + \bigg\lceil\frac{l}{2}\bigg\rceil, \bigg\lfloor\frac{l}{2}\bigg\rfloor) + C_\mu(L, s, l)$$
last term is the smallest index in one of the lists such that all elements for which the last element of the other list is smaller than it
We can change the order we compare in to make that term larger if we compute which one to use not based on any element in it

$$C_\mu(L, s, l) = \vert \{ i \mid i \in \mathbb{N}, s + \bigg\lceil\frac{l}{2}\bigg\rceil\le i \lt s + l, \forall j\in \mathbb{N}, s \le j \lt s + \bigg\lceil\frac{l}{2}\bigg\rceil: L_i \ge L_j \}\vert$$

We can also define $M$ without recursion, by noting that each use of $\mu$ uses two invocations of $\mu$, called on half as small a sample space
$$M(n, L) = \sum_{i=1}^{\lceil \log_2(n) \rceil} \left(\sum_{j=0}^{2^{i-1} - 1} C_\mu\left(L, j\bigg\lfloor\frac{n}{2^{i-1}}\bigg\rfloor + 1, \bigg\lfloor\frac{n}{2^{i-1}}\bigg\rfloor + [j=2^{i-1}-1] \right) \right)$$

### Insertion Sort
The definition for insertion sort is much simpler
$$I(n, L) = \sum_{i=2}^n 1+f_L(i)H(f_L(i)) = (n-1) + \sum_{i=2}^n f_L(i)H(f_L(i))$$
We can rewrite this to even simpler terms using properties of $f$

$$I(n, L) = (n-1) + \sum_{i=2}^n f_L(i)H(f_L(i))$$
$$= (n-1) -f_L(i)H(f_L(i)) + \sum_{i=1}^n f_L(i)H(f_L(i))$$
$$= (n-1) -f_L(i)H(f_L(i)) + \sum_{i=1}^n f_L(i)H(f_L(i))$$
$\sum_{i=1}^n f_L(i)H(f_L(i))$ is the sum of all the positive elements of $f_L$, since all negative elements are zeroed out. The total sum of the elements of $f_L$ is zero, so we know that 
$$\sum_{i=1}^n f(i) = 0$$
$$\sum_{i=1}^n f_L(i)H(f_L(i)) + \sum_{i=1}^n f_L(i)H(-f_L(i)) = 0$$
$$\sum_{i=1}^n f_L(i)H(f_L(i)) + \sum_{i=1}^n f_L(i)H(-f_L(i)) = 0$$
$$\sum_{i=1}^n f_L(i)H(f_L(i)) = -\sum_{i=1}^n f_L(i)H(-f_L(i))$$
$$\sum_{i=1}^n f_L(i)H(f_L(i)) = \sum_{i=1}^n \vert f_L(i) \vert H(-f_L(i))$$
$$\sum_{i=1}^n f_L(i)H(f_L(i)) + \sum_{i=1}^n \vert f_L(i) \vert H(f_L(i)) = \sum_{i=1}^n \vert f_L(i) \vert H(-f_L(i)) + \sum_{i=1}^n \vert f_L(i) \vert H(f_L(i))$$
$$2\sum_{i=1}^n f_L(i)H(f_L(i))  = \sum_{i=1}^n \vert f_L(i) \vert H(-f_L(i)) + \vert f_L(i) \vert H(f_L(i))$$
$$2\sum_{i=1}^n f_L(i)H(f_L(i))  = \sum_{i=1}^n \vert f_L(i) \vert(H(-f_L(i)) + H(f_L(i)))$$
$$2\sum_{i=1}^n f_L(i)H(f_L(i))  = \sum_{i=1}^n \vert f_L(i) \vert$$
$$\sum_{i=1}^n f_L(i)H(f_L(i))  = \frac{\sum_{i=1}^n \vert f_L(i) \vert}{2}$$Plugging that back in, we get
$$I(n, L)= (n-1) -f_L(i)H(f_L(i)) + \frac{\sum_{i=1}^n \vert f_L(i) \vert}{2}$$
Using the fact that $\max f(1) = 0$ , we get that

$$I(n, L)= (n-1)  + \frac{\sum_{i=1}^n \vert f_L(i) \vert}{2}$$

### Heap Sort

Heap sort works in two stages. The first orders the elements of the array to satisfy the max heap property, and the second swaps the first (largest) element of the heap with the last in the array, and then repairs the array. We can view the comparisons as two functions

$$H(n, L) = H_1(n, L) + H_2(n, L)$$
$H_1$ is the heap creation function, and we'll consider that first

#### Heap Creation

The procedure for creating the heap is fairly simple. For each element, from the end to the beginning, swap it with it's children until they satisfy the heap property (i.e., all of it's children are larger than their parents, and the left child is always less than or equal to the right node)

A general outline for the formula is 
$$H_1(n, L) = \sum_{i=0}^{n-1} 2 \cdot (\vert \{ j \mid j \in \mathcal{C_{n - i}}, L[j] \gt L[n - i] \}\vert + 1)$$where $\mathcal{C}_a$ denotes the set of all children of the heap node at index $a$. 
The set $\mathcal{C}_a$ can be derived by noting the pattern in each level of the tree. The first children are $2a + 1, 2a + 2$, the second set of children are $4a + 3, \dots, 4a+6$, the third set are $8a + 7, \dots, 8a + 14$, the fourth set are $16a + 15, \dots, 16a + 26$, and in general the bounds for the $i$th set of children are $2^ia + 2^i - 1, \dots, 2^ia + 2(2^i  -1)$.  