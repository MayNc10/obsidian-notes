$c$: A category of person
	$C$: a set of categories
$h$: A hierarchy of categories
	$h = {c_1, c_2, ...}$
	$h^n$: The $n$th level of a hierarchy, where $n=0$ represents the dominant category
		$h^n = c \in h : \left| \; \{c_1 \in h \setminus \{c\} \vert P(c_1, c) > 0\} \; \right| = n$
		This definition means that it is possible there is no $h^0$, if  $P(h^0, h') = 0$
		 This definition requires that there are no categories of equal power, or in other terms $\nexists c_1, c_2 \in h: P(c_1, c_2) = 0$
	$h'$: Any category $C$ for which if $h^n$ = $C$, $n \ne 0$
	 These functions can also be applied to a set of hierarchical categories $H$
	 A hierarchy is "existent" if there is a nonzero power differential between its dominant category and any other. 
		 $h$ is existent if $P(h^0, h') \ne 0$. 
		 $h$ is existent if $\exists h^0$
$P(c_1, c_2)$: The power differential function between two categories
	One can also write $P(h)$, which is shorthand for $P_i(h^0, h')$
$\Delta P$: A given power differential, equivalent to $P(c_1, c_2)$  
	The power differential represents how much power $c_1$ has over $c_2$ under the current system of discussion. 
$\Delta P_i$: An intersectional power differential, equivalent to $P_i(C_1, C_2)$  

An intersectional power differential is computed from categories via
$$\Delta P_i = P_i(C_1, C_2)  $$
One can also write $P_i (H)$, which is shorthand for $P_i (H^0, H')$

What can we say about $P_i$?
Well, we can name some laws it must obey:
1. for all $H$ where $\exists h \in H :$ $\exists h^0$,  $P_i\left(H  \right) > 0$. If for any reason a power differential of an intersectional oppression equals 0, the power differential still must exist, so it cannot be zero. 
	- ex: If racism was dismantled in the United States, Black women (targets of misoginoir) would still face oppression
	- Can we make a stronger claim, that $P_i(H) = P_i(H_1 : \{ h \in H \mid \exists h^0 \} )$? In other words, can we reduce a set of hierarchies to only existent ones? IDK, read Crenshaw and figure it out 
2. $P_i (\{  h_1 ,\; h_2,\; \dots \}^0 \cup \{ h_a,\; h_b,\; \dots \}', \; \{  h_1 ,\; h_2,\; \dots \}' \cup \{ h_a,\; h_b,\; \dots \}') \ne P_i (\{ h_1,\; h_2,\; \dots \}^0, \; \{ h_1,\; h_2,\; \dots \}')$
	 - ex: Trans men and Trans women both face transphobia, but trans men still oppress trans women through transmisogyny, not just misogyny. 
	 - This means that the sets passed to $P_i$ cannot be "deduplicated", and evaluation of $P_i$ must happen all at once, on all the categories at the same time. 
 3. $P_i(H) > P(h)$ for all $h \in H$
 4. $P_i (\{  h_1^0 ,\; h_2' \}, \; \{ h_1' ,\; h_2' \}) \; ?= P_i (\{  h_1^0 ,\; h_2^0 \}, \; \{ h_1' ,\; h_2' \})$
	 1. Is this true? Does misoginoir have the same weight coming from a black man as a white man? I would assume so, since it's not like a black woman has more recourse against a black man than a white man. Read crenshaw!
 5. If one individual is oppressed less than another, the first can oppress the send
