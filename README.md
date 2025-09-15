# Phase 1: Business Understanding

---


## Problem Statement
The English Wikipedia article for Zambia lacks several standard sections found in well-developed country pages, such as Infrastructure, Transportation, Environment, detailed Health Care, and expanded Culture. This reduces the completeness and utility of the page. Our project aims to systematically detect these missing or underdeveloped sections through structured, data-driven analysis.

## 1.1 Business Objectives
Our goal is to identify content gaps in the Zambia Wikipedia page to:
- Help Wikipedia editors prioritize content improvements.
- Provide educators and researchers with a quick reference for missing topics.
- Develop a repeatable method for assessing completeness in other country pages.

Success means delivering an evidence-based list of missing or underdeveloped sections, verified against a benchmark set of complete country pages.

**Desired Outcome:**  
A report and visualizations showing completeness scores per page and a ranked list of the most frequently missing sections.

**Business Success Criteria:**
- Stakeholders (editors, researchers) can use the output to prioritize editing efforts.
- Increased representation of Zambia on Wikipedia within 3–6 months after insights are shared.
- More comprehensive pages that enhance public knowledge about Zambia.

---

**Stakeholders:**
- Wikipedia editors (especially Zambian contributors)
- Students and researchers
- Educational institutions
- General public

**Desired Outcome:**  
A report and visualizations showing completeness scores per page and a ranked list of the most frequently missing sections.

**Business Success Criteria (Real-world):**
- Stakeholders (editors, researchers) can use the output to prioritize editing efforts.
- Increased representation of Zambia on Wikipedia within 3–6 months after insights are shared.
- More comprehensive pages that enhance public knowledge about Zambia.

---
## 1.2 Assess Situation

**Resources:**
- Wikipedia API for content retrieval
- Python environment (Google Colab/Jupyter Notebook)
- Libraries: `wikipedia-api`, `pandas`, `matplotlib`, `seaborn`
- Team members with skills in programming, data processing, and visualization

**Constraints:**
- Analysis is limited to structure, not factual accuracy
- Wikipedia content changes frequently, affecting reproducibility

**Risks:**
- API rate limits or downtime
- Variation in page structures
- Possible mismatch between our template and Wikipedia editorial norms

**Assumptions:**
- Selected standard template reflects an ideal structure for general topic pages
- Wikipedia API will remain stable during the project timeline

---

## 1.3 Determine Data Mining Goals

**Overall Data Mining Objective:**
Translate the business objective of improving Zambia’s Wikipedia representation into a technical process that measures completeness.

**Specific Data Mining Goals:**
1. Extract section headings from selected Zambia-related Wikipedia pages using the Wikipedia API.
2. Pre-process and normalize section titles for accurate comparison.
3. Compare the extracted structure against a predefined standard section template.
4. Calculate a completeness score for each page.
5. Identify and rank the most frequently missing sections across all pages.

**Data Mining Success Criteria (Technical):**
- 100% accuracy in detecting section presence/absence compared to manual verification for at least 2 sample pages.
- Completeness scores computed without data loss or parsing errors.
- Identification of at least 3 consistently missing sections across all pages.

---
## 1.4 High-Level Timeline & Phases:

### High-Level Timeline & Phases

| **Phase** | **Description** | **Deliverable** |
|-----------|-----------------|-----------------|
| **1. Business Understanding** | Define problem, goals, and success criteria | BU section in Notebook + `README.md` |
| **2. Data Understanding** | Explore data from 1–2 sample pages, check section structure | Sample raw data, API test results |
| **3. Data Preparation** | Clean, normalize, and structure data for scoring | Preprocessed data CSV |
| **4. Modelling** | Implement completeness scoring algorithm | Scoring function, results table |
| **5. Evaluation** | Verify accuracy by manual inspection of sample pages | Validation notes |
| **6. Deployment** | Finalize report, visualizations, and presentation | ACM report, slides, GitHub repo |


**Initial Assessment of Tools and Techniques**

- **Data Collection**:  
  - Wikipedia API  

- **Text Processing**:  
  - Natural Language Processing libraries

- **Analysis**:  
  - Python pandas  
  - scikit-learn for classification  

- **Visualization**:  
  - matplotlib  
  - seaborn for presenting findings  

- **Version Control**:  
  - GitHub with tagged commits

---
## 1.5 Cost And Benefit Analysis

**Costs:**
- Time investment in coding, testing, and documentation.
- Limited API calls if rate-limiting occurs (minor for our dataset size).

**Benefits:**
- Provides actionable insights to improve Zambia’s online representation.
- Lightweight, reproducible method for other countries or topics.
- Can be automated to run periodically for continuous monitoring.

# 2. Data Understanding

