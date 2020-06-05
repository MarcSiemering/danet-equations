# Anchored DANet

## Anchor points
$$
\mathbf{b}_j=
\begin{bmatrix}b_{j1} & \cdots & b_{jk} \end{bmatrix}
\in \mathbb{R}^{1 \times K}
\quad \text{with} ~ j=1,\ldots,N
$$

## Possible anchor point combinations ${N \choose C}$
$$
\mathbf{L}_p \in \mathbb{R}^{C \times K}
\quad \text{with}~ p=1, \ldots {N \choose C}
$$

## Distance between Anchors and Embedding Points
$$
\mathbf{D}_p = \mathbf{L}_p\mathbf{V}
$$

## Estimation of Speaker Assignment
$$
\hat{\mathbf{Y}}_p = softmax(\mathbf{D}_p)
$$

## Chosing Attractor combination set with largest distance between attractors. 
> The set with the minimum in-set similarity (i.e. largest in-set
distance between attractors) is selected for mask estimation.
$$
\mathbf{S}_p = \mathbf{A}_p\mathbf{A}_p^T, \quad \mathbf{S}_p \in \mathbb{R}^{C \times C}
$$
$$
s_p = \max \lbrace (s_{p_{ij}}) \rbrace, \quad i \neq j
$$
$$
\hat{\mathbf{A}} = \underset{\mathbf{A}_p}{\operatorname{argmin}} \lbrace (s_{p}) \rbrace, \quad p=1,2, \ldots, {N \choose C}
$$
where $s_p$ is a scalar that epresents the maximum similarity
between any two attractors in $\mathbf{A}_p$ and $\mathbf{A} \in \mathbb{R}^{C \times K}$ is the set set of attractors with smallest in-set similarity among all ${N \choose C}$ attractor sets. Given the attractors $\mathbf{A}$, the mask estimation is done in the same manner as equation 10 & 11.

For more details see: [Understanding the use of in-set similarity in ADANet](https://hackmd.io/s65GzDjySUep9M5EXfwryw?view#Understanding-the-use-of-in-set-similarity-in-ADANet)