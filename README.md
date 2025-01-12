## Red Wine Quality

**Objectives**
- Practice choosing variables and their transformations for a model.
- Practice fitting a linear regression model.
- Practice interpreting a fitted model’s coefficients and communicating uncertainty around them.

**IMPORTANT: plotly.express is used for graphs in this work. To see them, Notebook has to be run locally**

Kagle data set [Red Wine](https://www.kaggle.com/datasets/uciml/red-wine-quality-cortez-et-al-2009) is used for analysis. 

Bellow written introduction about the data is from Publications related to this data set: 

P. Cortez, A. Cerdeira, F. Almeida, T. Matos and J. Reis. Modeling wine preferences by data mining from physicochemical properties. In Decision Support Systems, Elsevier, 47(4):547-553, 2009.

*This work will consider vinho verde, a unique product from the Minho (northwest) region of Portugal. The data were collected from May/2004 to February/2007 using only protected designation of origin samples that were tested at the official certification entity. The data were
recorded by a computerized system (iLab), which automatically manages the process of wine sample testing from producer requests to laboratory and sensory analysis. Each entry denotes a given test (analytical or sensory) and the final database was exported into a single sheet (.csv).*

*During the preprocessing stage, the database was transformed in order to include a **distinct wine sample** (with all tests) per row. To avoid discarding examples, only the most common physicochemical tests were selected.*

### Project Goal
The purpose of this project is to analyze the Red Wine Quality dataset and identify which variables influence perceived wine quality the most by fitting a statistical model. Worth to mention, that focus here will be to create explanatory model (to understanding factors that influence wine quality) rather than predictive model.

### Summary
- Original dataset was splitted in to **Train** and **Test**.
- Ordinal Logistics Regression was chosen for modeling.
- 2 variables were not included in Model because of VIF higher than 4.
- 1 variable was excluded from Model because of p-value higher than 0.05.
- Positive Model coefficients indicate factors that improve the chances of higher wine quality (e.g., alcohol, sulphates).
- Negative Model coefficients indicate factors that decrease the chances of higher wine quality (e.g., volatile acidity, total sulfur dioxide).
- Model accuracy score is almost the same for **Train** (0.568) and **Test** (0.565) data.
- Confusion matrix shows slightly better clasification for **Test** data.
- Classification report results are very similar for **Train** and **Test** data.
- Breakpoints show that up till ~10 % (of **Alcohol** %) highest probability is for **Quality** = 5. From ~10 % to ~13.5 % highest probability is for **Quality** = 6, and above 13.5 % **Quallity** = 7.

### Suggestions for additional analysis and improvement
- Multinomial Logistic regression with weights to solve class imbalance.
- For simplified decision - Logistic Regression with 2 classes, e.g. "Good", and "Bad".
- Linear Regression for prediction of wine **Quality**.
- Ensure that the analysis accounts for potential multiple testing (using methods like Bonferroni correction) if many variables are assessed simultaneously.
- Additionl information about exact type of wine would add clarity to duplicates part. For current analysis duplicates were kept, as there was no clear evidence that these are the same values.
- Investigate effect of outliers, by capping them at some level if that could make **Quality** level differ from each other.



### Structure
wine.ipynb: Jupyter Notebook for this project,

winequality-red.csv: data set for this project,

README.md: Provides an overview and instructions for the projects.

requirements.txt: Provides list of packages to be installed what will be needed for anlysis.

```
pip install -r requirements.txt