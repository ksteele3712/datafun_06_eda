## datafun_06_eda 🍎🥦
In this project, I will analyze 77 different kinds of fruits and vegetables. We will see their nutrition values from a CSV file using Jupyter Notebook, pandas, seaborn, and other popular data analytics tools. The analysis will include visualizations and graphs to compare nutrients and highlight key findings. The notebook will tell a data story and present results in a clear and engaging way.


## 📁 Project File Structure

```text
datafun_06_eda/
├── data/
│   ├── nutrition_values.csv
│   ├── Fruit-Prices-2022.csv
│   └── Vegetable-Prices-2022.csv
├── kristinesteele_eda.ipynb
├── README.md
├── requirements.txt
├── .gitignore
└── ... (other files and folders)
```


## ⚙️ Setup for the Project

Follow these steps to set up your project:

1. **Sign into GitHub.**
2. **Create a repository titled `datafun_06_eda` with a README.**
3. **Clone the repository to VS Code:**
	```powershell
	git clone https://github.com/ksteele3712/datafun_06_eda
	```
4. **Create a `.gitignore` file:**
	- Purpose: Excludes files and folders from being tracked by git (e.g., virtual environments, temporary files, system files).
5. **Create a `requirements.txt` file:**
	- Purpose: Lists all Python packages needed for your project so others can install them easily with `pip install -r requirements.txt`.

6. **Be sure to be in the right terminal directory before installing requirements:**
	- Change to your project folder:
	```powershell
	cd C:\Repos\datafun_06_eda
	```
	- Then use these commands to set up your Python environment:
	```powershell
	py -m pip install --upgrade pip setuptools wheel
	py -m pip install --upgrade -r requirements.txt
	```
    - Then use these commands to add in external requirements:
	```powershell
    pip install jupyterlab pandas pyarrow matplotlib seaborn
    ```
	- 
## 🚀 GitHub Commit Commands

Use these commands to commit and push your changes to GitHub:

```powershell
git add .
git commit -m "update changes"
git push
```


## 7. **Create and configure your Jupyter notebook:**
	- Create a file titled `kristinesteele_eda.ipynb`.
	- Click on 'Kernel' in the notebook and select your preferred Python interpreter.
	- Choose your `.venv` environment to ensure all dependencies are available for your analysis.
  

## 📂 Importing Data Files

This project uses three main datasets:

- **Nutrition Values** (from Kaggle)
- **Fruit Prices 2022** (from data.gov)
- **Vegetable Prices 2022** (from data.gov)

To organize these files, we first created a `data` folder inside our `datafun_06_eda` project directory. We then downloaded the CSV files from their respective sources and placed them in the `data` folder:

- `data/nutrition_values.csv`
- `data/Fruit-Prices-2022.csv`
- `data/Vegetable-Prices-2022.csv`

This structure keeps our data organized and makes it easy to load each file in our analysis notebooks using pandas.

## 🥗 Chosen Dataset: Nutrition Values

For this project, I have chosen to work with the **Nutrition Values** dataset because nutrition is important to me. This dataset contains nutritional information for a variety of foods, including calories, carbohydrates, protein, fat, fiber, vitamins, and minerals.

**Dataset Description:**
The Nutrition Values dataset provides detailed nutritional data for many foods, which can be used to analyze dietary patterns, compare nutrients, and visualize nutrition trends.

**Local File:** [`data/nutrition_values.csv`](data/nutrition_values.csv)

**Source:** [Kaggle Nutrition Values Dataset](https://www.kaggle.com/datasets)

### 📊 Inspecting and Summarizing Data

After importing the data files, we used pandas commands to inspect and summarize our datasets:

```python
print(df.head(10))      # Display the first 10 rows
print(df.shape)         # Show the shape (rows, columns)
print(df.dtypes)        # Show data types for each column
print(df.describe())    # Show summary statistics for each column
```

These commands helped us understand the structure and key statistics of our nutrition, fruit, and vegetable data before further analysis.

## 📈 Summary of Graphs Used in EDA Notebook

Below are all the graph types used in `kristinesteele_eda.ipynb` with copiable code snippets for each:

### 1. Histogram
Shows the distribution of a single variable (e.g., calories).
```python
import matplotlib.pyplot as plt
plt.hist(df['calories'], bins=20)
plt.xlabel('Calories')
plt.ylabel('Frequency')
plt.title('Distribution of Calories')
plt.show()
```

### 2. Scatter Plot
Visualizes the relationship between two variables (e.g., calories vs. protein).
```python
plt.scatter(df['calories'], df['protein'])
plt.xlabel('Calories')
plt.ylabel('Protein')
plt.title('Calories vs. Protein')
plt.show()
```

### 3. Box Plot
Shows the spread and outliers for a variable (e.g., fiber).
```python
plt.boxplot(df['fiber'])
plt.ylabel('Fiber')
plt.title('Boxplot of Fiber')
plt.show()
```

### 4. Heatmap
Displays correlation between variables.
```python
import seaborn as sns
corr = df.corr()
sns.heatmap(corr, annot=True, cmap='coolwarm')
plt.title('Correlation Heatmap')
plt.show()
```

### 5. Pie Chart
Shows proportions of categories (e.g., fruit types).
```python
labels = df['type'].value_counts().index
sizes = df['type'].value_counts().values
plt.pie(sizes, labels=labels, autopct='%1.1f%%')
plt.title('Distribution of Fruit Types')
plt.show()
```

---
*Copy and paste these code snippets into your notebook to reproduce each graph type used in the analysis.*





