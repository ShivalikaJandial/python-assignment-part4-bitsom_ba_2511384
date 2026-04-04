# Student Performance Analysis & Prediction
**Assignment Part 4: Data Visualization & Machine Learning**

## Project Overview
In this project, I performed an end-to-end data analysis on a student performance dataset. I used **Pandas** for data manipulation, **Matplotlib** and **Seaborn** for exploratory data visualization, and **Scikit-learn** to build a Logistic Regression model that predicts whether a student will pass or fail based on their grades and habits.

## Files in this Repository
* `part4_visualization_ml.ipynb`: The main Jupyter notebook containing all code, analysis, and rendered plots.
* `students.csv`: The raw dataset used for this analysis.
* `plot1_bar.png` to `plot5_line.png`: Visualizations created using Matplotlib.
* `plot6_seaborn_bar.png` and `plot7_seaborn_scatter.png`: Visualizations created using Seaborn.
* `plot8_feature_importance.png`: A visual breakdown of which factors most influenced the model's predictions.

---

## Technical Approach & Logic

### Task 1: Data Exploration (Pandas)
I started by loading the `students.csv` file. To get a feel for the data, I used `.describe()` to look at the distribution of scores and `.value_counts()` to see the balance between passing and failing students. 
* **Key Logic**: To find the top student, I calculated a temporary average across all subject columns using `mean(axis=1)`. This allowed me to rank students by overall academic performance rather than just a single subject.

### Task 2: Matplotlib Visualizations
I created five distinct plots to visualize different aspects of the data:
* **Bar Chart**: Average scores per subject to see which subjects students find most difficult.
* **Histogram**: Distribution of Math scores, including a vertical dashed line for the mean to show how many students were above or below average.
* **Scatter Plot**: Study hours vs. Average scores, color-coded by Pass/Fail status. This clearly showed the correlation between effort and results.
* **Box Plot**: Compared attendance percentages between passing and failing students to identify outliers.
* **Line Plot**: Tracked Math and Science scores student-by-student to see performance trends across the class.

### Task 3: Seaborn & Comparison
I used Seaborn to create more complex statistical plots with less code.
* **My Reflection**: I found that Seaborn is much better at handling categorical data and "hue" mapping automatically. For example, creating a regression line over a scatter plot (`sns.regplot`) took significantly less manual grouping compared to Matplotlib. However, Matplotlib still feels more reliable for fine-tuning specific layout details.

### Task 4: Machine Learning Pipeline
I built a binary classifier using **Logistic Regression**.
1. **Preprocessing**: I separated the features (grades, attendance, study hours) from the target (`passed`). I used `StandardScaler` to normalize the data, which is essential for Logistic Regression so that features with different scales (like study hours vs. math scores) are treated fairly.
2. **Training**: I split the data (80% train, 20% test). Even with a small dataset, the model was able to learn basic patterns.
3. **Feature Importance**: By extracting the model coefficients, I discovered which factors (like attendance or study hours) had the strongest positive or negative impact on the "Pass" prediction. I visualized this using a horizontal bar chart where green bars represent factors that help a student pass.

---

## How to Run
1. Ensure you have the required libraries installed:
   ```bash
   pip install pandas matplotlib seaborn scikit-learn
   ```
2. Open the Jupyter notebook:
   ```bash
   jupyter notebook part4_visualization_ml.ipynb
   ```
3. Run all cells to see the data analysis and model predictions.

## Conclusion
Even though the dataset was small, the analysis clearly shows that **attendance** and **study hours** are high predictors of success. The machine learning model provides a basic framework that could be scaled with a much larger dataset for better accuracy.

---
### Submission Checklist
- [x] Jupyter notebook with all outputs visible.
- [x] All 8 generated plots (.png files) uploaded.
- [x] Logic explained through comments in the code.
- [x] Repository is public and accessible.
