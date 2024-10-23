#### Goodhart's Law: 
"When a measure becomes a target, it ceases to be a good measure"

#### One interpretation
The way I interpret this adage is that optimizing a system based on a measure will fail as people will rig the measure

### Expression

$$\exists \mathbf{x} \in B : \forall\mathbf{x}_i \in B, f(\mathbf{x}) > f(\mathbf{x}_i) \implies \exists\psi \notin B: f(\psi) > f(\mathbf{x})$$
Where $B$ represents the bounds on the input variable $\mathbf{x}$, and $f$ is the function to optimize. This states that as long as there exists an optimal input to $f$ *within* $B$, there will be a more optimal input to it *outside* $B$. 

This is a corollary to the original statement - what it means to "cease to be a good measure" is that it no longer represents the *idea* the system was trying to optimize for. It has been gamed to represent something else, i.e. free markets *should* optimize for the best products and best prices, but in fact lead to a number of degenerate cases like monopolies (and a whole bunch of others). This is encapsulated in the idea that we expect $\mathbf{x}$ to exist within $B$ - $B$ represents the rules the system should play by. This theorem states that actually, these rules will be broken in order to achieve a more optimal result. $\psi$ is not an input (or a behavior) "allowed" by the system, but it will be observed anyway. 
  