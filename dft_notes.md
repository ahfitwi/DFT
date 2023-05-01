# 1. Introduction To Discrete Fourier Transform (DFT)
- The FFT is a fast, O[NlogN] algorithm to compute DFT, which naively is an O[N2] computation.
- The DFT, like the more familiar continuous version of the Fourier transform, has a forward and inverse form which are defined as follows:
  - Forward Discrete Fourier Transform (DFT):
    $$X_k = \sum_{n=0}^{N-1} x_n .e^{\frac{-i2 \pi kn}{N}}$$
  - Inverse Discrete Fourier Transform (IDFT):
  $$x_n = \frac{1}{N} \sum_{k=0}^{N-1} X_k .e^{\frac{i2 \pi kn}{N}}$$
  $$x_n \rightarrow X_k$$
-  v
#
