{% include mathjax.html %}

# Distributed Algorithms for Connectivity and MST in Large Graphs with Efficient Local Computation

We study distributed algorithms for large-scale graphs, focusing on the
fundamental problems of connectivity and minimum spanning tree (MST). We
consider the $k$-machine model, a well-studied model for distributed
computing for large-scale graph computations, where $k \geq 2$ machines
jointly perform computations on graphs with $n$ nodes (typically, $n \gg
k$). The input graph is assumed to be initially randomly partitioned among
the $k$ machines, a common implementation in many real-world systems.
Communication is point-to-point, and the goal is to minimize the number of
\emph{communication rounds} (denoted $T_c$) of the computation.

While communication is a significant factor that affects the time needed for
large-scale computations, the \emph{computation cost} incurred by the
individual machines also contributes to the overall time complexity of the
distributed algorithm. We posit a complexity measure called the \emph{local
computation cost} (denoted $T_{\ell}$) that measures the worst-case local
computation cost among the machines.  A lower bound for $T_{\ell}$
in our model is $\bigOm{\sfrac{(m+n)}{k} + \Delta + k}$, while a
lower bound on $T_c$ is $\bigOm{\sfrac{n}{k^2}}$ [Klauck et al., SODA 2015],
where $m$ is the number of edges and $\Delta$ is the maximum degree. Prior
algorithms for connectivity and MST in the $k$-machine model [Klauck et al.,
SODA 2015, Pandurangan et al., SPAA 2016] do not take into account local
computation; a straightforward local implementation of these algorithms is
not optimal with respect to local computation.

In this paper, we study several distributed algorithms for connectivity and
MST and analyze their performance with respect to \emph{both} the computation and
communication cost. In particular, we analyze a well-studied flooding
algorithm for connectivity and connected components that takes
$\softO{n/k + D}$ rounds and $\softO{m / k + \Delta + k}$
local computation time.\footnote{$\tilde{\mathcal{O}}$ notation hides
$\operatorname{polylog}(n)$ multiplicative and additive factors.} We then
present a deterministic filtering algorithm that has an improved
round complexity of $\softO{\sfrac{n}{k}}$ but local computation
complexity of $\softO{\sfrac{m}{k} + n}$. Next, we present two
\emph{deterministic} algorithms which are increasingly sophisticated
implementations of the classical Bor\r{u}vka's algorithm, the last of which
has round complexity $\softO{\sfrac{n}{k}}$ and local computation
complexity $\softO{\sfrac{(m + n)}{k} + \Delta + k}$. We finally
present a \emph{randomized} algorithm to find connected components with
round complexity $\softO{\sfrac{n}{k^2}}$ and local computation
complexity $\softO{\sfrac{(m + n)}{k} + \Delta + k}$ that are
both essentially optimal (up to polylogarithmic factors).
