
# Personalized Student Recommendations

### Overview

This project looks at quiz performance data to help students study better. It checks quiz answers, groups questions by topic, and shows where students are strong or need improvement. It uses simple analysis and graphs to draw useful insights.

### Demo


### Prerequisites
To run this project, make sure you have the following,
* **Operating System:** Windows 10/MacOS/Linux
* **Python Version:** Python 3.8 or newer
* **Tools:** Visual Studio Code or Jupyter Notebook
* **Libraries:** Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn, NLTK, Regular Expression
* **Other Tools:** Git for version control

## Problem Statement
Analyse two types of quiz data:
1. **Current Quiz Data:** Details of the latest quiz attempt [(Quiz Submission Data)](https://www.jsonkeeper.com/b/LLQT) and document having all the questions and answers [(Quiz Endpoint)](https://www.jsonkeeper.com/b/LLQT).
2. **Historical Quiz Data:** Past performance from five previous quizzes for each student [(API Endpoint)](https://api.jsonserve.com/XgAgFJ).

The aim is to:
* Spot patterns in quiz performance.
* Highlight strengths and weaknesses.
* Suggest ways to improve study habits.

## Environment Setup
1. Clone the repository in your computer.
2. Open the project folder in Visual Studio Code.
3. Set up a Python environment:
```
conda create -p venv python -y
conda activate venv/
```
4. Install necessary libraries:
```
pip install -r requirements.txt
```
5. Run `TestlineAssignment.ipynb` by choosing the environment you have just created.

## Data Issues
### Mismatch in Historical Data:
* Historical quizzes didn’t match the current quiz topics.
* Question IDs present in Historical quiz [(API Endpoint)](https://api.jsonserve.com/XgAgFJ) were not present in All questions document (Quiz Endpoint)](https://www.jsonkeeper.com/b/LLQT).
* Historical data came from a different user, not the one preset in current quiz. Due to all these reasons, we couldn’t use Historical quiz [(API Endpoint)](https://api.jsonserve.com/XgAgFJ) for analysis. we focused only on the current quiz data [(Quiz Submission Data)](https://www.jsonkeeper.com/b/LLQT).

## Solution Approach
### 1. Prepare Data:
* Grouped questions by topic.
* Marked answers as correct or incorrect.
### 2. Clustering:
* Used **TF-IDF** to process question text.
* Applied **KMeans** to group similar questions.
* Used **silhouette** scores to decide the number of clusters.
### 3. Analyze Performance:
* Combined answers of current quiz data with question groups.
* Identified the performance and given appropriate insights.
### 4. Graphs:
* Made charts to show performance trends and topic difficulty.

## Results and Visualizations
* Charts showing performance by topic.
  <img width="849" alt="Screenshot 2025-01-26 at 3 10 48 PM" src="https://github.com/user-attachments/assets/3885aea4-c104-4942-aaa8-ce48d029850d" />

* Grouped topics as easy, moderate, or hard.
  <img width="874" alt="Screenshot 2025-01-26 at 3 10 58 PM" src="https://github.com/user-attachments/assets/0e3542e8-6411-42e8-bc2d-fe5f1c163aad" />

* Grouped topics on the basis of average score
  <img width="801" alt="Screenshot 2025-01-26 at 3 11 09 PM" src="https://github.com/user-attachments/assets/9bff0fc5-7fb7-4a53-b144-ab0911a92844" />


## Recommendations
* Spend more time on weak topics.
* Review moderate topics to improve.
* Keep practicing strong topics to stay consistent.

## Roadblocks and Solutions
* **Problem:** Elbow method didn’t show the best cluster number as it was almost a straight line without a sudden change.
  <img width="694" alt="Screenshot 2025-01-26 at 4 01 54 PM" src="https://github.com/user-attachments/assets/f41c5205-c6f5-48a0-b20e-23aaf728f579" />

* **Fix:** Used silhouette scores to decide clusters. The maximum point in the graph is the number of clusters.
  <img width="582" alt="Screenshot 2025-01-26 at 4 03 11 PM" src="https://github.com/user-attachments/assets/92d663a1-444b-480f-95aa-baff6464bb56" />


## Future Work and Limitations
* **Limitations:**
    * No historical data used due to mismatches.
    * Analysis based only on current quiz data.
* **Next Steps:**
    * Add historical data when available.
    * Improve clustering for better grouping.
