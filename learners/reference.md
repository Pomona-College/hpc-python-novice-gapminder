---
title: Reference
---

## Python Quick Reference

### Common Data Types

```python
# Integers
x = 42
type(x)  # <class 'int'>

# Floats
pi = 3.14159
type(pi)  # <class 'float'>

# Strings
name = "Alice"
type(name)  # <class 'str'>

# Lists (mutable, ordered)
numbers = [1, 2, 3, 4, 5]
numbers[0]  # 1
numbers.append(6)

# Tuples (immutable, ordered)
coords = (10, 20)
coords[0]  # 10

# Dictionaries (key-value pairs)
person = {'name': 'Bob', 'age': 30}
person['name']  # 'Bob'
```

## NumPy Quick Reference

### Creating Arrays

```python
import numpy as np

# From Python lists
arr = np.array([1, 2, 3, 4, 5])

# Built-in functions
zeros = np.zeros(5)      # [0. 0. 0. 0. 0.]
ones = np.ones(3)        # [1. 1. 1.]
range_arr = np.arange(0, 10, 2)  # [0 2 4 6 8]

# Random
random_arr = np.random.random(5)  # 5 random floats [0, 1)
```

### Array Operations

```python
# Element-wise operations
arr1 = np.array([1, 2, 3])
arr2 = np.array([4, 5, 6])

arr1 + arr2      # [5 7 9]
arr1 * arr2      # [4 10 18]
arr1 ** 2        # [1 4 9]

# Aggregation functions
arr.sum()        # Sum of all elements
arr.mean()       # Average
arr.std()        # Standard deviation
arr.min()        # Minimum value
arr.max()        # Maximum value
```

### Array Indexing and Slicing

```python
arr = np.array([10, 20, 30, 40, 50])

arr[0]           # 10 (first element)
arr[-1]          # 50 (last element)
arr[1:4]         # [20 30 40] (slice)
arr[::2]         # [10 30 50] (every other element)

# 2D arrays
arr_2d = np.array([[1, 2, 3], [4, 5, 6]])
arr_2d[0, 1]     # 2 (row 0, column 1)
arr_2d[1, :]     # [4 5 6] (entire second row)
```

## Pandas Quick Reference

### Creating DataFrames

```python
import pandas as pd

# From dictionary
data = {'name': ['Alice', 'Bob', 'Charlie'],
        'age': [25, 30, 35]}
df = pd.DataFrame(data)

# From CSV file
df = pd.read_csv('gapminder_gdp_africa.csv')

# Display
df.head()        # First 5 rows
df.tail()        # Last 5 rows
df.info()        # Column info
df.describe()    # Statistical summary
```

### Selecting Data

```python
# Column selection
df['name']                    # Single column as Series
df[['name', 'age']]          # Multiple columns as DataFrame

# Row selection
df.loc[0]                    # By label
df.iloc[0]                   # By position
df.loc[df['age'] > 30]       # Boolean indexing

# Cell selection
df.loc[0, 'name']            # Specific cell
```

### Data Manipulation

```python
# Adding columns
df['age_squared'] = df['age'] ** 2

# Filtering
young = df[df['age'] < 30]

# Sorting
df.sort_values('age')           # Sort ascending
df.sort_values('age', ascending=False)  # Sort descending

# Grouping and aggregation
df.groupby('category')['age'].mean()

# Missing data
df.isnull()      # Check for NaN values
df.fillna(0)     # Replace NaN with 0
df.dropna()      # Remove rows with NaN
```

## Matplotlib Quick Reference

### Basic Plotting

```python
import matplotlib.pyplot as plt

# Line plot
plt.plot([1, 2, 3, 4], [1, 4, 2, 3])
plt.xlabel('X axis')
plt.ylabel('Y axis')
plt.title('Simple Line Plot')
plt.show()

# Scatter plot
plt.scatter([1, 2, 3, 4], [1, 4, 2, 3])
plt.show()

# Bar plot
plt.bar(['A', 'B', 'C'], [10, 24, 36])
plt.show()
```

### Figure and Subplot Management

```python
# Create figure with specific size
fig, ax = plt.subplots(figsize=(10, 6))

# Create multiple subplots
fig, (ax1, ax2) = plt.subplots(1, 2, figsize=(12, 5))
ax1.plot([1, 2, 3])
ax2.scatter([1, 2, 3], [1, 4, 9])

plt.tight_layout()  # Prevent overlap
plt.show()
```

### Customization

```python
plt.plot([1, 2, 3], label='Line 1')
plt.plot([3, 2, 1], label='Line 2')
plt.legend()           # Show legend

plt.xlim(0, 4)         # Set x-axis limits
plt.ylim(0, 5)         # Set y-axis limits

plt.grid(True)         # Show grid

# Color and style
plt.plot([1, 2, 3], 'r--')     # Red dashed line
plt.scatter([1, 2, 3], s=50, alpha=0.5)  # Size and transparency

# Save figure
plt.savefig('my_plot.png', dpi=300)
```

### Common Plot Types

```python
# Histogram
plt.hist(data, bins=20)

# Box plot
plt.boxplot([data1, data2])

# Heatmap (requires matplotlib.image or seaborn)
import seaborn as sns
sns.heatmap(df)

# 3D plot
from mpl_toolkits.mplot3d import Axes3D
fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')
```

## Jupyter Notebook Keyboard Shortcuts

### Navigation

| Shortcut | Action |
|----------|--------|
| `Enter` | Edit mode |
| `Esc` | Command mode |
| `Up/Down` | Previous/next cell |
| `Shift+Enter` | Run cell and move to next |
| `Ctrl+Enter` | Run cell (stay in place) |
| `Alt+Enter` | Run cell and insert new below |

### Cell Operations (in Command Mode)

| Shortcut | Action |
|----------|--------|
| `A` | Insert cell above |
| `B` | Insert cell below |
| `D, D` | Delete cell |
| `M` | Change to Markdown |
| `Y` | Change to Code |
| `Z` | Undo |
| `Ctrl+Shift+Z` | Redo |

### Useful Tricks

| Action | Command |
|--------|---------|
| Get help on function | `help(function_name)` or `function_name?` |
| Show docstring | `function_name?` |
| Show source code | `function_name??` |
| Time execution | `%timeit statement` |
| Run shell command | `!command` |
| Magic commands | `%magic` |

## Useful Resources

- **NumPy:** https://numpy.org/doc/stable/
- **Pandas:** https://pandas.pydata.org/docs/
- **Matplotlib:** https://matplotlib.org/stable/contents.html
- **Python Docs:** https://docs.python.org/3/
- **HPC Support:** its-hpc@pomona.edu
