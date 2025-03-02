# 📊 Mean, Variance, and Standard Deviation Calculator

This project implements a function to calculate the mean, variance, standard deviation, maximum, minimum, and sum of a 3x3 matrix using NumPy.

## 📂 Project Structure

```
📂 mean-variance-standard-deviation-calculator
├── 📄 mean_var_std.py        # Main script with calculations
├── 📄 test_module.py        # Unit tests for the function
├── 📄 README.md             # Documentation
├── 📄 requirements.txt      # Required libraries
```

## 📝 Code Explanation

The script `mean_var_std.py` defines a function `calculate(list)`, which takes a list of 9 numbers, reshapes it into a 3x3 matrix, and computes:

### 📌 1. Mean Calculation
The mean is computed along rows, columns, and the entire matrix:
```python
"mean": [np.mean(matrix, axis=0).tolist(), np.mean(matrix, axis=1).tolist(), np.mean(matrix).tolist()]
```

### 📌 2. Variance Calculation
The variance is computed similarly:
```python
"variance": [np.var(matrix, axis=0).tolist(), np.var(matrix, axis=1).tolist(), np.var(matrix).tolist()]
```

### 📌 3. Standard Deviation Calculation
Computes standard deviation along the same dimensions:
```python
"standard deviation": [np.std(matrix, axis=0).tolist(), np.std(matrix, axis=1).tolist(), np.std(matrix).tolist()]
```

### 📌 4. Maximum and Minimum Values
Finds the max and min values in the matrix along each axis and overall:
```python
"max": [np.max(matrix, axis=0).tolist(), np.max(matrix, axis=1).tolist(), np.max(matrix).tolist()]
"min": [np.min(matrix, axis=0).tolist(), np.min(matrix, axis=1).tolist(), np.min(matrix).tolist()]
```

### 📌 5. Sum Calculation
Computes the sum along rows, columns, and the entire matrix:
```python
"sum": [np.sum(matrix, axis=0).tolist(), np.sum(matrix, axis=1).tolist(), np.sum(matrix).tolist()]
```

## ✅ Example Output
For the input `[0,1,2,3,4,5,6,7,8]`, the function returns:
```json
{
  "mean": [[3.0, 4.0, 5.0], [1.0, 4.0, 7.0], 4.0],
  "variance": [[6.0, 6.0, 6.0], [0.666, 0.666, 0.666], 6.666],
  "standard deviation": [[2.449, 2.449, 2.449], [0.816, 0.816, 0.816], 2.582],
  "max": [[6, 7, 8], [2, 5, 8], 8],
  "min": [[0, 1, 2], [0, 3, 6], 0],
  "sum": [[9, 12, 15], [3, 12, 21], 36]
}
```

## 📜 License
This project is open-source and available under the MIT License.

⭐ If you find this project useful, give it a star on GitHub!


