# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:

```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# STEP 2: Read the Data
def read_data(filename):
    """Reads data from a CSV and returns a DataFrame."""
    return pd.read_csv(filename)

# STEP 3 & 4: Visualization Functions

def plot_distplot(data, column, bins=10, color='blue'):
    """Plots the distribution of a numerical column."""
    plt.figure(figsize=(8,5))
    sns.histplot(data[column], bins=bins, kde=True, color=color)
    plt.title(f'Distribution of {column}')
    plt.xlabel(column)
    plt.ylabel('Frequency')
    plt.show()

def plot_boxplot(data, column, hue=None):
    """Plots a boxplot for a column, with option for hue."""
    plt.figure(figsize=(8,5))
    sns.boxplot(x=hue, y=column, data=data)
    plt.title(f'Boxplot of {column}')
    plt.show()

def plot_scatter(data, x_col, y_col, hue=None):
    """Draws a scatter plot between two numeric columns with optional hue."""
    plt.figure(figsize=(8,5))
    sns.scatterplot(x=x_col, y=y_col, hue=hue, data=data)
    plt.title(f'Scatter Plot of {x_col} vs {y_col}')
    plt.show()

def plot_count(data, column):
    """Draws a count plot for a categorical column."""
    plt.figure(figsize=(8,5))
    sns.countplot(x=column, data=data)
    plt.title(f'Count Plot of {column}')
    plt.show()

def plot_correlation_heatmap(data, annot=True, cmap='coolwarm'):
    """Plots a heatmap of correlation matrix."""
    plt.figure(figsize=(10,7))
    # Select only numeric columns for correlation calculation
    numeric_data = data.select_dtypes(include=['float64', 'int64'])
    corr = numeric_data.corr()
    sns.heatmap(corr, annot=annot, cmap=cmap)
    plt.title('Correlation Heatmap')
    plt.show()

# Example usage with 'bmi.csv' (change file and columns as necessary)
if __name__ == "__main__":
    df = read_data('bmi.csv')
    plot_distplot(df, 'Height', bins=15, color='navy')
    plot_distplot(df, 'Weight', bins=15, color='darkred')
    plot_boxplot(df, 'Weight', hue='Gender')
    plot_count(df, 'Gender')
    plot_scatter(df, 'Height', 'Weight', hue='Gender')
    plot_correlation_heatmap(df)
```

# Result:
 <img width="1135" height="574" alt="Screenshot 2025-10-07 220205" src="https://github.com/user-attachments/assets/7aff1483-9f27-413a-a499-4e9cc755c80d" />
 <img width="1166" height="582" alt="Screenshot 2025-10-07 220214" src="https://github.com/user-attachments/assets/0cce69c3-0eec-47b4-8aa9-c00fdb23f385" />
 <img width="1224" height="580" alt="Screenshot 2025-10-07 220224" src="https://github.com/user-attachments/assets/9ff8e7e4-b295-43ee-a086-439f2a727aaf" />
 <img width="1160" height="590" alt="Screenshot 2025-10-07 220232" src="https://github.com/user-attachments/assets/adbc8fc7-863b-4b48-8d77-6e883c8fb49f" />
 <img width="1160" height="580" alt="Screenshot 2025-10-07 220240" src="https://github.com/user-attachments/assets/ae19820e-2a0c-4bb1-9029-8884ae5800da" />
 <img width="1110" height="756" alt="Screenshot 2025-10-07 220251" src="https://github.com/user-attachments/assets/d43d0cc8-ba58-4efd-b77a-19b0f730964c" />






