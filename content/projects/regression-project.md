---
title: STA 101 Regression Project
---

This regression project is **due Tuesday July 19 at 11:59pm.**

View [team assignments here](https://duke.box.com/s/06n8tniiuroqg2ms0nkrbz79zsq73gpk)

The deliverable for this project (what you will turn in) is a written report. See below for more details.


## About the project

For this project you will create a linear model (of your choosing) to predict newborn birth weights (or some transformation of the variable) using a sample of 3000 observations from 2020 US birth data originally sourced from [the CDC](https://www.cdc.gov/nchs/data_access/vitalstatsonline.htm).

Download the data using the code below.

```
births = read_csv("https://sta101.github.io/static/appex/data/trainUSbirth.csv")
```

Here's a code book for the data set:


- `newborn_birth_weight`: newborn birth weight in grams (response)
- `month`: birth month (1 = January, …, 12 = December)
- `mother_age`: age of the mother in years
- `prenatal_care_starting_month`: month in which prenatal care began; if 0, there was no prenatal care
- `daily_cigarette_prepregnancy`: daily number of cigarettes smoked before the pregnancy
- `daily_cigarette_trimester_1`: daily number of cigarettes smoked during the 1st trimester of the pregnancy
- `daily_cigarette_trimester_2`: daily number of cigarettes smoked during the 2nd trimester of the pregnancy
- `daily_cigarette_trimester_3`: daily number of cigarettes smoked during the 3rd trimester of the pregnancy
- `mother_height`: height of the mother in inches
- `mother_bmi`: body mass index of the mother
- `mother_weight_prepregnancy`: weight of the mother before the pregnancy in pounds
- `mother_weight_delivery`: weight of the mother at delivery in pounds
- `mother_diabetes_gestational`: whether the mother had diabetes during the pregnancy
- `newborn_sex`: sex of the newborn
- `gestation_week`: number of gestational weeks
- `mother_risk_factors`: whether the mother had any risk factor (diabetes, hypertension, previous preterm birth, previous cesarean, infertility treatment used, etc)



If you wish, you can optionally evaluate the predictive ability of your model, using 1000 observations contained in the test data set below.

```
test_data = read_csv("https://sta101.github.io/static/appex/data/testUSbirth.csv")
```

Here is an example of exactly how to evaluate your predictive ability in a typical linear regression model:

```
# load data
births = read_csv("https://sta101.github.io/static/appex/data/trainUSbirth.csv")
test_data = read_csv("https://sta101.github.io/static/appex/data/testUSbirth.csv")

# fit a model with mother_age as a predictor of newborn_birth_weight
myPredictiveModel = linear_reg() %>%
  set_engine("lm") %>%
  fit(newborn_birth_weight ~ mother_age, data = births)

# predict based on new data
predict_test = test_data %>%
  mutate(myPrediction = predict(myPredictiveModel, test_data)$.pred) 

# compute sum squared error
predict_test %>%
  mutate(squared_error = (newborn_birth_weight - myPrediction)^2) %>%
  summarize(sse = sum(squared_error))

```

See [ae7]() for an example of how to do this in a logistic regression setting.

## Written report

Your report must be written using R Markdown. Your written report should not exceed five pages inclusive of all tables and figures. Use the code below to download a template file for the project.

```
download.file("https://sta101.github.io/static/projects/regression_project_template.Rmd",
destfile = "regressionProject.rmd")
```

To begin, add YAML to the top and specify a project name, a team name (optional) and the names of each group member. You can use the YAML posted below as a template.

```
---
title: "Regression project"
author: "The Last Rbenders: Aang, Katara, Sokka, Momo"
---
```

All team members must contribute to the report. Before you finalize your report, make sure the printing of code chunks is turned off by including the following code chunk at the top of your RMD:

    ```{r setup, include=FALSE}
        knitr::opts_chunk$set(echo = FALSE)
    ```


Next, load any relevant libraries and the data.

The written report is worth 50 points, broken down as follows:

### Introduction `7pts`

The introduction provides motivation and context for your research.

To begin, introduce the data set in a few short sentences. Next, create a code book (aka a "data dictionary") of the variables in the data set. Although a code book is provided above, you should include one in your report as well so that your report is self-contained.

Complete the introduction by providing a concise, clear statement of your research question and hypotheses. Be sure to motivate why the research question is interesting / useful.

Example research question and hypotheses:

*Can we predict body mass with bill depth? We hypothesize that penguins with deeper bills will also have more mass.*

### Methodology `15pts`

Here you should introduce your regression model. Specifically, do you use regular linear regression or logistic regression? Why? What's the **full model equation**?

Did you choose to leave out some predictors but include others? Why or why not? You can also include summary statistics or create plots to explore the data and help inform your model choices.

Do you fit multiple models? If so, why?

Do you compare them using R^2 or AIC? If so, why?


### Results `15pts`

Report and interpret your final fitted model equation(s).

Report any relevant R^2 or AIC you use to select between models.

Place figure(s) here to illustrate the main results from your analysis. 1 beautiful figure is worth more than several poorly formatted figures. You must have at least 1 figure.

Provide only the main results from your analysis. The goal is not to do an exhaustive data analysis (calculate every possible statistic and create every possible model for all variables). Rather, you should demonstrate that you are proficient at asking meaningful questions and answering them using data, that you are skilled in writing about and interpreting results, and that you can accomplish these tasks using R. More is not better.

How well does your model predict new data?

### Discussion `8pts`

This section is a conclusion and discussion. You should 

1. Summarize your main finding in a sentence or two.

2. Discuss your finding and why it is useful (put in the context of your motivation from the introduction).

3. Critique your own analyses and include a brief paragraph on what you would do differently if you were able to start the project over.

4. List a brief (1 or 2 sentence) summary of the relative contributions of each team member. E.g. "Aang built the models, Katara implemented them in R, and Sokka wrote the introduction and discussion." 

- Note: all team members should be comfortable describing all aspects of the project and understanding all code.

### Formatting `5pts`

Your project should be professionally formatted. For example, this means labeling graphs and figures, turning off code chunks, and using typical style guidelines.

## Submitting to gradescope

- Select **one** team member to upload the team’s PDF submission to Gradescope.

- Be sure to select every team member's name in  Gradescope.

- Associate all pages with "Full report".
