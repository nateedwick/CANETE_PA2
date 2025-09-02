# ADVANCED PROGRAMMING: Programming Assignment #2

## Project Overview  
This project contains solutions to problems using the **NumPy library** as part of **Advanced Programming Assignment 2.** It demonstrates how to identify, apply, and combine different NumPy functions to solve problems. The problems cover essential concepts such as random array generation, normalization, reshaping arrays, and indexing

## Getting Started
The code can be run in any Python environment that supports NumPy. For this project, **Jupyter Notebook** was used through **Anaconda Navigator** to write and execute the solutions. 
When using np.save("filename.npy", array), the .npy file is automatically saved in the same folder as the Jupyter Notebook file.

## Problems and Solutions

### 1. Normalization Problem
- **Goal:** Create a random 5×5 NumPy array and normalize it by subtracting its mean and dividing by its standard deviation. Save the normalized array as X_normalized.npy.

- **Code:**  A function from NumPy called np.random.random((5, 5)) is used to generate a 5×5 array containing random numbers between 0 and 1. This array is stored in the variable X. To normalize the array, the mean of X is obtained using X.mean() and the standard deviation is obtained using X.std(). Each element of the array is subtracted by the mean and divided by the standard deviation, which results in a normalized array stored in X_normalized. The normalized data now has a mean close to 0 and a standard deviation of 1. The command np.save("X_normalized.npy", X_normalized) is used to save the normalized array as a .npy file. Finally, the program prints both the original and normalized arrays for verification.
  ```python
  import numpy as np

  X = np.random.random((5, 5))           # random 5x5 ndarray (5 rows at columns)

  X_normalized = (X - X.mean()) / X.std()     # normalization process (subtract mean sa each elements tas divide sa sd)

  np.save("X_normalized.npy", X_normalized)   # saves normalized array as .npy
  
- **Output:**
  ```python
      print("Original Array:\n", X)
      print("\nNormalized Array:\n", X_normalized)

> Original Array:\
> [[0.54448084 0.72123388 0.76778989 0.64725219 0.68450814]\
> [0.02930046 0.17813176 0.41702243 0.59001943 0.5557514]\
> [0.13273943 0.97269145 0.6725715  0.34097546 0.66947673]\
> [0.09768099 0.39524974 0.99185424 0.3963563  0.91657438]\
> [0.08581219 0.51872286 0.92158466 0.15892968 0.23220236]]

> Normalized Array:\
> [[ 0.13431251  0.74421737  0.90486377  0.48893582  0.61749137]\
> [-1.64337126 -1.12981329 -0.30549604  0.2914482   0.17320276]\
> [-1.28644429  1.61189801  0.57630273 -0.56790407  0.56562391]\
> [-1.40741709 -0.380625    1.67802123 -0.3768067   1.41826021]\
> [-1.44837163  0.04543192  1.43554868 -1.19607209 -0.94323704]]


 ### 2. Divisible by 3 Problem
- **Goal:** Create a 10×10 NumPy array containing the squares of the first 100 positive integers. From this array, determine all elements that are divisible by 3. Save the result as div_by_3.npy.
  
- **Code:** The code begins with np.arange(1, 101) which generates integers from 1 to 100. By squaring each value using **2, the result is an array of perfect squares from 1 up to 100. The .reshape(10, 10) function rearranges this one-dimensional array into a 10×10 matrix stored in variable A. To identify the numbers divisible by 3, the condition A % 3 == 0 is applied, which checks each element and returns only those that satisfy the condition. The filtered values are stored in the variable div_by_3. With np.save("div_by_3.npy", div_by_3), the result is saved into a .npy file. Finally, the code prints both the 10×10 array of squares and the extracted divisible-by-3 elements for verification.

  ```python
  import numpy as np

  A = np.arange(1, 101)**2          # squares of first 100 integers (arange pero walang interval)
  A = A.reshape(10, 10)             # reshapes array into 10x10 (10 rows at columns)

  div_by_3 = A[A % 3 == 0]          # get elements na divisible by 3 lang

  np.save("div_by_3.npy", div_by_3)  # saves the result as .npy

- **Output:**
  ```python
  print("10x10 Array:\n", A)
  print("\nDivisible by 3:\n", div_by_3)

> 10x10 Array:\
> [[    1     4     9    16    25    36    49    64    81   100]\
> [  121   144   169   196   225   256   289   324   361   400]\
> [  441   484   529   576   625   676   729   784   841   900]\
> [  961  1024  1089  1156  1225  1296  1369  1444  1521  1600]\
> [ 1681  1764  1849  1936  2025  2116  2209  2304  2401  2500]\
> [ 2601  2704  2809  2916  3025  3136  3249  3364  3481  3600]\
> [ 3721  3844  3969  4096  4225  4356  4489  4624  4761  4900]\
> [ 5041  5184  5329  5476  5625  5776  5929  6084  6241  6400]\
> [ 6561  6724  6889  7056  7225  7396  7569  7744  7921  8100]\
> [ 8281  8464  8649  8836  9025  9216  9409  9604  9801 10000]]

> Divisible by 3:\
> [  9   36   81  144  225  324  441  576  729  900 1089 1296 1521 1764\
> 2025 2304 2601 2916 3249 3600 3969 4356 4761 5184 5625 6084 6561 7056\
> 7569 8100 8649 9216 9801]

