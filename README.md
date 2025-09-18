## ECE2112 PA #2 | DOCUMENTATION

**1. NORMALIZATION PROBLEM:Normalization is one of the most basic preprocessing techniques in data analytics. This involves centering and scaling process. Centering means subtracting the data from the mean and scaling means dividing with its standard deviation. Mathematically, normalization can be expressed as:

<p align="center">
  $Z = \frac{X - x̄}{\sigma}$
</p>  

In Python, element-wise mean and element-wise standard deviation can be obtained by using .mean() and .std() calls.

In this problem, create a random 5 x 5 ndarray and store it to variable X. Normalize X. Save your normalized ndarray as X_normalized.npy.
