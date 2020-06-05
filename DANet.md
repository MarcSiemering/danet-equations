# Deep Attractor Network
## Speech Separation Problem
### Mixture in time domain:
$$
x(t) = \sum_{i=1}^C s_i(t)
\tag{ADANet.1}
$$
### Mixture in frequency domain:
$$
X(f,t) = \sum_{i=1}^C S_i(t,f)
\tag{ADANet.2}
$$

---



### Embedding Sapce
$$
\mathbf{V} = f(\mathbf{x}) \in \mathbb{R}^{K \times FT}
\tag{ADANet.6}
$$
$$
\mathbf{V} =
\begin{bmatrix}
V_{1,1}    & \cdots     & V_{1,ft}  \\
\vdots     & \ddots     & \vdots    \\
V_{i,k}     & \cdots    & V_{k,ft}
\end{bmatrix}
$$

---


## Clean estimate of speaker $i$:
$$
\hat{\mathbf{s}}_i = \mathbf{x} \odot \mathbf{m}_i
\tag{ADANet.3}
$$
with $\odot$ element-wise multiplication and
$$
\sum_{i=1}^C\mathbf{m}_i(f,t)=1 \quad \forall f,t
\tag{ADANet.4}
$$

---

## Attractor Calculation
$$
\mathbf{a}_i = \frac{
\mathbf{y}_i \mathbf{V}^T
}{
\sum_{f,t}\mathbf{y}_i
}
\quad i = 1,2, \ldots, C
\tag{ADANet.7}
$$

---

## Threshold Vector calculation
$$
\mathbf{w}_{ft} = 
\begin{cases}
1, & \text{if} \quad \mathbf{x}_{ft} > \rho \\
0, & \text{else}
\end{cases}
\tag{ADANet.8}
$$

## Attractor Calculation with Salient Weight Threshold
$$
\mathbf{a}_i = \frac{
(\mathbf{y}_i \odot \mathbf{w}) \mathbf{V}^T
}{
\sum_{f,t}(\mathbf{y}_i \odot \mathbf{w})
}
\quad i = 1,2, \ldots, C
\tag{ADANet.9}
$$
