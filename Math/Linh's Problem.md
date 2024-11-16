- Graph of polyminoes -> two graphs, front and back 
$$G, G'$$
$G_i$ and $G'_i$ are on opposite sides
So $G_i'' = G_i$

Define $F_G(\mathcal{F})$ on a subset $\mathcal{F} \in G$, such that 
$$\forall f \in \mathcal{F}, \exists!\bar{f} \in N(f), \bar{f}\notin \mathcal{F}$$ $$\mathcal{\overline{F}} = \{\bar{f} \mid f \in \mathcal{F}\}$$
$F_G(\mathcal{F}) = \bar{G}$, which satisfies the following properties
$$G_i \in \mathcal{F} \implies \nexists\bar{G_i}$$
$$G_i \in \overline{\mathcal{F}} \implies \bar{G_i} = G'_i$$
Then we can prove some properties
Firstly, we prove that 
$$\exists\mathscr{G}: \mathscr{G} = \{G_i\}, \mathscr{G'} = \{G_j \mid G_j \in N(G_i)\}$$
NOT DONE: prove we can reduce to by folding things away
$$\exists\bar{\mathscr{G}} : \bar{\mathscr{G}} = \{G_i, G_j\}$$
Uhh we prob need to change our definition, since we could have a 3x3 square with a hole in the center, which has weird folding properties (in particular it makes a new square appear in the center). The reduction property still holds afaik. 

Then $F_\bar{\mathscr{G'}}(\{G'_j\}) = \mathscr{G}$
We remove $\bar{\mathscr{G}}'_j$ from $\bar{\mathscr{G}}''$. We then set $\bar{\mathscr{G}}'_i = \bar{\mathscr{G}}''_j = \bar{\mathscr{G}}_j = G_j$ So then we have a set just containing $G_j$, and its reverse just containing $G_i$, therefore $\mathscr{G}$.

We then ask, for a particular $G_i$, for which $G_j$ is there a $G_k \in N(G_j)$ such that applications of $F$ can take $G -> \bar{G}$, where $G_j = G_i, G_j \in N(G_k)$

### Simple Non-Looping Graphs

A non-looping graph $G$ is a graph where $\forall G_i, G_j$ that are connected, $\exists! G_k$ such that in $G - G_k$, $G_i$ and $G_j$ aren't connected. "Connected" in this case is just the general graph theory notion of two vertexes having some path between them. We can also say that there does not exist some $\bar{G}$ reachable from $G$ through $F$ such that $\nexists G_a \in \bar{G}, G_a = G_k$ but $\exists G_n,m, G_n = G_i, G_m = G_j$. This implies that there is only one path from $G_i$ to $G_j$. 

1. We can always map any $G_i$ to $G_j$ 


What's a better formal definition of our set?

