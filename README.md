# Google Advanced Data Analytics Course Project: TikTok Claims Classification Scenario
**Daniel Poe, 2025-06-27**

This is a course project that I have completed as part of the [Google Advanced Data Analytics Professional Certificate](https://www.coursera.org/professional-certificates/google-advanced-data-analytics). This certificate builds on data analytics skills and experience to take careers to the next level. It is designed for graduates of the [Google Data Analytics Certificate](https://www.coursera.org/professional-certificates/google-data-analytics) or people with equivalent data analytics experience. This course enables learners to expand their knowledge through practical, hands-on projects that feature Jupyter Notebook, Python, and Tableau. Course participants can learn the following:

- Explore the roles of data professionals within an organization 
- Create data visualizations and apply statistical methods to investigate data
- Build regression and machine learning models to analyze and interpret data
- Communicate insights from data analysis to stakeholders

This notebook will cover each of the end-of-course projects as a demonstration of skills gained throughout the certificate program. I have completed this at an earlier date, but I have decided to compile everything into one notebook here for ease of reference.

At the time of writing and compilation, I have learnt to use the Polars package through the [DataCamp - Introduction to Polars](https://app.datacamp.com/learn/courses/introduction-to-polars) course. I will utilise the new skills I have learned during that course in the compiled notebook.

The final compiled notebook can be viewed [here](https://github.com/daniel207pzd/Google-Advanced-Data-Analytics-Course-Project-TikTok-Claims/blob/main/Google%20Advanced%20Data%20Analytics%20-%20TikTok%20Claims%20Course%20Project%20(Daniel%20Poe).ipynb).

## Background

![tiktok-logo-evolution_2018](https://github.com/user-attachments/assets/92261f0b-b1fe-4900-805a-7e009a850a48)

At TikTok, our mission is to inspire creativity and bring joy. Our employees lead with curiosity and move at the speed of culture. Combined with our company's flat structure, you will be given dynamic opportunities to make a real impact on a rapidly expanding company and grow your career.

TikTok users have the ability to submit reports that identify videos and comments that contain user claims. These reports identify content that needs to be reviewed by moderators. The process generates a large number of user reports that are challenging to consider in a timely manner. 

TikTok is working on the development of a predictive model that can determine whether a video contains a claim or offers an opinion. With a successful prediction model, TikTok can reduce the backlog of user reports and prioritise them more efficiently.

### Team Members at TikTok
#### Data Team Roles

- Willow Jaffey - Data Science Lead
- Rosie Mae Bradshaw - Data Science Manager
- Orion Rainier - Data Scientist

The members of the data team at TikTok are well-versed in data analysis and data science. Messages to these more technical coworkers should be concise and specific.

#### Cross-Functional Team Members

- Mary Joanna Rodgers - Project Management Officer
- Margery Adebowale - Finance Lead, Americas
- Maika Abadi - Operations Lead

Your TikTok team includes several managers who oversee operations. It is important to adjust your general correspondence appropriately to their roles, given that their responsibilities are less technical in nature. 

***Note:*** The story, all names, characters, and incidents portrayed in this project are fictitious. No identification with actual persons (living or deceased) is intended or should be inferred. And, the data shared in this project has been created for pedagogical purposes. 

## Business Task
To develop a predictive model to accurately classify TikTok videos as containing either a claim or an opinion. Successful model implementation will reduce the backlog of user reports and enable more efficient prioritisation of content moderation efforts.

## Dataset
This project uses a dataset called tiktok_dataset.csv. It contains synthetic data created for this project in partnership with TikTok. The dataset contains 19,383 rows and 12 columns. Each row represents a different published TikTok video in which a claim/opinion has been made.

## Exploratory Data Analysis (EDA) Tableau Visualisations
While I was carrying out EDA, I also used Tableau to create visuals to help non-technical stakeholders engage and interact with the data. The Tableau visualisations can be found [here](https://public.tableau.com/app/profile/daniel.poe/viz/GoogleAdvancedDataAnalyticsTikTokClaimsCourseProjectTableauVisualisationsDanielPoe/ClaimClassificationsDatasetEDA).

## Modelling and Evaluation
A random forest model and an XGBoost model were built and compared. Based on the classification reports, both models were found to be near perfect. However, the errors of the XGBoost model tended to be false negatives. Identifying claims was the priority in this project. Therefore, it is essential that the model accurately captures all actual claim videos. The random forest model has better scores and is thus selected as the champion model.

The confusion matrix and feature importance plot of the random forest model using the test data are shown below.
![image](https://github.com/user-attachments/assets/15cf40bc-bf16-472f-991c-62baa4f810a9)
![image](https://github.com/user-attachments/assets/a6508b68-4c6e-49f0-807d-d4eda3ca98b4)

The most predictive features were all related to engagement levels generated by the video.

## Conclusion
As noted, the model performed exceptionally well on the test holdout data. Before deploying the model, the data team recommends further evaluation using additional subsets of user data. Furthermore, the data team recommends monitoring the distributions of video engagement levels to ensure that the model remains robust to fluctuations in its most predictive features.
