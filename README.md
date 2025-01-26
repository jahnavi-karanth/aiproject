
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
* Grouped topics as easy, moderate, or hard.

## Recommendations
* Spend more time on weak topics.
* Review moderate topics to improve.
* Keep practicing strong topics to stay consistent.

## Roadblocks and Solutions
* **Problem:** Elbow method didn’t show the best cluster number.
* **Fix:** Used silhouette scores to decide clusters.

## Future Work and Limitations
* **Limitations:**
    * No historical data used due to mismatches.
    * Analysis based only on current quiz data.
* **Next Steps:**
    * Add historical data when available.
    * Improve clustering for better grouping.