- Adjacency matrix of different parings of oppression, with value encoding a "preference" for one group over another

$\mathcal{O_C}$ is the opposition matrix for a particular context $C$

The $i$th row and column matches to a particular oppression group, so we have labeling function
$$L: \left[1, ..., n\right] \mapsto c \in \mathcal{H}$$for a category $c$ and hierarchy set $\mathcal{H}$

For basics, we can ignore intersectional identities

$$\forall i: \mathcal{O}_{i,i} = \mathcal{I}$$ for an identity value $\mathcal{I}$. We also have 
$$\forall i,j: \mathcal{O}_{i,j} *^{-1} \mathcal{O}_{j,i} = \mathcal{I}$$ for some binary operation $*$. Specifically, for $*$, $*^{-1}$ is its inverse such that
$$(a * b) *^{-1} b = a$$

 
 Ideally, we'd be able to generate this matrix from a vector
 $$\mathcal{V} = \begin{bmatrix} \mathfrak{p}_1 \\ \mathfrak{p}_2 \\ \vdots \\ \mathfrak{p}_n \end{bmatrix}$$
 for a "preference" $\mathfrak{p}_i$
 We'd then be able to generate $\mathcal{O}$ by
 $$\mathcal{O}_{i,j} = \mathcal{V}_i * \mathcal{V}_j$$
 Or
 $$\mathcal{O} = \mathcal{V} * \mathcal{V}^\intercal$$
 This is consistent with our properties above, as long as we extrapolate from the identity definition to define
 $$x *^{-1} x = \mathcal{I}$$
Which further implies
$$x = x * \mathcal{I}$$


This obviously satisfies the first property, and the second follows from
$$\mathcal{O}_{i,j} *^{-1} \mathcal{O}_{j,i} = (\mathcal{V}_i * \mathcal{V}_j) *^{-1} ( \mathcal{V}_j * \mathcal{V}_i) $$
$$ = (\mathcal{V}_i * \mathcal{V}_j) * \mathcal{V}_j * \mathcal{V}_i$$

## Raw Opposition 

The Raw data opposition matrix encodes the direct rates for one side vs the other. For our legal context, we can have the row be plantiff identity and the column be defendant

So we have a matrix $\mathcal{R}$ where $\mathcal{R}_{i,j}$ represents the percentage of cases with plaintiff $i$ and defendant $j$ that $i$ won. This means we don't have our reciprocal property, and have more freedom to determine the combining function

## Manipulations

One way we can rewrite this data is to compare the relative win rate to the same-identity win rate. What that means is that if we have matrix $\mathcal{R}$, we can make the "comparison" matrix $\mathcal{C}$ through

$$\mathcal{C}_{i,j} = \frac{\mathcal{R}_{i,j}}{\mathcal{R}_{j,j}}$$
This has the nice property that $$\forall i: \mathcal{C}_{i,i} = 1$$

