Project Title: Analysis of Students' Academic Performance

Project Description:
This project involves analyzing students' academic performance using two datasets: "Expanded_data_with_more_features.csv" and "Original_data_with_more_rows.csv". The goal is to identify patterns and insights based on various features such as gender, parental education, marital status, and ethnic group, and to understand how these factors influence students' scores in Math, Reading, and Writing.

Installation:

Ensure you have Python installed (preferably Python 3.6 or higher).
Install the required libraries using pip:
pip install pandas numpy seaborn matplotlib



Copy code
pip install pandas numpy seaborn matplotlib
Usage:

Load the datasets:

python
Copy code
import pandas as pd
df1 = pd.read_csv("Expanded_data_with_more_features.csv")
df2 = pd.read_csv("Original_data_with_more_rows.csv")
Merge the datasets:

python
Copy code
df = df1.merge(df2)
Analyze the data:

View the first few rows:

python
Copy code
print(df.head())
Visualize gender distribution:

python
Copy code
import seaborn as sns
import matplotlib.pyplot as plt

plt.figure(figsize=(5,5))
ax = sns.countplot(data=df, x="Gender")
ax.bar_label(ax.containers[0])
plt.show()
Analyze the relationship between parental education and students' scores:

python
Copy code
gb = df.groupby("ParentEduc").agg({"MathScore": "mean", "ReadingScore": "mean", "WritingScore": "mean"})
print(gb)

plt.figure(figsize=(6,5))
plt.title("Relationship between Parents' Education and Students' Scores")
sns.heatmap(gb, annot=True)
plt.show()
Analyze the relationship between parents' marital status and students' scores:

python
Copy code
gb1 = df.groupby("ParentMaritalStatus").agg({"MathScore": "mean", "ReadingScore": "mean", "WritingScore": "mean"})
print(gb1)

plt.figure(figsize=(6,5))
plt.title("Relationship between Parents' Marital Status and Students' Scores")
sns.heatmap(gb1, annot=True)
plt.show()
Visualize scores distribution using box plots:

python
Copy code
sns.boxplot(data=df, x="MathScore")
plt.show()

sns.boxplot(data=df, x="ReadingScore")
plt.show()

sns.boxplot(data=df, x="WritingScore")
plt.show()
Conclusions:

There are more females than males in the dataset.
Parental education has a significant impact on students' scores.
Parental marital status has negligible impact on students' scores.
Dependencies:

pandas
numpy
seaborn
matplotlib
