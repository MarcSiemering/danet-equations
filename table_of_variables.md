# Table of Variables

| Symbol         | Description                                  | Dimension                          |
| -------------- | -------------------------------------------- | ---------------------------------- |
| $\mathbf{a}_i$ | Attractor point for speaker $i$              |  $\mathbb{R}^{1 \times K}$         |
| $\mathbf{a}_{t,i}$ | Attractor point for speaker $i$ at time $t$  |  $\mathbb{R}^{1 \times K}$     |
| $\mathbf{A}_p$ | Attractors for combination $p$ (ADANet)      |  $\mathbb{R}^{C \times K}$         |
| $\mathbf{A}_t$ | Attractors at time $t$ (ODANet)              |  $\mathbb{R}^{C \times K}$         |
| $\alpha_{t,i}$ | Contexted-based update coefficient for speaker $i$'s attractor at time $t$ (ODANet) |  $\mathbb{R}$ |
| $\boldsymbol{\alpha}_{t,i}$ | Dynamic weighted update coefficient for speaker $i$'s attractor at time $t$ (ODANet) |  $\mathbb{R}^{1 \times K}$ |
| $\mathbf{b}_j$ | Anchor point number $j$                      |  $\mathbb{R}^{1 \times K}$         |
| $C$            | Number of Speakers                           |  $\mathbb{N}$                      |
| $\mathbf{D}_p$ | Distance between Embedding Points and Anchor point combination $p$  |  $\mathbb{R}^{C \times FT}$ |
| $F$            | Number of frequency bins                     |  $\mathbb{N}$                      |
| $f$            | Frequency index                              |  $\mathbb{N}$                      |
| $\mathbf{f}_{t,i}$ | Forget Gate (ODANet, Dynamic Weighting)  |  $\mathbb{R}^{1 \times K}$         |
| $\mathbf{g}_{t,i}$ | Gate (ODANet, Dynamic Weighting)         |  $\mathbb{R}^{1 \times K}$         |
| $H$            | Output dimension of last LSTM layer          | \mathbb{N}                         |
| \mathbf{h}_{t-1} | Output of last LSTM layer at time $t-1$    | \mathbb{R}^{1 \time H}             |
| $i$            | Speaker index                                |  $\lbrace 1,2, \ldots , C \rbrace$ |
| $j$            | Anchor point index                           |  $\lbrace 1,2, \ldots , N \rbrace$ |
| $K$            | Embedding dimension                          |  $\mathbb{N}$                      |
| $l$            | Loss                                         |  $\mathbb{R}$                      |
| $\mathbf{L}_p$ | Anchor point combination $p$                 |  $\mathbb{R}^{C \times K}$         |
| $\mathbf{m}_i$ | Mask for speaker $i$                         |  $[0,1]^{1 \times FT}$             |
| $\hat{\mathbf{m}}_i$ | Estimated mask for speaker $i$         |  $[0,1]^{1 \times FT}$             |
| $p$            | Anchor point combination index               |  $\lbrace 1,2, \ldots , {N \choose C} \rbrace$ |
| $\rho$         | Threshold for the log magnetude spectrogram  |  $\mathbb{R}$                      |
| $s_i(t)$       | Speaker source number $i$ in time domain     |  $\mathbb{R}$                      |
| $S_i(f,t)$     | Speaker source number $i$ in frequency domain |  $\mathbb{C}$                     |
| $\mathbf{s}_i$ | Magnitude clean spectrogram $\vert S_i(f,t) \vert$ of speaker source number $i$  |  $\mathbb{R}^{1 \times FT}$ |
| $\hat{\mathbf{s}}_i$ | Estimated magnitude spectrogram of the source $i$  |  $\mathbb{R}^{1 \times FT}$ |
| $T$            | Number of time frames                        |  $\mathbb{N}$                      |
| $t$            | Time index                                   |  $\mathbb{N}$                      |
| $\mathbf{V}$   | Embedding                                    |  $\mathbb{R}^{K \times FT}$        |
| $\mathbf{V}_t$ | Embedding at time $t$  (ODANet)              |  $\mathbb{R}^{K \times F}$         |
| $\mathbf{w}$   | Threshold vector                             |  $\{0,1\}^{1 \times FT}$           |
| $X(f,t)$       | Mixture in frequency domain                  |  $\mathbb{C}$                      |
| $\mathbf{x}$   | Feature vector containing magnitude spectrogram $\vert X(f,t) \vert$  |  $\mathbb{R}^{1 \times FT}$ |
| $x(t)$         | Mixture in time domain                       |  $\mathbb{R}$                      |
| $\mathbf{y}_i$ | True source assignment/mask for speaker $i$  |  $[0,1]^{1 \times FT}$             |
| $\hat{\mathbf{y}}_{t,i}$ | Estimated source assignment/mask for speaker $i$  at time $t$ (ODANet) |  $[0,1]^{1 \times F}$ |
| $\hat{\mathbf{Y}}_p$ | Estimated Source Assignment for Anchor point combination $p$  |  $[0,1]^{C \times FT}$ |
| $\hat{\mathbf{Y}}_t$ | Estimated Source Assignment at time $t$ (ODANet)   |  $[0,1]^{C \times F}$ |

