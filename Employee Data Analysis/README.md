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
### 1. Importing the excel file and necessary modules.
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```
![Importing and reading](https://github.com/user-attachments/assets/0060396c-0fab-4231-832f-f1345ec3834a)

### 2. Preprocessing
- Correcting the inconsistencies in the `Height` column by replacing values with **random numbers between 150 and 180**.
```
df['Height'] = np.random.randint(150, 181, size=len(df))
df
```
![Screenshot 2024-12-17 120243](https://github.com/user-attachments/assets/10b36800-f797-4e53-aaba-1eb4d192181d)

- We filled missing `Salary` values with the mean salary and replaced missing `College` names with "Unknown."
```
df['Salary'].fillna(df['Salary'].mean(), inplace=True)
df['College'].fillna('Unknown', inplace=True)
df
```  
![Screenshot 2024-12-17 120333](https://github.com/user-attachments/assets/c8870d6c-b1f6-4fc3-b184-53ed66a45c85)
  
- Verifying data integrity and consistency before analysis.
```
df.isnull().sum() 
df.duplicated().sum()
```

![Screenshot 2024-12-17 122106](https://github.com/user-attachments/assets/490d950e-b38f-463c-9080-2244d9caeb8e)

---

### 3. Analysis Tasks
The following tasks were performed on the dataset:

#### 1: Distribution of Employees Across Teams
- **Objective**: Determine the number of employees in each team and calculate their percentage split to the total workforce.
```
df['Team'].value_counts()
team_distribution = df['Team'].value_counts()
total_employees = len(df)
team_percentage = (team_distribution / total_employees) * 100
team_percentage
```
- **Output**: Tabular and graphical representation.
![Screenshot 2024-12-17 120425](https://github.com/user-attachments/assets/915c99d5-9c37-4fad-8fd1-0365109e5dfc)

![Screenshot 2024-12-17 120437](https://github.com/user-attachments/assets/dd4bed5e-701b-48f6-a8a6-5be704755dc8)

#### 2: Segregation Based on Positions
- **Objective**: Grouping employees based on their roles within the company.
  ```
  employees = df.groupby('Position')['Name'].apply(list)
  for Position, Names in employees.items():
  print(f"employees in {Position} position:")
    for name in Names:
     print(name)
    print("\n")
  position_distribution = df['Position'].value_counts()
  position_distribution
- **Output**: Summary and visualization.
- 
  ![Screenshot 2024-12-17 120453](https://github.com/user-attachments/assets/21b6ff41-a4f2-44e7-ace3-8a49ddfc7b86)


  ![Screenshot 2024-12-17 120503](https://github.com/user-attachments/assets/a38c435a-ea33-4a94-9042-66e946e6c38a)

#### 3: Predominant Age Group
- **Objective**: Identify the most common age group among employees.
```
df['Age Group'] = df['Age'].apply(lambda age:'20-25' if 20 <= age <= 25 else ('26-30' if 26 <= age <= 30 else ('31-35' if 31 <= age <= 35 else '36 and above')))
df
df['Age Group'].value_counts()
```

- **Output**: Summary and Graphical representation.

  ![Screenshot 2024-12-17 120522](https://github.com/user-attachments/assets/d5ef654d-1898-4438-83b5-f55d9b2a2f00)

  ![Screenshot 2024-12-17 123246](https://github.com/user-attachments/assets/baaefe1f-4410-4a4a-926e-c6d7ed57e683)


#### 4: Salary Expenditure Analysis
- **Objective**: Finding the **team** and **position** with the highest total salary expenditure.
```
team_salary = df.groupby('Team')['Salary'].sum().sort_values(ascending=False)
position_salary =df.groupby('Position')['Salary'].sum().sort_values(ascending=False)
team_salary,position_salary

highest_salary_team = team_salary.idxmax()
highest_salary_position = position_salary.idxmax()

print(f"Team with the highest salary: {highest_salary_team}")
print(f"Position with the highest salary: {highest_salary_position}")
```
  
- **Output**: Salary analysis table and relevant visualizations.

  ![Screenshot 2024-12-17 123306](https://github.com/user-attachments/assets/260e8eb6-a49d-47eb-9c5e-68e225d10141)

  ![Screenshot 2024-12-17 123402](https://github.com/user-attachments/assets/d79e7766-e75a-4ebd-926f-65f061ac39da)

#### 5: Correlation Between Age and Salary
- **Objective**: Checking if there is a correlation between employee age and salary.
```
Correlation = df['Salary'].corr(df['Age'])
print("The correlation b/w Salary and Age is ",Correlation)
```
  
- **Output**: Correlation coefficient and scatter plot.

  ![Screenshot 2024-12-17 123422](https://github.com/user-attachments/assets/7164f18e-1289-4ea0-a99b-e7f00c44da56)

  ![Screenshot 2024-12-17 123431](https://github.com/user-attachments/assets/1602b3de-81d6-41b8-a0c3-d8fd993c2f0e)

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

2. 
3. **Position Segregation**: Employees categorized based on their roles.
4. **Age Analysis**: Identified the dominant age group.
5. **Salary Insights**: Teams and positions with the highest salary expenditures.
6. **Correlation**: Examined the relationship between age and salary.

## How to Use
1. Clone this repository.
2. Navigate to the project directory.
3. Open and run the project notebook.
4. 
## Conclusion
This project successfully analyzed the given company's employee dataset, providing insights into team distribution, salary trends, and the relationship between age and salary. The graphical visualizations enhance the understanding of key trends and patterns.
