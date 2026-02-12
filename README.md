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

### Hypothesis 2: Digital and Domain skills

Job roles that combine digital or AI skills with domain knowledge (such as healthcare, business, education or engineering) are growing faster than roles that require only technical skills or only non-technical skills.


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
![alt text](images/AI_Impact_On_Job_Market.png)

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


## The rationale to map the business requirements to the Data Visualisations
* List your business requirements and a rationale to map them to the Data Visualisations
First – a very important data note
Match rate: 14.4%

This means:

➡️ Only about 14% of job postings could be matched to a role in the automation-risk dataset.

So all your hypothesis tests are based on a much smaller subset of the 50,015 jobs.

That’s not wrong — but it does explain why:

effects look weak

models explain very little variance

You should mention this as a limitation.

✅ H1a

More human-centred skills → lower automation risk

Your regression:

human_centred_index coef = -0.1218
p < 0.001
R² = 0.004
✔ Interpretation

The coefficient is negative

The p-value is significant

So:

👉 Jobs with higher human-centred skills tend to have slightly lower automation risk

But…
R-squared = 0.004

This means:

👉 human-centred skills explain only 0.4% of the variation

✔ What you should say

H1a is statistically supported, but the effect is very small.

A clean sentence:

Human-centred skills are significantly associated with lower automation risk, however the relationship is weak and explains only a very small proportion of variance.

✅ H1b

Repetitive tasks → higher automation risk

Your regression:

task_repetition_level coef = 0.0025
p = 0.827
✔ Interpretation

p-value is very large

coefficient is almost zero

👉 No evidence of a relationship.

✔ What you should say

H1b is not supported.

Simple:

Task repetition level does not significantly predict automation risk in this dataset.

✅ H2a

Tech+Domain roles have lower automation risk than Technical-only

Your results:

Mean risk Tech+Domain    = 0.273
Mean risk Technical-only = 0.626
t = -2.237
one-sided p = 0.036
✔ Interpretation

Tech+Domain mean is much lower

one-sided p < 0.05

👉 This supports your hypothesis.

✔ What you should say

H2a is supported.

Example sentence:

Roles that combine technical and domain skills have significantly lower automation risk than technical-only roles.

✅ H2b

Tech+Domain roles grow faster than Technical-only

Your results:

Mean growth Tech+Domain    = 0.073
Mean growth Technical-only = 0.034
t = 0.581
one-sided p = 0.292
✔ Interpretation

Tech+Domain is higher on average

but…

👉 p = 0.292 → not significant

✔ What you should say

H2b is not supported.

You can say:

Although Tech+Domain roles show higher average job growth, the difference is not statistically significant.

✅ Your plots match the statistics
H1a scatter

You saw a cloud with a very weak downward pattern.

That matches:

R² = 0.004

So visually:
➡️ weak relationship = correct.

H1b scatter

Completely flat cloud.

That matches:

p = 0.827
H2 bar charts

Big visual difference for automation risk ✔
Small and noisy difference for growth ✔

✅ ML prototype
R^2 : 0.01
RMSE: 0.266
✔ Interpretation

The model explains about 1% of variance.

This is not a strong predictive model.

But that is totally fine because your notebook clearly says:

ML prototype (predictive demo)

✔ What you should say

The machine learning model has very limited predictive power and is used only as a demonstration of a simple predictive workflow.

✅ One more important thing you should explicitly mention

Look at this:

Joined df shape: 1,125,625
Rows after dedupe: 50,015

This large jump happens because:

many job titles match the same role

and roles are duplicated during the merge

You correctly fixed this with:

drop_duplicates("job_link")

So your final dataset is correct — but it is good practice to briefly mention this in your methodology.

✅ Final summary you can literally reuse

You can write something like this:

H1a was supported: human-centred skills were significantly associated with lower automation risk, although the effect size was very small.
H1b was not supported: task repetition level did not significantly predict automation risk.
H2a was supported: roles combining technical and domain skills had significantly lower automation risk than technical-only roles.
H2b was not supported: Tech+Domain roles showed higher average growth, but the difference was not statistically significant.

A key limitation of the study is the low role-matching rate (14.4%), which substantially reduced the effective sample size and may weaken observed relationships.


## Analysis techniques used
* List the data analysis methods used and explain limitations or alternative approaches.
* How did you structure the data analysis techniques. Justify your response.
* Did the data limit you, and did you use an alternative approach to meet these challenges?
* How did you use generative AI tools to help with ideation, design thinking and code optimisation?

## Ethical considerations
* Were there any data privacy, bias or fairness issues with the data?
* How did you overcome any legal or societal issues?

## Dashboard Design
* List all dashboard pages and their content, either blocks of information or widgets, like buttons, checkboxes, images, or any other item that your dashboard library supports.
* Later, during the project development, you may revisit your dashboard plan to update a given feature (for example, at the beginning of the project you were confident you would use a given plot to display an insight but subsequently you used another plot type).
* How were data insights communicated to technical and non-technical audiences?
* Explain how the dashboard was designed to communicate complex data insights to different audiences. 

## Unfixed Bugs
* Please mention unfixed bugs and why they were not fixed. This section should include shortcomings of the frameworks or technologies used. Although time can be a significant variable to consider, paucity of time and difficulty understanding implementation are not valid reasons to leave bugs unfixed.
* Did you recognise gaps in your knowledge, and how did you address them?
* If applicable, include evidence of feedback received (from peers or instructors) and how it improved your approach or understanding.

## Development Roadmap
Challenges - had to create the repoistory again due to commit issue i was facing - this was due to large data not enough storage space. 

## Deployment
### Heroku

* The App live link is: https://YOUR_APP_NAME.herokuapp.com/ 
* Set the runtime.txt Python version to a [Heroku-20](https://devcenter.heroku.com/articles/python-support#supported-runtimes) stack currently supported version.
* The project was deployed to Heroku using the following steps.

1. Log in to Heroku and create an App
2. From the Deploy tab, select GitHub as the deployment method.
3. Select your repository name and click Search. Once it is found, click Connect.
4. Select the branch you want to deploy, then click Deploy Branch.
5. The deployment process should happen smoothly if all deployment files are fully functional. Click now the button Open App on the top of the page to access your App.
6. If the slug size is too large then add large files not required for the app to the .slugignore file.


## Main Data Analysis Libraries
* Here you should list the libraries you used in the project and provide an example(s) of how you used these libraries.


## Credits 

* In this section, you need to reference where you got your content, media and extra help from. It is common practice to use code from other repositories and tutorials, however, it is important to be very specific about these sources to avoid plagiarism. 
* You can break the credits section up into Content and Media, depending on what you have included in your project. 

### Content 

- The text for the Home page was taken from Wikipedia Article A
- Instructions on how to implement form validation on the Sign-Up page was taken from [Specific YouTube Tutorial](https://www.youtube.com/)
- The icons in the footer were taken from [Font Awesome](https://fontawesome.com/)

### Media

- The photos used on the home and sign-up page are from This Open-Source site
- The images used for the gallery page were taken from this other open-source site



## Acknowledgements (optional)
* Thank the people who provided support through this project.