- NN data can be thought of as a probability distribution
- NN training is fitting a manifold to these points
- The more correspondence there is between data, the lower dimension this manifold is

Consider a 2D case to make it simple
input is $x$, output is $y$
In this case, we're fitting a curve

Say we have an underlying distribution $P$. $P$ is actually 3D, because for each input, we have a probability of it taking different values

(Should $P(x)$ be a PDF, CDF, or something else)

We also have our observation set $\mathcal{O} = \{(x_1, y_1), (x_2, y_2), \dots\}$
We finally have our neural net estimator function, $E(x)$. $E(x)$ produces a single value, the best guess of the network

Questions:
- How can we quantify $E(x)$'s "performance"?
- What is the "best" that $E(x)$ can do in general? What is the best it can do on the dataset?
- How does the performance of $E$ change with changes to $P$?
- How does the performance of $E$ change with changes to $O$?
- How does this work when $E$ takes a vector of input, or produces a vector of output?

Start by investigating classification nets
	[[Classification Nets]]
