# Five Number Summary and Box Plot in Python

This README explains a Python notebook that demonstrates how to compute the five-number summary (minimum, Q1, median, Q3, maximum), identify outliers using the Interquartile Range (IQR), and visualize the data with a box plot using Seaborn and Matplotlib.

## **Overview**

The code covers:
- Calculation of the five-number summary for a dataset
- Calculation of IQR and fences for outlier detection
- Visualization of the data using a box plot
- Handling of datasets with and without outliers

## **Requirements**

- Python 3.x
- numpy
- seaborn
- matplotlib

Install dependencies with:

```bash
pip install numpy seaborn matplotlib
```

## **Code and Explanation**

### **1. Import Libraries**

```python
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
```
*These libraries are needed for numerical operations (numpy), plotting (matplotlib), and statistical visualization (seaborn).*[1]

### **2. Five-Number Summary Calculation**

```python
lst_marks = [45, 32, 56, 75, 89, 54, 32, 89, 90, 87, 67, 54, 45, 98, 99, 67, 74]
minimum, Q1, median, Q3, maximum = np.quantile(lst_marks, [0, 0.25, 0.50, 0.75, 1.0])
```
- `lst_marks`: List of numerical data (e.g., student marks).
- `np.quantile`: Calculates the quantiles for the given data:
  - 0% (minimum), 25% (Q1), 50% (median), 75% (Q3), 100% (maximum).

### **3. Display the Five-Number Summary**

```python
minimum, Q1, median, Q3, maximum
```
- This line outputs the five-number summary as a tuple.

### **4. Interquartile Range (IQR) Calculation**

```python
IQR = Q3 - Q1
IQR
```
- IQR measures the spread of the middle 50% of the data.
- Useful for detecting outliers.

### **5. Outlier Fences Calculation**

```python
lower_fence = Q1 - 1.5 * IQR
higher_fence = Q3 + 1.5 * IQR
```
- **Lower fence**: Data below this value are considered outliers.
- **Higher fence**: Data above this value are considered outliers.

### **6. Print the Outlier Fences**

```python
print(lower_fence)
print(higher_fence)
```
- Prints the calculated lower and upper bounds for outliers.

### **7. Box Plot Visualization (Without Outliers)**

```python
sns.boxplot(lst_marks)
plt.savefig("without_outliers.jpg", dpi=300)
```
- Creates a box plot for the data.
- The plot is saved as "without_outliers.jpg".
- Box plots visually display the five-number summary and highlight outliers as points outside the whiskers.

### **8. Example with Outliers**

```python
lst_marks = [-50, -60, 45, 32, 56, 75, 89, 54, 32, 89, 90, 87, 67, 54, 45, 98, 99, 67, 74, 150, 170]
```
- This list includes extreme values (outliers) to demonstrate their effect on the box plot and summary statistics.

## **Summary Table: Five-Number Summary Example**

| Statistic | Value (Example) |
|-----------|-----------------|
| Minimum   | 32.0            |
| Q1        | 54.0            |
| Median    | 67.0            |
| Q3        | 89.0            |
| Maximum   | 99.0            |

## **How It Works**

- The code first computes the five-number summary to describe the distribution of the dataset.
- The IQR is used to establish fences for identifying outliers.
- Box plots provide a visual summary, showing the median, quartiles, and possible outliers.

## **Usage**

1. Replace `lst_marks` with your own data.
2. Run each code cell in sequence.
3. View the box plot image output for visual analysis.