## A
| Symbol         | Description                                  | Dimension                          |
| -------------- | -------------------------------------------- | ---------------------------------- |
| $\mathbf{a}_i$ | Attractor point for speaker $i$              |  $\mathbb{R}^{1 \times K}$         |
| $\mathbf{a}_{t,i}$ | Attractor point for speaker $i$ at time $t$  |  $\mathbb{R}^{1 \times K}$     |
| $\mathbf{A}_p$ | Attractors for combination $p$ (ADANet)      |  $\mathbb{R}^{C \times K}$         |
| $\mathbf{A}_t$ | Attractors at time $t$ (ODANet)              |  $\mathbb{R}^{C \times K}$         |
| $\alpha_{t,i}$ | Update coefficient for speaker $i$'s attractor at time $t$ (ODANet) |  $\mathbb{R}$ |
| $\boldsymbol{\alpha}_{t,i}$ | Dynamic weighted update coefficient for speaker $i$'s attractor at time $t$ (ODANet) |  $\mathbb{R}^{1 \times K}$ |

## B
| Symbol         | Description                                  | Dimension                          |
| -------------- | -------------------------------------------- | ---------------------------------- |
| $\mathbf{b}_j$ | Anchor point number $j$                      |  $\mathbb{R}^{1 \times K}$         |

## C
| Symbol         | Description                                  | Dimension                          |
| -------------- | -------------------------------------------- | ---------------------------------- |
| $C$            | Number of Speakers                           |  $\mathbb{N}$                      |

## D
| Symbol         | Description                                  | Dimension                          |
| -------------- | -------------------------------------------- | ---------------------------------- |
| $\mathbf{D}_p$ | Distance between Embedding Points and Anchor point combination $p$  |  $\mathbb{R}^{C \times FT}$ |

## E

## F
| Symbol         | Description                                  | Dimension                          |
| -------------- | -------------------------------------------- | ---------------------------------- |
| $F$            | Number of frequency bins                     |  $\mathbb{N}$                      |
| $f$            | Frequency index                              |  $\mathbb{N}$                      |
| $\mathbf{f}_{t,i}$ | Forget Gate (ODANet, Dynamic Weighting)  |  $\mathbb{R}^{1 \times K}$         |

## G
| Symbol         | Description                                  | Dimension                          |
| -------------- | -------------------------------------------- | ---------------------------------- |
| $\mathbf{g}_{t,i}$ | Gate (ODANet, Dynamic Weighting)         |  $\mathbb{R}^{1 \times K}$         |

## H
| Symbol         | Description                                  | Dimension                          |
| -------------- | -------------------------------------------- | ---------------------------------- |
| $H$            | Output dimension of last LSTM layer          | \mathbb{N}                         |
| \mathbf{h}_{t-1} | Output of last LSTM layer at time $t-1$    | \mathbb{R}^{1 \time H}             |


## I
| Symbol         | Description                                  | Dimension                          |
| -------------- | -------------------------------------------- | ---------------------------------- |
| $i$            | Speaker index                                |  $\lbrace 1,2, \ldots , C \rbrace$ |

## J
| Symbol         | Description                                  | Dimension                          |
| -------------- | -------------------------------------------- | ---------------------------------- |
| $j$            | Anchor point index                           |  $\lbrace 1,2, \ldots , N \rbrace$ |

