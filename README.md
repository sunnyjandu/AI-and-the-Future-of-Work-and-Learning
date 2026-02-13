# ![CI logo](https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png)

# AI and the Future of Work and Learning

Educational Institutions face increasing pressure to ensure that course content remains relevant in a labour market shaped by rapid advances in artificial intelligence and automation. To make informed decisions about curriculum design, institutions require evidence-based insights into which skills and job roles are most likely to change or decline, and which are expected to remain resilient.

This project uses the datasets from kaggle to support strategic decision-making in course content development, helping Institutions align teaching programmes more closely with future workforce needs.

## Business Requirements
1. Identify Future Skill Demands
- Determine which skills are most resistant to AI-driven automation.
- Highlight emerging skill areas that should be prioritised in course curricula.

2. Assess Job Vulnerability
- Identify job roles and career pathways that are at high, medium, or low risk of automation.
- Understand which types of roles graduates may be more or less prepared for.

3. Support Curriculum Review and Design
- Identify gaps in current course offerings relative to future job-market needs.

4. Guide Student Employability Strategy
- Support decisions on employability modules, digital skills training, and transferable skills.
- Advise students on skill development aligned with future careers.

5. Ensure Ethical and Responsible Use of Data

## Project Aim & Objectives 
To support Educational Institutions in making informed curriculum decisions by analysing how artificial intelligence is changing job roles and skill requirements in the global labour market.

The project objectives are to:
1. Analyse labour-market data to identify job roles and skills most affected by AI and automation.
2. Highlight roles and skills that are likely to decline, evolve, or remain resilient.
3. Use data visualisation to communicate workforce trends relevant to higher education.
4. Apply machine-learning techniques to predict future job demand and skill changes.
5. Develop an interactive dashboard to support evidence-based curriculum design.

