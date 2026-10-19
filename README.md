# Education project

> This project looks at the relationships between ACT/SAT scores and several socioeconomic factors.

\---

## Project Overview

This project uses two education-based datasets (described below) to explore correlations between socioeconomic factors and ACT scores. A strong correlation was found between average ACT scores and economic background.

* **Objective:** Clearly state the main goal of the project.
* **Domain:** Education
* **Key Techniques:** Regression
  
\---

## Project Structure

```
├── data/                 # Raw and processed data
├── code/                 # Jupyter notebooks and Python scripts
├── reports/              # Generated reports and visualizations
├── requirements.txt      # Dependencies
└── README.md             # Project documentation
```

\---

## Data

* **Source:** https://github.com/brian-fischer/DATA-5100/blob/main/EdGap\_data.xlsx
* **Description:** Data from EdGap accessed through the Data 5100 GitHub repository.

  * Contains information on ACT/SAT scores reported per school, as well as socioeconomic statistics about that school district. Excel format.
* **Source:** https://www.dropbox.com/s/lkl5nvcdmwyoban/ccd\_sch\_029\_1617\_w\_1a\_11212017.csv?dl=1
* **Description:** Public information regarding each school from the National Center for Education Statistics. CSV format.

\---

## Analysis

All analysis performed in submitted Jupyter notebook, run in order from top to bottom.

Initial exploratory analysis involved finding correlation coefficients between variables with a heatmap and pair plots, identifying outliers with boxplots/IQR, and proposing further steps for analysis.

Single predictor ordinary least squares regression models were performed for the median income, percent married parent households, and percent of students qualified for reduced-price lunch (fig. 2). P-values, R-squared, RMSE, and mean absolute error were also calculated for each model. Residual plots were also produced to assess the fit of the linear model.

A multiple variable ordinary least squares regression model using all five socioeconomic numerical predictor variables to predict the average ACT score was performed. 

Variables with large p-values (percent married and median income) were dropped for the reduced variable model, which was created in the same way. Residual plots were also produced to assess the fits of both models. Mean absolute error and R-squared were calculated and were nearly identical across the full and reduced models. An ANOVA was also performed between the two models and found no significant differences.

A scaled reduced model was produced by normalizing the reduced number of numerical predictor variables. Mean absolute error and R-squared were calculated and were identical across the reduced and normalized reduced models.


\---

## Results

The variable with the highest correlation and highest predictive power in regards to average ACT score was the percentage of students who qualified for free or reduced-price lunch. 
This is likely due to the fact that the other four socioeconomic variables are census tract data and come from the areas surrounding the school and may, therefore, not be fully reflective of the student population because students may travel to other nearby districts or census tracts to attend school, whereas the proportion of students at a particular school who qualify for free or reduced-price lunch is a direct measure of the socioeconomic status of that school’s student population.
These models demonstrate a strong negative correlation between the proportion of students at a school who qualify for free or reduced-price lunch and that school’s average ACT score. We can also, therefore, conclude that as the proportion of students whose family’s income is at or below 185% of the Federal poverty line rises, the average ACT score of that school will fall.
This demonstrates a direct relationship between poor economic background and poor ACT scores.

\---

## Authors

* Jacqueline Muse

\---

## License



\---

## Acknowledgements

* This analysis uses pandas (pd), numpy (np), matplotlib.pyplot (plt), seaborn (sns), sklearn, statsmodels.formula.api (smf), and statsmodels.api (sm). One optional map figure was created using plotly.offline (po) and plotly.graph_objs (pg).
* References:
ACT. (2016). Adjusted Differences in ACT Scores by Family Income. Retrieved from https://www.act.org/content/dam/act/unsecured/documents/5688-data-byte-2016-5-adjusted-differences-in-act-scores-by-family-income.pdf
Geiser, S. (2020). Family Background Accounts for 40% of SAT/ACT Scores Among UC Applicants. In J. A. Soares (Ed.), The Scandal of Standardized Tests: Why We Need to Drop the SAT and ACT. Teachers College Press. Retrieved from https://cshe.berkeley.edu/news/family-background-accounts-40-satact-scores-among-uc-applicants
Mineo, L. (2023, November 22nd). New study finds wide gap in SAT/ACT test scores between wealthy, lower-income kids. The Harvard Gazette. Retrieved from The Harvard Gazette: https://news.harvard.edu/gazette/story/2023/11/new-study-finds-wide-gap-in-sat-act-test-scores-between-wealthy-lower-income-kids/
USDA. (2025, 8 5). Child Nutrition Programs - National School Lunch Program. Retrieved from https://www.ers.usda.gov/topics/food-nutrition-assistance/child-nutrition-programs/national-school-lunch-program




