# Employee Data Analysis

## Project Overview
As a culminating project, this repository contains an analysis of a **Company's Employee Dataset**. The dataset consists of **458 rows and 9 columns**, detailing employee information across various teams. This project involves data preprocessing, insightful analysis, and graphical representations to address key business questions.

## Dataset Description
The dataset consists of the following columns:
| Column Name | Description                          |
|-------------|--------------------------------------|
| Name        | Employee's name                      |
| Team        | Team to which the employee belongs   |
| Number      | Assigned number                      |
| Position    | Position/role of the employee        |
| Age         | Employee's age                       |
| Height      | Employee's height                    |
| Weight      | Employee's weight                    |
| College     | Employee's college/university        |
| Salary      | Employee's salary                    |

## Objectives
The main goals of this project are:
1. **Data Preprocessing**: Ensure data consistency by correcting values.
2. **Data Analysis**: Extract meaningful insights through statistical calculations and visualizations.
3. **Visualization**: Represent findings visually to enhance understanding and decision-making.

## Project Workflow

### 1. Preprocessing
- Correcting the inconsistencies in the `Height` column by replacing values with **random numbers between 150 and 180**.
- missing values in the `College` column is filled with Unknown.
- Verifying data integrity and consistency before analysis.

---

### 2. Analysis Tasks
The following tasks were performed on the dataset:

#### 1: Distribution of Employees Across Teams
- **Objective**: Determine the number of employees in each team and calculate their percentage split to the total workforce.
- **Output**: Tabular and graphical representation.
  
#### 2: Segregation Based on Positions
- **Objective**: Grouping employees based on their roles within the company.
- **Output**: Summary and visualization.

#### 3: Predominant Age Group
- **Objective**: Identify the most common age group among employees.
- **Output**: Summary and Graphical representation.

#### 4: Salary Expenditure Analysis
- **Objective**: Finding the **team** and **position** with the highest total salary expenditure.
- **Output**: Salary analysis table and relevant visualizations.

#### 5: Correlation Between Age and Salary
- **Objective**: Checking if there is a correlation between employee age and salary.
- **Output**: Correlation coefficient and scatter plot.

## Requirements

### Tools
- Python 3.x
- Jupyter Notebook or any Python IDE

### Python Libraries
- pandas
- numpy
- matplotlib
- seaborn

## Results
The key findings of the project include:
1. **Employee Distribution**: Visualized team-wise employee count and percentage split.
2. **Position Segregation**: Employees categorized based on their roles.
3. **Age Analysis**: Identified the dominant age group.
4. **Salary Insights**: Teams and positions with the highest salary expenditures.
5. **Correlation**: Examined the relationship between age and salary.

## How to Use
1. Clone this repository.
2. 2. Navigate to the project directory.
3. 3. Open and run the project notebook.

## Conclusion
This project successfully analyzed the given company's employee dataset, providing insights into team distribution, salary trends, and the relationship between age and salary. The graphical visualizations enhance the understanding of key trends and patterns.
