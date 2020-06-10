# Online Deep Attractor Network

## Estimation of source assignment at time $t$

$$
\hat{\mathbf{Y}}_t = Softmax(\mathbf{A}_{t-1}\mathbf{V}_t)
\tag{ODANet.4}
$$

## Attractor estimation at time $t$
$$
\hat{\mathbf{a}}_{t,i} = \frac{
\hat{\mathbf{y}}_{t,i} \mathbf{V}_t^T
}{
\sum_{f}\hat{\mathbf{y}}_{t,i}
}
\quad i = 1,2, \ldots, C
\tag{ADANet.7}
$$

## Context-based weighting

$$
\begin{aligned}
            \mathbf{a}_{t,i} & =
            \frac{\sum_{j=t-\tau}^t \hat{\mathbf{y}}_{j,i} \mathbf{V}_j^T}
            {\sum_{j=t-\tau}^t \sum_f \hat{\mathbf{y}}_{j,i}}
            \\
            & =
            \frac{\sum_{j=t-\tau}^{t-1} \hat{\mathbf{y}}_{j,i} \mathbf{V}_j^T
            + \hat{\mathbf{y}}_{t,i} \mathbf{V}_t^T}
            {\sum_{j=t-\tau}^t \sum_f \hat{\mathbf{y}}_{j,i}}
            \\
            & \approx
            \frac{
            \mathbf{a}_{t-1,i} \sum_{j=t-\tau}^{t-1} \sum_f \hat{\mathbf{y}}_{j,i}
            + \hat{\mathbf{a}}_{t,i} \sum_f \hat{\mathbf{y}}_{t,i}}
            {\sum_{j=t-\tau}^t \sum_f \hat{\mathbf{y}}_{j,i}}
            \\
            & :=
            (1 - \alpha_{t,i}) \mathbf{a}_{t-1,i} + \alpha_{t,i}\hat{\mathbf{a}}_{t,i}
\end{aligned}
$$

## Update coefficient

$$
\begin{aligned}
    \alpha_{t,i} & =
    \frac{\sum_f \hat{\mathbf{y}}_{t,i}}
    {\sum_{j=t-\tau}^t \sum_f \hat{\mathbf{y}}_{j,i}} &
\end{aligned}
\tag{ODANet.10}
$$

# Dynamic weighting
$$
\boldsymbol{\alpha}_{t,i} =
\frac{
    \mathbf{g}_{t,i} \cdot \sum_f \hat{\mathbf{y}}_{t,i}
}{
    \mathbf{f}_{t,i}
    \cdot
    \sum_{j=t-\tau}^{t-1} \sum_f \hat{\mathbf{y}}_{j,i}
    +
    \mathbf{g}_{t,i}
    \cdot
    \sum_f \hat{\mathbf{y}}_{t,i}
}
\tag{ODANet.11}
$$
## Forget
$$
    \mathbf{f}_{t,i} =
    \sigma(
    \mathbf{h}_{t-1}
    \mathbf{W}_\mathrm{f}
    +
    \mathbf{x}_t
    \mathbf{U}_\mathrm{f}
    +
    \mathbf{a}_{t-1}
    \mathbf{J}_\mathrm{f}
    +
    \mathbf{b}_\mathrm{f}
    )
$$
## Gate
$$
    \mathbf{g}_{t,i} =
    \sigma (
        \mathbf{h}_{t-1}
        \mathbf{W}_\mathrm{g}
        +
        \mathbf{x}_t
        \mathbf{U}_\mathrm{g}
        +
        \mathbf{a}_{t-1}
        \mathbf{J}_\mathrm{g}
        +
        \mathbf{b}_\mathrm{g}
    )
$$

| Symbol                  | Description                                      | Dimension                 |
| ----------------------- | ------------------------------------------------ | ------------------------- |
| $\mathbf{h}_{t-1}$      | Output of last LSTM layer at time $t-1$          | $\mathbb{R}^{1 \times H}$ |
| $\mathbf{W}_\mathrm{f}$ | Training Parameter of ODANet's Dynamic weighting | $\mathbb{R}^{H \times K}$ |
| $\mathbf{W}_\mathrm{g}$ | Training Parameter of ODANet's Dynamic weighting | $\mathbb{R}^{H \times K}$ |
| $\mathbf{x}_t$          | Feature vector containing magnitude spectrogram $\vert X(f,t) \vert$ at time $t$  |  $\mathbb{R}^{1 \times F}$ |
| $\mathbf{U}_\mathrm{f}$ | Training Parameter of ODANet's Dynamic weighting | $\mathbb{R}^{F \times K}$ |
| $\mathbf{U}_\mathrm{g}$ | Training Parameter of ODANet's Dynamic weighting | $\mathbb{R}^{F \times K}$ |
| $\mathbf{a}_{t-1,i}$    | Attractor point for speaker $i$ at time $t-1$    | $\mathbb{R}^{1 \times K}$ |
| $\mathbf{J}_\mathrm{f}$ | Training Parameter of ODANet's Dynamic weighting | $\mathbb{R}^{K \times K}$ |
| $\mathbf{J}_\mathrm{g}$ | Training Parameter of ODANet's Dynamic weighting | $\mathbb{R}^{K \times K}$ |
| $\mathbf{b}_\mathrm{f}$ | Training Parameter of ODANet's Dynamic weighting | $\mathbb{R}^{1 \times K}$ |
| $\mathbf{b}_\mathrm{g}$ | Training Parameter of ODANet's Dynamic weighting | $\mathbb{R}^{1 \times K}$ |

###### tags: `danet-equations` `Masterarbeit` `ODANet`

