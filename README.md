# Stochastic Block Model
Python implementation of the Belief Propagation algorithm to find marginals of the SBM.

Implements the BP equations:

```math
\begin{aligned}
Y_{s_i}^{j \rightarrow i} &= \sum_{s_j} C_{s_j,s_i} \chi_{s_j}^{j \rightarrow i}\\
\log \chi_{s_i}^i &= \underbrace{\log n_{s_i} - h_{s_i} + \sum_{j \in \partial i} \log Y^{j \rightarrow i}_{s_i}}_{\log \tilde \chi_{s_i}^i} - \log Z^i\\
\log \chi_{s_i}^{i \rightarrow j} &=\begin{cases}
    \log \chi_{s_i}^i + \mathcal{O}(\frac 1N) \quad& \text{if } (i,j)\notin E \\
    \log \tilde \chi_{s_i}^i - \log Y_{s_i}^{j \rightarrow i} - \log Z^{i \rightarrow j} \quad& \text{if } (i,j) \in E
\end{cases}\\
h_{s_i} &= \frac 1 N \sum_k \sum_{s_k} C_{s_k,s_i} \chi_{s_k}^k
\end{aligned}
```

More documentation in `hw2.ipynb`

Homework for [Staticial physics of computation](https://edu.epfl.ch/coursebook/en/statistical-physics-of-computation-PHYS-512) class.
