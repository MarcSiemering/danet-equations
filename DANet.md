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

## Ideal Masks

### Ideal Binary Mask (IBM)
$$
IBM_{i,ft} =
\delta(\vert \mathbf{s}_{i,ft} \vert > \vert \mathbf{s}_{j,ft} \vert)
\quad \forall j \neq i
\tag{ADANet.5}
$$

### IDEAL Ratio Mask (IRM)
$$
IRM_{i,ft} =
\frac{
    \vert \mathbf{s}_{i,ft} \vert
}{
    \sum_{j=1}^C \vert \mathbf{s}_{j,ft} \vert
}
\tag{ADANet.5}
$$

### Wiener-Filter like Mask (WFM)
$$
WFM_{i,ft} =
\frac{
    \vert \mathbf{s}_{i,ft} \vert^2
}{
    \sum_{j=1}^C \vert \mathbf{s}_{j,ft} \vert^2
}
\tag{ADANet.5}
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

## Distance Calculation
$$
\mathbf{d}_i = \mathbf{a}_i \mathbf{V}_i
\quad i = 1,2, \ldots , C
\tag{ADANet.10}
$$

## Mask Calculation
$$
\hat{\mathbf{m}}_i = \mathcal{H}(\mathbf{d}_i)
\quad i = 1,2, \ldots , C
\tag{ADANet.11}
$$

where $\mathcal{H}$ the softmax or sigmoid function applied to each element of $\mathbf{d}_i$

$$
\begin{cases}
Softmax(\mathbf{d}_{i,ft}) = 
\frac{
    \exp(d_{i,ft})
}{
    \sum_{j=1}^C \exp(d_{j,ft})
}
\\
\color{red}
Sigmoid(\mathbf{d}_{i,ft}) = 
\frac{
    1
}{
    \sum_{j=1}^C (1+\exp(-d_{j,ft})
}
\end{cases}
\tag{ADANet.12}
$$

## Loss

$$
l = \frac{1}{C} \sum_i \Vert \mathbf{x} \odot (\mathbf{m}_i - \hat{\mathbf{m}}_i) \Vert_2^2
\tag{ADANet.13}
$$

###### tags: `danet-equations` `Masterarbiet`

