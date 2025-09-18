## ECE2112 PA #2 | DOCUMENTATION

**1. NORMALIZATION PROBLEM:Normalization is one of the most basic preprocessing techniques in data analytics. This involves centering and scaling process. Centering means subtracting the data from the mean and scaling means dividing with its standard deviation. Mathematically, normalization can be expressed as:**

<p align="center">
$Z = \frac{X - x̄}{\sigma}$
</p>  

In Python, element-wise mean and element-wise standard deviation can be obtained by using `.mean()` and `.std()` calls.

In this problem, create a random 5 x 5 ndarray and store it to variable `X`. Normalize `X`. Save your normalized ndarray as `X_normalized.npy`.

**CODE** 
```
#Importing the numpy library 
import numpy as np 
```
▸ Syntax for importing the numpy library.
```
#Creates a 5x5 array containing a random values
X = np.random.random((5,5)) 
```
▸ This line is where the creating of random 2d array with a size of (5,5) happened by using the numpy `.random`, and stores to variable `X.`  

```
print ("5x5 array\n", X)   
```
▸For printing the array.  
```
#Calculates and stores the normalized array
Z= (X - X.mean ())/X.std() 

#Prints the normalized array
print ("Normalized array\n", Z)
```
▸ The normalization formula is applied to every value in the random array, and the resulting normalized array is stored in the variable  `Z`. 

```
#Prints the normalized array
print ("Normalized array\n", Z)
```
▸ For printing the normalized array. 

```
#Saves the arrays on disk
np.save('X_normalized', Z) 
```
▸ Saving the normalized array stored in `z` in `X_normalized.npy`. 

**OUTPUT** 

```
5x5 array
 [[0.15390611 0.01348515 0.98212324 0.6403481  0.22513149]
 [0.86817222 0.89749795 0.55835643 0.46107926 0.95445657]
 [0.81684804 0.97818223 0.80373009 0.07347218 0.11645759]
 [0.58532931 0.53430071 0.88711406 0.28953762 0.59605845]
 [0.18981828 0.31424207 0.17902653 0.03367446 0.78501509]]
Normalized array
 [[-1.11128717 -1.54047577  1.42011103  0.37549489 -0.89359087]
 [ 1.07182626  1.16145868  0.12489207 -0.17243005  1.33554941]
 [ 0.91495684  1.40806554  0.87486259 -1.35712886 -1.22574643]
 [ 0.20733312  0.05136713  1.12972089 -0.69673721  0.24012611]
 [-1.00152366 -0.6212295  -1.03450804 -1.4787683   0.81766127]]

```
**2. DIVISIBLE BY 3 PROBLEM: Create the following 10x10 ndarray** 

$$
A = \begin{bmatrix}
1 & 4 & \cdots & 81 & 100 \\
\vdots & \vdots & \ddots & \vdots & \vdots \\
\vdots & \vdots & \ddots & \vdots & \vdots \\
\vdots & \vdots & \ddots & \vdots & \vdots \\
8281 & 8464 & \cdots & 9801 & 10000
\end{bmatrix}
$$

which are the squares of the first 100 positive integers. 

**CODE**

```
import numpy as np  
```
▸ Syntax for importing the numpy library.

```
#Creates a 1d aaray containing numbers 1-100 then it takes the square of each number 
A = (np.arange(1,101)**2) 
```
▸ Using the `.arrange` function, it enables a 1d array containing the number 1-100 to be created and raised to the power of 2. Then the resulting array will be stored to variable `A`. 

```
#Reshaping the array into a 10x10 2d matrix 
A = A.reshape(10,10)
```
▸The `.reshape` is used to reshaped the array into a 10x10 2d matrix. 

```
#Prints the 10x10 array 
print ("The Squares of the First 100 Positive Integers:\n" , A)  
```
▸ For printing the 10x10 array. 

```
#Subsets array of A for all numbers divisible by 3 then stores it to 'D' 
D = A[A%3==0] 
```
▸ Using a boolean indexing a subset of array `A` is created to obtain all numbers divisible by 3. After that the subset will be stored in variable `D`. 

```
#Prints the subset 
print("Numbers Divisible by 3:\n", D)
```
▸ For printing the subset. 

```
#Saves the arrays on disk 
np.save ('div_by_3', D) 
```
▸The subset stored in `D` is saved as `div_by_3.npy`. 

**OUTPUT** 

```
The Squares of the First 100 Positive Integers:
 [[    1     4     9    16    25    36    49    64    81   100]
 [  121   144   169   196   225   256   289   324   361   400]
 [  441   484   529   576   625   676   729   784   841   900]
 [  961  1024  1089  1156  1225  1296  1369  1444  1521  1600]
 [ 1681  1764  1849  1936  2025  2116  2209  2304  2401  2500]
 [ 2601  2704  2809  2916  3025  3136  3249  3364  3481  3600]
 [ 3721  3844  3969  4096  4225  4356  4489  4624  4761  4900]
 [ 5041  5184  5329  5476  5625  5776  5929  6084  6241  6400]
 [ 6561  6724  6889  7056  7225  7396  7569  7744  7921  8100]
 [ 8281  8464  8649  8836  9025  9216  9409  9604  9801 10000]]
Numbers Divisible by 3:
 [   9   36   81  144  225  324  441  576  729  900 1089 1296 1521 1764
 2025 2304 2601 2916 3249 3600 3969 4356 4761 5184 5625 6084 6561 7056
 7569 8100 8649 9216 9801]
```