## K
| Symbol         | Description                                  | Dimension                          |
| -------------- | -------------------------------------------- | ---------------------------------- |
| $K$            | Embedding dimension                          |  $\mathbb{N}$                      |

## L
| Symbol         | Description                                  | Dimension                          |
| -------------- | -------------------------------------------- | ---------------------------------- |
| $l$            | Loss                                         |  $\mathbb{R}$                      |
| $\mathbf{L}_p$ | Anchor point combination $p$                 |  $\mathbb{R}^{C \times K}$         |

## M
| Symbol         | Description                                  | Dimension                          |
| -------------- | -------------------------------------------- | ---------------------------------- |
| $\mathbf{m}_i$ | Mask for speaker $i$                         |  $[0,1]^{1 \times FT}$             |
| $\hat{\mathbf{m}}_i$ | Estimated mask for speaker $i$         |  $[0,1]^{1 \times FT}$             |

## N

## O

## P
| Symbol         | Description                                  | Dimension                          |
| -------------- | -------------------------------------------- | ---------------------------------- |
| $p$            | Anchor point combination index               |  $\lbrace 1,2, \ldots , {N \choose C} \rbrace$ |

## Q

## R
| Symbol         | Description                                  | Dimension                          |
| -------------- | -------------------------------------------- | ---------------------------------- |
| $\rho$         | Threshold for the log magnetude spectrogram  |  $\mathbb{R}$                      |

## S
| Symbol         | Description                                  | Dimension                          |
| -------------- | -------------------------------------------- | ---------------------------------- |
| $\mathbf{s}_i$ | Magnitude clean spectrogram $\vert S_i(f,t) \vert$ of speaker source number $i$  |  $\mathbb{R}^{1 \times FT}$ |
| $\hat{\mathbf{s}}_i$ | Estimated magnitude spectrogram of the source $i$  |  $\mathbb{R}^{1 \times FT}$ |

## T
| Symbol         | Description                                  | Dimension                          |
| -------------- | -------------------------------------------- | ---------------------------------- |
| $T$            | Number of time frames                        |  $\mathbb{N}$                      |
| $t$            | Time index                                   |  $\mathbb{N}$                      |
| $\tau$         | Length of context window                     |  $[1,t-1]$                         |

## U

## V
| Symbol         | Description                                  | Dimension                          |
| -------------- | -------------------------------------------- | ---------------------------------- |
| $\mathbf{V}$   | Embedding                                    |  $\mathbb{R}^{K \times FT}$        |
| $\mathbf{V}_t$ | Embedding at time $t$  (ODANet)              |  $\mathbb{R}^{K \times F}$         |

## W
| Symbol         | Description                                  | Dimension                          |
| -------------- | -------------------------------------------- | ---------------------------------- |
| $\mathbf{w}$   | Threshold vector                             |  $\{0,1\}^{1 \times FT}$           |

## X
| Symbol         | Description                                  | Dimension                          |
| -------------- | -------------------------------------------- | ---------------------------------- |
| $X(f,t)$       | Mixture in frequency domain                  |  $\mathbb{C}$                      |
| $\mathbf{x}$   | Feature vector containing magnitude spectrogram $\vert X(f,t) \vert$  |  $\mathbb{R}^{1 \times FT}$ |
| $x(t)$         | Mixture in time domain                       |  $\mathbb{R}$                      |

## Y
| Symbol         | Description                                  | Dimension                          |
| -------------- | -------------------------------------------- | ---------------------------------- |
| $\mathbf{y}_i$ | True source assignment/mask for speaker $i$  |  $[0,1]^{1 \times FT}$             |
| $\hat{\mathbf{y}}_{t,i}$ | Estimated source assignment/mask for speaker $i$  at time $t$ (ODANet) |  $[0,1]^{1 \times FT}$             |
| $\hat{\mathbf{Y}}_p$ | Estimated Source Assignment for Anchor point combination $p$  |  $[0,1]^{C \times FT}$ |
| $\hat{\mathbf{Y}}_t$ | Estimated Source Assignment at time $t$ (ODANet)   |  $[0,1]^{C \times FT}$ |

## Z




