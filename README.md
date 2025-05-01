# python_pandas

## Installation

To get started, install the `pandas` library (and `numpy` if needed):

```bash
pip install pandas numpy
```

## Creating DataFrames

This project demonstrates various ways to create pandas DataFrames:

- **Empty DataFrame**
- **From a list**
- **From a list of lists**
- **From a numpy array**
- **From a dictionary**
- **From a list of dictionaries**
- **From zipped lists (list of tuples)**

Example:
```python
import pandas as pd
import numpy as np

# Empty DataFrame
empty_df = pd.DataFrame()

# From list
df_list = pd.DataFrame([1, 2, 3, 4, 5], index=['a', 'b', 'c', 'd', 'e'], columns=['Values'])

# From list of lists
data = [['tom', 10], ['nick', 15], ['juli', 14]]
df = pd.DataFrame(data, columns=['Name', 'Age'], index=['a', 'b', 'c'])

# From numpy array
array = np.array([[1, 2], [3, 4], [5, 6]])
df_array = pd.DataFrame(array, columns=['A', 'B'], index=['a', 'b', 'c'])

# From dictionary
data = {
    'Timestamp': ['2023-01-01 09:30', '2023-01-01 09:31', '2023-01-01 09:32'],
    'Stock': ['AAPL', 'AAPL', 'AAPL'],
    'Price': [150.25, 150.50, 150.75],
    'Volume': [1000, 1500, 1200]
}
df_trading = pd.DataFrame(data)

# From list of dictionaries
data = [{'b': 2, 'c': 3}, {'a': 10, 'b': 20, 'c': 30}]
df_dict = pd.DataFrame(data, index=['first', 'second'])

# From zipped lists
Name = ['tom', 'krish', 'nick', 'juli']
Age = [25, 30, 26, 22]
list_of_tuples = list(zip(Name, Age))
df_zip = pd.DataFrame(list_of_tuples, columns=['Name', 'Age'])
```

## DataFrame Index Operations

The notebooks also cover various index operations:

- **Setting an index**: `set_index()`
- **Resetting the index**: `reset_index()`
- **Renaming the index**: using `.index.name`
- **MultiIndex (hierarchical indexing)**: setting multiple columns as index

Example:
```python
# Sample DataFrame
data = {
    'City': ['New York', 'Los Angeles', 'Chicago', 'Houston', 'Phoenix'],
    'State': ['NY', 'CA', 'IL', 'TX', 'AZ'],
    'Population': [8419000, 3980000, 2716000, 2328000, 1690000]
}
df = pd.DataFrame(data)

# Set index
df_indexed = df.set_index('City')

# Reset index
df_reset = df_indexed.reset_index()

# Rename index
df_state_index = df.set_index('State')
df_state_index.index.name = 'StateName'

# MultiIndex
df_multi = df.set_index(['State', 'City'])
```

---

For more details and code examples, see the Jupyter notebooks in the `dataframe/` directory.