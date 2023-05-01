# 1. Introduction To Discrete Fourier Transform (DFT)
- The FFT is a fast, O[NlogN] algorithm to compute DFT, which naively is an O[N2] computation.
- The DFT, like the more familiar continuous version of the Fourier transform, has a forward and inverse form which are defined as follows:
  - Forward Discrete Fourier Transform (DFT):
    $$X_k = \sum_{n=0}^{N-1} x_n .e^{\frac{-i2 \pi kn}{N}}$$
  - Inverse Discrete Fourier Transform (IDFT):
  $$x_n = \frac{1}{N} \sum_{k=0}^{N-1} X_k .e^{\frac{i2 \pi kn}{N}}$$
    - Transformation from $x_n \rightarrow X_k$ is a translation from configuration space to frequency space.
-  Both NumPy and SciPy have wrappers of the extremely well-tested FFTPACK library, found in the submodules numpy.fft and scipy.fftpack.
- 
# 2. Computing the Discrete Fourier Transform
- A matrix-vector multiplication of $\vec{p}$:
$$\vec{X} = M.\vec{x}$$
- Where matrix M is given by:
$$M{kn} = e^{\frac{-i2\pi k n}{N}}$$

# Computing DFT using simple matrix multiplication as follows:

          import numpy as np
          def DFT_slow(x):
            """Compute the discrete Fourier Transform of the 1D array x"""
            x = np.asarray(x, dtype=float)
            N = x.shape[0]
            n = np.arange(N)
            k = n.reshape((N, 1))
            M = np.exp(-2j * np.pi * k * n / N)
            return np.dot(M, x)

https://jakevdp.github.io/blog/2013/08/28/understanding-the-fft/?fbclid=IwAR2T7YT4i1dacrTvn4Ym5bgZNTVGshtRvqQj5k6GjQqF3sWzbEmRSadDPb8#The-Discrete-Fourier-Transform
