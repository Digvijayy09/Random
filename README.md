https://colab.research.google.com/drive/1D2IzNJ-kGx216etin5NY2YZWRRufI9za


import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
from scipy import stats

# Generate random data for demonstration
data = np.random.normal(loc=50, scale=10, size=1000)

# Statistical properties
mean = np.mean(data)
median = np.median(data)
mode = stats.mode(data).mode[0]
std_dev = np.std(data)
variance = np.var(data)
percentile_25 = np.percentile(data, 25)
percentile_50 = np.percentile(data, 50)  # Same as median
percentile_75 = np.percentile(data, 75)

# Display statistical properties
print(f"Mean: {mean}")
print(f"Median: {median}")
print(f"Mode: {mode}")
print(f"Standard Deviation: {std_dev}")
print(f"Variance: {variance}")
print(f"25th Percentile: {percentile_25}")
print(f"50th Percentile (Median): {percentile_50}")
print(f"75th Percentile: {percentile_75}")

# Data distribution plot
sns.histplot(data, kde=True, bins=30, color='blue')
plt.title('Histogram and Data Distribution')
plt.xlabel('Data Values')
plt.ylabel('Frequency')
plt.show()

# Scatter plot of random data
data_x = np.random.normal(50, 10, 1000)
data_y = np.random.normal(50, 10, 1000)
plt.scatter(data_x, data_y, alpha=0.5, color='green')
plt.title('Scatter Plot of Random Data')
plt.xlabel('X-axis Data')
plt.ylabel('Y-axis Data')
plt.show()

# Big data distribution
big_data = np.random.normal(loc=0, scale=1, size=1000000)
sns.histplot(big_data, bins=50, kde=True, color='red')
plt.title('Big Data Distribution')
plt.xlabel('Data Values')
plt.ylabel('Frequency')
plt.show()

# Normal data distribution comparison
normal_data1 = np.random.normal(0, 1, 1000)
normal_data2 = np.random.normal(5, 2, 1000)
sns.kdeplot(normal_data1, label='N(0,1)', color='blue')
sns.kdeplot(normal_data2, label='N(5,2)', color='orange')
plt.title('Comparison of Normal Distributions')
plt.legend()
plt.show()

# Percentiles of big data
descriptive_stats = {
    "Mean": np.mean(big_data),
    "Median": np.median(big_data),
    "25th Percentile": np.percentile(big_data, 25),
    "50th Percentile": np.percentile(big_data, 50),
    "75th Percentile": np.percentile(big_data, 75),
}

print("Big Data Descriptive Statistics:")
for key, value in descriptive_stats.items():
    print(f"{key}: {value}")
    
