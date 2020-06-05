# Table of Variables

| Symbol         | Description                                  | Dimension                          |
| -------------- | -------------------------------------------- | ---------------------------------- |
| $\mathbf{a}_i$ | Attractor point for speaker $i$              |  $\mathbb{R}^{1 \times K}$         |
| $\mathbf{A}_p$ | Attractors for combination $p$               |  $\mathbb{R}^{C \times K}$         |
| $\mathbf{b}_j$ | Anchor point number $j$                      |  $\mathbb{R}^{1 \times K}$         |
| $C$            | Number of Speakers                           |  $\mathbb{N}$                      |
| $\mathbf{D}_p$ | Distance between Embedding Points and Anchor point combination $p$  |  $\mathbb{R}^{C \times FT}$ |
| $F$            | Number of frequency bins                     |  $\mathbb{N}$                      |
| $i$            | Speaker index                                |  $\lbrace 1,2, \ldots , C \rbrace$ |
| $j$            | Anchor point index                           |  $\lbrace 1,2, \ldots , N \rbrace$ |
| $K$            | Embedding dimension                          |  $\mathbb{N}$                      |
| $\mathbf{L}_p$ | Anchor point combination $p$                 |  $\mathbb{R}^{C \times K}$         |
| $\mathbf{m}_i$ | Mask for speaker $i$                         |  $[0,1]^{1 \times FT}$         |
| $p$            | Anchor point combination index               |  $\lbrace 1,2, \ldots , {N \choose C} \rbrace$ |
| $\rho$         | Threshold for the log magnetude spectrogram  |  $\mathbb{R}$                      |
| $s_i(t)$       | Speaker source number $i$ in time domain     |  $\mathbb{R}$                      |
| $S_i(f,t)$     | Speaker source number $i$ in frequency domain |  $\mathbb{C}$                     |
| $\mathbf{s}_i$ | Magnitude clean spectrogram $\vert S_i(f,t) \vert$ of speaker source number $i$  |  $\mathbb{R}^{1 \times FT}$ |
| $\hat{\mathbf{s}}_i$ | Estimated magnitude spectrogram of the source $i$  |  $\mathbb{R}^{1 \times FT}$ |
| $T$            | Number of time frames                        |  $\mathbb{N}$                      |
| $\mathbf{V}$   | Embedding                                    |  $\mathbb{R}^{K \times FT}$        |
| $\mathbf{w}$   | Threshold vector                             |  $\{0,1\}^{1 \times FT}$        |
| $\mathbf{y}_i$ | True source assignment/mask for speaker $i$  |  $[0,1]^{1 \times FT}$        |
| $\hat{\mathbf{Y}}_p$ | Estimated Source Assignment for Anchor point combination $p$  |  $[0,1]^{C \times FT}$ |
| $X(f,t)$       | Mixture in frequency domain                  |  $\mathbb{C}$                      |
| $\mathbf{x}$   | Feature vector containing magnitude spectrogram $\vert X(f,t) \vert$  |  $\mathbb{R}^{1 \times FT}$ |
| $x(t)$         | Mixture in time domain                       |  $\mathbb{R}$                      |