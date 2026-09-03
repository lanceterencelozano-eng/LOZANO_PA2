# Programming Assignment 2
#### Made by: Lance Terence A. Lozano | 2ECE-C

## Objectives
1. create and reshape NumPy arrays using appropriate NumPy functions;
2. perform vectorized numerical operations on an ndarray;
3. compute array statistics and use Boolean conditions to select elements; and
4. save computed NumPy arrays as .npy files.

`import numpy as np`

## Reproducible Normalization Problem
Demonstrates pseudo-random array generation using `np.random.seed(2112)` and `np.random.randint()` to construct a reproducible 5×5 integer matrix. It applies vectorized arithmetic to perform Z-score normalization by subtracting the array mean and dividing by the population standard deviation. Finally, it verifies that the normalized array achieves a mean of 0 and a standard deviation of 1 before saving it to `X_normalized.npy`.

```python
np.random.seed(2112)
X = np.random.randint(10, 101, size=(5,5))
X
```
```python
X_mean = np.mean(X)
X_mean
```
```python
X_std = np.std(X) 
X_std
```
```python
X_normalized = (X - X_mean) / X_std
X_normalized
```
```python
X_normalized_mean = np.mean(X_normalized)
X_normalized_mean
```
```python
X_normalized_std = np.std(X_normalized)
X_normalized_std
```
```python
np.save("X_normalized.npy", X_normalized)
```

## Cubes Divisible by 4 Problem
Generates the first 100 positive integers, vectorially computes their cubes, and reshapes the sequence into a 10×10 matrix using `np.arange()` and `.reshape()`. It utilizes Boolean indexing with the modulo operator `C % 4 == 0` to filter out elements divisible by 4 in row-major order. The resulting 50-element array is confirmed and exported to binary format as `div_by_4.npy`.

```python
C = (np.arange(1, 101) ** 3).reshape(10, 10)
C
```
```python
C.shape
```
```python
div_by_4 = C[C % 4 == 0] 
div_by_4
```
```python
div_by_4.size
```
```python
np.save("div_by_4.npy", div_by_4)
```

## Above-Mean Squares Problem
Constructs a 6×6 matrix of the squared values of the first 36 positive integers without using Python loops. It calculates the overall arithmetic mean of the matrix using `np.mean()` and applies conditional filtering `S > S_mean` to extract elements strictly greater than the mean. The extracted 15-element array is verified and saved as `above_mean.npy`.

```python
S = (np.arange(1, 37) ** 2).reshape(6, 6)
S
```
```python
S_mean = np.mean(S) 
S_mean
```
```python
above_mean = S[S > S_mean]  
above_mean
```
```python
above_mean.size
```
```python
np.save("above_mean.npy", above_mean)
```
## README File Version History
September 3,2026 - Initial README output uploaded
