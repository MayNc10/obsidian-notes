- Adjacency matrix of different parings of oppression, with value encoding a "preference" for one group over another

$\mathcal{O_C}$ is the opposition matrix for a particular context $C$

The $i$th row and column matches to a particular oppression group, so we have labeling function
$$L: \left[1, ..., n\right] \mapsto c \in \mathcal{H}$$for a category $c$ and hierarchy set $\mathcal{H}$

For basics, we can ignore intersectional identities

$$\forall i: \mathcal{O}_{i,i} = \mathcal{I}$$ for an identity value $\mathcal{I}$. We also have 
$$\forall i,j: \mathcal{O}_{i,j} * \mathcal{O}_{j,i} = \mathcal{I}$$ for some binary operation $*$. 

 
 Ideally, we'd be able to generate this matrix from a vector
 $$\mathcal{V} = \begin{bmatrix} \mathfrak{p}_1 \\ \mathfrak{p}_2 \\ \vdots \\ \mathfrak{p}_n \end{bmatrix}$$
 for a "preference" $\mathfrak{p}_i$
 We'd then be able to generate $\mathcal{O}$ by
 $$\mathcal{O}_{i,j} = \mathcal{V}_i * \mathcal{V}_j$$
 Or
 $$\mathcal{O} = \mathcal{V} * \mathcal{V}^\intercal$$
 This is consistent with our properties above, as long as we extrapolate from the identity definition to define
 $$x * x = \mathcal{I}$$
This obviously satisfies the first property, and the second follows from
$$\mathcal{O}_{i,j} * \mathcal{O}_{j,i} = (\mathcal{V}_i * \mathcal{V}_j) * ( \mathcal{V}_j * \mathcal{V}_i) $$
$$ = (\mathcal{V}_i * \mathcal{V}_j) * \mathcal{V}_j * \mathcal{V}_i$$
wait this isn't rigorous we have an inverse identity as the diagonal but we need something stronger i think cause we also want our identity to be, yknow, an indeentity. Can it have both these properties?