# PROGRAMMING ASSIGNMENT 2

This repository contains my Jupyter Notebook submission for **ECE 2112: Advanced Computer Programming and Algorithms – Experiment 2**, covering two Python problems:
**Normalization** and **Divisible by 3**.

> Source of problems: *EXPERIMENT 2 - Numerical Python.pdf*

---

## Project Structure

```
.
├─ 2ECEB_LUCAS_PA2.ipynb   # Jupyter notebook with solutions
└─ README.md               # You're here
```

---

# NORMALIZATION

## Problem Description
**NORMALIZATION PROBLEM**: Normalization is one of the most basic preprocessing techniques in
data analytics. This involves centering and scaling process. Centering means subtracting the data from the
mean and scaling means dividing with its standard deviation. Mathematically, normalization can be
expressed as: 

$$
Z = \frac{X - \mu}{\sigma}
$$

In Python, element-wise mean and element-wise standard deviation can be obtained by using .mean() and
.std() calls. 

In this problem, create a random 5 x 5 ndarray and store it to variable X. Normalize X. Save your normalized
ndarray as *X_normalized.npy*

---

## Implementation and Explanation

### 1. Import NumPy
The first step is to import the `numpy` library as `np`. This library provides objects and tools for working with arrays.  

```
import numpy as np
```

### 2. Create a random 5x5 array
`np.random.random((5,5))` generates a 5x5 array with random values between 0 and 1. This array is stored in variable `X`. 

```
X = np.random.random((5,5))              
```

### 3. Compute the mean of the array
`np.mean(X)` calculates the **mean of all elements** in the array `X`. This value is stored in variable `M`.

```
M = np.mean(X)                
```

### 4. Compute the standard deviation of the array
`np.std(X)` computes the **standard deviation of all elements** in the array `X`. This value is stored in variable `SD`.

```
SD = np.std(X)        
```

### 5. Normalize the array
The normalization formula `(X - M) / SD` is applied element-wise. Each element of `X` has the mean `M` subtracted, then is divided by the standard deviation `SD`. The resulting normalized array is stored in variable `Z`.

```
Z = (X-M) / SD               
```

### 6. Save the normalized array
`np.save("X_normalized.npy", Z)` saves the normalized array `Z` to a file named `"X_normalized.npy"`. This allows the data to be loaded later.

```
np.save("X_normalized.npy", Z)
```

### 7. Load the saved array
`np.load('X_normalized.npy')` loads the array from the file `X_normalized.npy` and stores it in the variable `data`.

```
data = np.load("X_normalized.npy")
```

### 8. Print the original and normalized arrays
The `print()` function is used to display the original array `X` and the normalized array `data`. An empty print statement is used to separate the outputs for readability.

```
print(X)
print("")
print(data)
```

**Sample Output (values will vary because of randomness):**  

```
[[0.67506671 0.01548969 0.34755666 0.61320741 0.66938374]
 [0.28622405 0.82969895 0.70548245 0.34724348 0.86552085]
 [0.60718707 0.97320478 0.47984127 0.42497323 0.01499727]
 [0.83094167 0.93142143 0.96301468 0.98234529 0.84676398]
 [0.8988588  0.49357715 0.95188524 0.93862153 0.3431964 ]]

[[ 0.11596543 -2.15785765 -1.01309135 -0.09728806  0.09637397]
 [-1.22452915  0.64904398  0.22082052 -1.01417103  0.77253624]
 [-0.11804255  1.14376536 -0.55705395 -0.74620579 -2.15955522]
 [ 0.65332812  0.99972163  1.10863608  1.17527631  0.7078739 ]
 [ 0.88746534 -0.50970094  1.07026846  1.02454323 -1.02812292]]
```

---

# DIVISIBLE BY 3 PROBLEM

## Problem Description
**DIVISIBLE BY 3 PROBLEM**: Create the following 10 x 10 ndarray.

$$
A = 
\begin{bmatrix}
1 & 4 & \cdots & 81 & 100 \\
\vdots & \vdots & \ddots & \vdots & \vdots \\
\vdots & \vdots & \ddots & \vdots & \vdots \\
\vdots & \vdots & \ddots & \vdots & \vdots \\
8281 & 8464 & \cdots & 9801 & 10000
\end{bmatrix}
$$

which are the squares of the first 100 positive integers.

From this ndarray, determine all the elements that are divisible by 3. Save the result as *div_by_3.npy*

---

## Implementation and Explanation

### 1. Import NumPy
The first step is to import the `numpy` library as `np`. This library provides objects and tools for working with arrays.

```
import numpy as np
```

### 2. Create an array from 1 to 100
`np.arange(1,101,1)` generates a 1D array with values starting from 1 up to 100 (inclusive). This array is stored in variable `arr`.

```
arr = np.arange(1,101,1)
```

### 3. Square each element
`arr ** 2` squares each element in the array `arr`. The resulting array is stored in arr_squared.

```
arr_squared = arr ** 2
```

### 4. Reshape the array into 10x10
`arr_squared.reshape(10,10)` reshapes the 1D array of 100 elements into a 2D 10×10 array.

```
arr_squared = arr_squared.reshape(10,10)
```

### 5. Select elements divisible by 3
`arr_squared[arr_squared % 3 == 0]` selects only the elements of `arr_squared` that are divisible by 3. The resulting 1D array is stored in div.

```
div = arr_squared[arr_squared % 3 == 0]
```

### 6. Save the selected elements
`np.save("div_by_3.npy", div)` saves the array `div` into a file named `"div_by_3.npy"`. This allows the data to be retrieved later. 

```
np.save("div_by_3.npy", div)
```

### 7. Load the saved array
`np.load("div_by_3.npy")` loads the array from the file `"div_by_3.npy"` and stores it in `div_final`.

```
div_final = np.load("div_by_3.npy")
```

### 8. Print the results
The `print()` function is used to display the squared 10×10 array `arr_squared` and the array of elements divisible by 3 `div_final`. An empty `print()` is used to separate outputs for readability.

```
print(arr_squared)
print("")
print(div_final)
```

**Sample Output:**  

```
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

[   9   36   81  144  225  324  441  576  729  900 1089 1296 1521 1764
 2025 2304 2601 2916 3249 3600 3969 4356 4761 5184 5625 6084 6561 7056
 7569 8100 8649 9216 9801]
```

---

**Author:** LUCAS, Beatrice Sophia

**Section:** 2ECE-B

**Course:** ECE 2112 (Advanced Computer Programming and Algorithms)  
