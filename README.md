<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
# Abstract
We study distributed algorithms for large-scale graphs, focusing on the
fundamental problems of connectivity and minimum spanning tree (MST). We
consider the $$k$$-machine model, a well-studied model for distributed
computing for large-scale graph computations, where $$k \geq 2$$ machines
jointly perform computations on graphs with $$n$$ nodes (typically, $$n \gg
k$$). The input graph is assumed to be initially randomly partitioned among
the $$k$$ machines, a common implementation in many real-world systems.
Communication is point-to-point, and the goal is to minimize the number of
\emph{communication rounds} (denoted $$T_c$$) of the computation.

While communication is a significant factor that affects the time needed for
large-scale computations, the *computation cost* incurred by the
individual machines also contributes to the overall time complexity of the
distributed algorithm. We posit a complexity measure called the *local
computation cost* (denoted $$T_{\ell}$$) that measures the worst-case local
computation cost among the machines.  A lower bound for $$T_{\ell}$$
in our model is $$\Omega\left((m+n) / k + \Delta + k\right)$$, while a
lower bound on $$T_c$$ is $$\Omega\left(n / k^2\right)$$ [Klauck et al., SODA 2015],
where $$m$$ is the number of edges and $$\Delta$$ is the maximum degree. Prior
algorithms for connectivity and MST in the $$k$$-machine model [Klauck et al.,
SODA 2015, Pandurangan et al., SPAA 2016] do not take into account local
computation; a straightforward local implementation of these algorithms is
not optimal with respect to local computation.

In this paper, we study several distributed algorithms for connectivity and
MST and analyze their performance with respect to *both* the computation and
communication cost. In particular, we analyze a well-studied flooding
algorithm for connectivity and connected components that takes
$$\tilde{\mathcal{O}}\left(n/k + D\right)$$ rounds and $$\tilde{\mathcal{O}}\left(m / k + \Delta + k\right)$$
local computation time.`[^1]`{=markdown} We then
present a deterministic filtering algorithm that has an improved
round complexity of $$\tilde{\mathcal{O}}\left(n / k\right)$$ but local computation
complexity of $$\tilde{\mathcal{O}}\left(m / k + n\right)$$. Next, we present two
*deterministic* algorithms which are increasingly sophisticated
implementations of the classical Bor\r{u}vka's algorithm, the last of which
has round complexity $$\tilde{\mathcal{O}}\left(n / k\right)$$ and local computation
complexity $$\tilde{\mathcal{O}}\left((m + n) / k + \Delta + k\right)$$. We finally
present a *randomized* algorithm to find connected components with
round complexity $$\tilde{\mathcal{O}}\left(n / k^2\right)$$ and local computation
complexity $$\tilde{\mathcal{O}}\left((m + n) / k + \Delta + k\right)$$ that are
both essentially optimal (up to polylogarithmic factors).

`[^1]:`{=markdown} $$\tilde{\mathcal{O}}$$ notation hides $$\operatorname{polylog}(n)$$ multiplicative 
and additive factors.