## Objective
The objective of this phase is to perform an initial exploration of our dataset(s).  
We aim to:
- Get a "feel" for the data,
- Identify its main characteristics,
- Spot potential quality issues,
- Prepare for data cleaning and transformation in the next phase.

---

# 2.1. Initial Data Collection

### Interpretation of initial data collection sectiom
- Installs the Wikipedia API library.  
- Imports Wikipedia API and pandas.  
- Initializes a Wikipedia API object in English with a custom user agent.
- Defines a function to extract all sections (with hierarchy levels) from a Wikipedia page.  
- Collects sections from Wikipedia pages of Zambian provinces.  
- Stores the extracted data (province, section title, depth) in a list.  
- Converts the list into a DataFrame and saves it as a CSV file.  
- Displays the first 20 rows of the DataFrame. ##

# 2.2. Data Description
- Checks the dataset’s shape (rows and columns).  
- Prints dataset information (column types and non-null counts).  
- Shows descriptive statistics for numeric columns.  
- Displays the first 10 rows.  
- Counts unique provinces and unique sections.

# 2.3. Data Exploration
- Imports Matplotlib and Seaborn for visualization.  
- Plots a histogram showing how section depths are distributed across the dataset.  
- The horizontal bar chart shows the number of sections for each Zambian province page.
- Identifies the 20 most frequent section titles across all provinces.  
- A horizontal bar chart showing their frequencies.

# 2.4. verfication of Data Quality

# 2.5. Summary of Initial Findings

In our initial analysis, we loaded a dataset containing all the Wikipedia pages about the provinces in Zambia. Upon describing the data, we observed the following:

- **Depth of Pages:** Most Wikipedia pages on the provinces had a depth of 2, indicating that sub-sections were limited.
- **Section Naming Variability:** Some sections had different naming conventions across pages, which may appear as anomalies in the analysis.
- **Number of Sections by Province:**
  - **Central Province:** 12 sections (most sections in the dataset)
  - **Western Province:** 12 sections
  - **Copperbelt Province:** 8 sections (least sections in the dataset)
- **Missing Sections:** The quality report noted that Central and Southern Provinces had the most missing common sections (2 missing sections each), which is an anomaly considering that Central Province has the highest number of sections in the dataset.

  ---
# 3. Data Preparation

## 3.1 Data Loading
Phase where we loaded the data collected in the previous stage
## 3.2  Filtering Non-Informative Headers
## 3.4 Creating the Master Vocabulary
## 3.5 Vectorizing Articles
phase where each article was converted to a binary vector representation
## 3.6 Complete Data Preparation Pipeline
Here we Put together an executable pipeline
Not all section headers are meaningful for our analysis. We filter out administrative and navigation sections

# 4. Modeling
#### Setup and Data Loading.
#### 4.1. Association Rule Mining (Apriori).
#### 4.2. Supervised Classification
##### 4.2.1. Decision Tree Classifier
##### 4.2.2. Random Forest Classifier
##### 4.2.2. Random Forest Classifier
##### 4.2.3. k-Nearest Neighbors (k-NN) Classifier
#### 4.3. Model Comparison & Conclusion

# 5. Evaluation
#### 5.1 Evaluation of results and key findings
**Project Objective:**  
To identify structural gaps in Zambian Wikipedia articles by finding sections that are common in high-quality *Featured* articles but frequently missing from Zambian ones.

**Success Criteria:**  
The project is successful if we can produce a data-driven, ranked list of such sections.

**Evaluation:**  
Our Random Forest model successfully distinguished between article classes with ~90% accuracy, proving that a structural difference exists. The feature importance from this model provided a ranked list of the most discriminative sections.  

Our final analysis calculated the **prevalence gap** for these top sections between the two article categories.

# 6. Deployment
### 6.1. Project Summary and Findings

This project followed the CRISP-DM methodology to analyze the structure of Zambian Wikipedia articles with the goal of identifying common missing sections compared to a benchmark of high-quality "Featured" articles.

**Data Collection & Preparation:** We successfully collected and prepared a dataset of 227 Zambian articles and 400 Featured articles. We extracted, cleaned, and vectorized the section headers using TF-IDF for modeling.  

**Modeling:** We trained three classification models. The Random Forest Classifier was selected as the final, best-performing model, achieving approximately 90% accuracy in distinguishing between the two article categories based solely on their section structure.  

**Key Insight:** The most valuable result from the Random Forest model was its feature importances, which gave us a data-driven list of the sections most characteristic of a high-quality article. Our final evaluation analysis compared the prevalence of these top sections and identified a clear "content gap." Sections like *histori* (history), *recept* (reception), *legaci* (legacy), and *background* were found to be significantly more common in Featured articles than in Zambian articles.  

---