## Dataset Content
I’m using the AI Impact on Jobs dataset from Kaggle. 
-  1.3M LinkedIn Jobs & Skills 2024 Dataset: [View Here](https://www.kaggle.com/datasets/asaniczka/1-3m-linkedin-jobs-and-skills-2024?utm_source=chatgpt.com) 
This dataset contains over 1.3 million job adverts collected from LinkedIn and published on Kaggle.
It shows job titles and the skills employers ask for in real job postings.

In this project, this dataset is used to understand which skills are in demand, which skills are often combined together, and which new or hybrid skills are becoming more important.

- AI Automation Risk by Job Role Dataset: [View Here](https://www.kaggle.com/datasets/khushikyad001/ai-automation-risk-by-job-role?utm_source=chatgpt.com) 
This dataset, shared on Kaggle, shows how likely different job roles are to be automated.
Each job role has a score or level that tells whether the role is at low, medium or high risk from AI and automation.

In this project, this dataset is used to understand which jobs are more vulnerable and which jobs are more resilient.

## Hypothesis and how to validate?

### Hypothesis 1: Human-centred Skills and Automation Risk

Job roles that require more human-centred skills (such as communication, creativity and problem-solving) have lower automation risk than roles based mainly on routine or repetitive tasks.

H1a: More human-centred skills -> LOWER automation risk
H1b: Repetitive tasks → HIGHER automation risk

Will validate using regression statistical method

### Hypothesis 2: Digital and Domain skills

Job roles that combine digital or AI skills with domain knowledge (such as healthcare, business, education or engineering) are growing faster than roles that require only technical skills or only non-technical skills.

H2a: Tech+Domain has LOWER automation risk than Technical-only
H2b: Tech+Domain has HIGHER growth than Technical-only

Will validate using regression statistical method 


## Project Plan

#### Phase 1 - Planning 
1. Create a GitHub repository
2. Create these folders:
data/
   raw/
   processed/
notebooks/
   etl.ipynb
   hypothsis.ipynb

3. README.md - Documenting the Process 
4. Project Kanban Board - To manage the project 
![alt text](Assets/Kanban_view2.png)

#### Phase 2 - ETL 

1. Extract (load the datasets into Python - Pandas )

- Read the LinkedIn dataset
- Read the automation risk dataset
- Save as extract.py

2. Transform 

- Clean Data 
- Split the skills
- Duplictates 
- Aggregate data etc...

3. Load
- Load clean data for next phase

#### Phase 3 -Feature Engineering & EDA 
- Feature Engineering - Create viariables needed for hypothesis testing
- Descriptive Statistics 
- Correlation Matrix

#### Phase 4 – Testing Hypothesis

- Hypothesis 1: Human-centred Skills and Automation Risk
- Hypothesis 2: Hypothesis 2: Digital and Domain skills

#### Phase 4 – Build a PowerBI Dashboard

Communicate results to institutions.
1. Extract & Load Data
2. Build your visuals - Implement Wireframe

![alt text](Assets/AI_Impact_On_Job_Market.png)

#### Phase 5 - Build the data-driven prototype (ML)

-  Build a Decision Tree Classifier

#### Phase 6 – Documentation
Final Report Must Include:

- Project Aims and Objective 
- Datasets
- ETL Process
- Hypothesis Results
- Dashboard Screenshots
- ML results
- Curriculum Recommendations


## The rationale to map the business requirements to the Data Visualisations (Todo)


## Analysis techniques used
The project used:
- Descriptive statistics
- Regression analysis
- Hypothesis testing
- A simple machine-learning prototype

Descriptive statistics were used to:
- Summarise automation risk, human-centred skills, and job growth
- Understand data distribution
- Support exploratory data analysis

To test Hypothesis 1:
- Ordinary Least Squares (OLS) regression was used

To test Hypothesis 2:
- Independent samples t-tests were used

A simple linear regression model was used as:
- A machine-learning prototype


## Ethical considerations (Redo)
This project uses two publicly available Kaggle datasets: a LinkedIn job postings and skills dataset and an AI automation risk by job role dataset. Both datasets contain aggregated information about job roles and skills. They do not include personal names, contact details, or other identifying information. Therefore, there is no direct risk to individual privacy.

However, some ethical concerns remain. The LinkedIn job postings dataset only includes jobs advertised on LinkedIn and collected by the dataset authors. This creates platform bias. Jobs from organisations or regions that do not widely use LinkedIn may be under-represented. As a result, smaller employers, informal labour markets, and roles in developing regions may not be fully reflected in the data.

The automation risk and skill measures in the AI automation risk dataset are based on secondary sources or modelling assumptions rather than direct observation. These estimates may reflect the judgement of the dataset creators and may include hidden assumptions about which jobs are more likely to be automated.



## Dashboard Design (Redo)
The project uses a single-page interactive dashboard titled “AI, Skills and Automation Risk in Job Postings.”
The dashboard contains several components designed to provide both high-level summary insights and detailed analytical visualisations.

Four KPI cards are displayed at the top of the dashboard:
- Total job postings – the total number of job records included in the dashboard
- Average automation risk – the mean automation risk score
- Average job growth – the mean projected job growth rate
- Average human-centred skills – the mean human-centred skills index
These cards provide a high-level overview of the dataset before users explore more detailed visualisations.

Scatter Plot – Human-Centred Skills and Automation Risk (H1a)
A scatter plot visualises the relationship between human-centred skills (x-axis) and automation risk (y-axis). Each point represents a job posting. This visual supports the analysis of Hypothesis 1a by illustrating the continuous relationship between the two variables.

Bar Chart – Automation Risk by Skill Group (H2a)
A bar chart compares the average automation risk between two groups:
- High AI and high domain knowledge roles (Tech+Domain proxy)
- High AI and low domain knowledge roles (Technical-only proxy)
Bar Chart – Job Growth by Skill Group (H2b)
A second bar chart compares the average job growth rate between the same two skill groups. This visual supports Hypothesis 2b.

Column Chart – Distribution of Automation Risk
A column chart displays the distribution of job postings across three automation-risk bands:
- Low
- Medium
- High
This chart provides descriptive and contextual information about the dataset.

Interactive Controls (Slicers)
The dashboard includes interactive slicers that allow users to filter the data dynamically:
- Automation risk band – allows users to filter jobs by risk category
- Job role (optional slicer) – allows exploration of individual job roles
These slicers function as interactive filtering tools and enable users to explore different subsets of the data.

Communication of Insights to Technical and Non-Technical Audiences
The dashboard was designed to support both technical and non-technical audiences.

For technical audiences:
- Precise quantitative measures (average risk and growth rates) are displayed.
- Hypothesis labels (H1a, H2a, H2b) clearly link each visual to the statistical analysis performed in Python.
- Consistent variable names are maintained between the analytical pipeline and the dashboard.
- Visual comparisons replicate the structure of the statistical tests conducted in the notebook.

For non-technical audiences:
Complex numerical outputs (such as regression tables and p-values) are replaced with intuitive visual comparisons.
- Bar charts and scatter plots present easily interpretable patterns.
- KPI cards summarise key metrics without requiring statistical knowledge.
- Filters allow users to interactively explore the data without needing to understand the underlying model.
- Dashboard Design for Communicating Complex Insights

The dashboard was structured to guide users progressively from overview to analytical insight.
At the top of the page, summary cards present high-level metrics that establish immediate context. The scatter plot is positioned prominently to communicate the continuous relationship between human-centred skills and automation risk. This is followed by grouped bar charts that focus attention on skill-group comparisons relevant to the project hypotheses. Finally, the distribution chart provides contextual information about how automation risk is distributed across the dataset.
Clear titles and hypothesis labels explicitly link each visual to a research question. The use of simple colour schemes, limited chart types, and consistent grouping definitions reduces cognitive load and prevents overwhelming non-technical users.
Interactive slicers enable users to explore the same insights across different subsets of the data, supporting exploratory analysis while preserving a coherent analytical narrative.
Overall, the dashboard translates complex, multi-step statistical and data-engineering processes into an accessible and structured visual narrative for both technical and non-technical audiences.

 'The published dashboard can be found here: link' Dashboard [View Here](https://app.powerbi.com/links/YAjlzsqQEM?ctid=c233c072-135b-431d-af59-35e05babf941&pbi_source=linkShare) 


## Development roadmap (Redo)
The project followed an iterative development process that was driven by both technical constraints and data quality challenges.

An early technical issue occurred when attempting to commit the full LinkedIn job postings dataset, which contains over one million records. Due to repository size and storage limitations, the repository had to be recreated after repeated commit failures. To resolve this issue, the dataset was trimmed to a manageable subset of approximately 50,000 job postings prior to analysis.

This reduction enabled stable version control and faster local processing but also directly affected subsequent analysis. In particular, reducing the dataset decreased the number of job postings that could be matched to the automation risk dataset, which in turn affected the statistical power of hypothesis testing. As a result, elements of the analytical approach were revised, including the grouping strategy used in Hypothesis 2.

The development process therefore progressed through the following stages: repository setup and data ingestion; identification of data storage and version control constraints; dataset sub-sampling and trimming; data cleaning, normalisation, and role matching; feature engineering and hypothesis testing; dashboard development and iterative visual refinement; and documentation and ethical review.

This roadmap reflects the need to balance computational feasibility with analytical rigour throughout the project.

## Main data analysis libraries
Python Libraries Used:
- Pandas: Data loading, cleaning, merging and feature engineering.
- NumPy: Used to support numerical operations and missing value handling.
- SciPy: To conduct statistical hypothesis testing.
- Statsmodels: Used to estimate linear regression models for Hypothesis.
- Scikit-learn: Used to build a simple predictive prototype model.

## Credits & Content
The datasets used in this project were obtained from Kaggle:
- LinkedIn Jobs and Skills Dataset (2024), Kaggle
- AI Automation Risk by Job Role Dataset, Kaggle

Generative AI tools (ChatGPT, Github Chat) were used for:
- Ideas and brainstorming
- Support in data analysis workflow coding to achieve the desired results
- EDA & hypothesthis testing choices and explanations. 

## Media
No external images, photographs or multimedia assets were used in this project.
Dashboard wireframe - created using balsamiq
Kanband snapshot - Github Kanban board 
Dashboard Snapshot - PowerBI Dashboard 

## Acknowledgements 
I would like to express my gratitude to my facilitator and cohorts for support throughout this project.