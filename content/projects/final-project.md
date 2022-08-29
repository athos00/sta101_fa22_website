---
title: "STA 101 Final Project"
---

This final project has three deliverable items:

- a pre-project proposal **due Friday July 29 at 11:59pm**,
- a final presentation **due Thursday August 4 at 11:59pm**,
- final report **due Friday August 5 at 11:59pm**.

In addition to the above, a component of the grade will be peer-reviewing project report drafts during lab in the final week of class and commenting on the presentaitons on August 5th.

View [team assignments here](https://duke.box.com/s/06n8tniiuroqg2ms0nkrbz79zsq73gpk)


## About the project

Find a data set, develop a question you can answer with the data, and do it.

## Proposal `5pts`

1. Find 2 or 3 data sets of interest. Each data must have a mix of categorical and numeric variables and contain at least 500 observations and 10 variables or **have prior approval by Prof. Fisher**.

2. Identify the source of the data, when and how it was originally collected (by the curator, not necessarily how you found the data) and a brief description of the observations.

3. Identify a research question you can answer with each data set (and which variables will help you answer the question!)

4. At the end of your document, provide a `glimpse()` of each data set.

Your proposal should be no longer than 1 page (not including the glimpses). After you submit your proposal, I will offer feedback and help you decide which data set to choose for the final project. For this reason, please rank your proposal data sets with your favorite first.

## Where to find data?

Some example resources you might use to find a data set are below. You may not use a data set used in this class or another class. 

- [R Data Sources for Regression Analysis](https://rfun.library.duke.edu/blog/data-sources-for-regression-analysis/)
- [FiveThirtyEight data](https://data.fivethirtyeight.com/)
- [TidyTuesday](https://github.com/rfordatascience/tidytuesday)
- [World Health Organization](https://www.who.int/gho/database/en/)
- [The National Bureau of Economic Research](https://data.nber.org/data/)
- [International Monetary Fund](https://data.imf.org/?sk=388DFA60-1D26-4ADE-B505-A05A558D9A42&sId=1479329328660)
- [General Social Survey](http://gss.norc.org/)
- [United Nations Data](http://data.un.org/)
- [United Nations Statistics Division](https://unstats.un.org/home/)
- [U.K. Data](https://data.gov.uk/)
- [U.S. Data](https://www.data.gov/)
- [U.S. Census Data](https://www.census.gov/data.html)
- [European Statistics](https://ec.europa.eu/eurostat/)
- [Statistics Canada](https://www.statcan.gc.ca/eng/start)
- [Pew Research](https://www.pewresearch.org/download-datasets/)
- [UNICEF](https://data.unicef.org/)
- [CDC](https://www.cdc.gov/datastatistics/index.html)
- [World Bank](https://datacatalog.worldbank.org/)
- [Election Studies](https://electionstudies.org//)

## Written report `50pts`

Your report must be written using R Markdown. Your written report should not exceed ten pages inclusive of all tables and figures. Use the code below to download a template file for the project.

```
download.file("https://sta101.github.io/static/projects/final_project_template.Rmd",
destfile = "finalProject.rmd")
```

To begin, add YAML to the top and specify a project name, a team name (optional) and the names of each group member. You can use the YAML posted below as a template.

```
---
title: "Final project"
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

To begin, introduce the data set in a few short sentences. Next, create a code book (aka a "data dictionary") of the variables in the data set.

Complete the introduction by providing a concise, clear statement of your research question and hypotheses. Be sure to motivate why the research question is interesting / useful.

Example research question and hypotheses:

*Can we predict body mass with bill depth? We hypothesize that penguins with deeper bills will also have more mass.*

### Methodology `15pts`

Here you should introduce any statistical methods you use and describe why you choose the methods you do to answer your question. You might also include any preliminary summary statistics or figures you use to explore the data.

### Results `15pts`

Place figure(s) here to illustrate the main results from your analysis. 1 beautiful figure is worth more than several poorly formatted figures. You must have at least 1 figure.

Provide only the main results from your analysis. The goal is not to do an exhaustive data analysis (calculate every possible statistic and create every possible model for all variables). Rather, you should demonstrate that you are proficient at asking meaningful questions and answering them using data, that you are skilled in writing about and interpreting results, and that you can accomplish these tasks using R. More is not better.

### Discussion `8pts`

This section is a conclusion and discussion. You should 

1. Summarize your main finding in a sentence or two.

2. Discuss your finding and why it is useful (put in the context of your motivation from the introduction).

3. Critique your own analyses and include a brief paragraph on what you would do differently if you were able to start the project over.

4. List a brief (1 or 2 sentence) summary of the relative contributions of each team member. E.g. "Aang built the models, Katara implemented them in R, and Sokka wrote the introduction and discussion." 

- Note: all team members should be comfortable describing all aspects of the project and understanding all code.

### Formatting `5pts`

Your written report should be professionally formatted. This means complete sentences, labeling graphs and figures, turning off code chunks, and using typical style guidelines. The only sections your reportm ay contain are **Introduction**, **Methodology**, **Results** and **Discussion**. You should include a citation of your data set and the citation should be formatted in any style of your choosing (e.g. MLA, APA etc.) It is important that your citations (should you include multiple) be consistent in their formatting.

### Peer review `2.5pts`

During lab in the final week, you will peer-review draft reports. Details will be announced in lab.


## Presentation `40pts`

For your presentation, you and your team must also create presentation slides that summarize and showcase your project. Introduce your research question and data set, showcase visualizations, and provide some conclusions. These slides should serve as a brief visual accompaniment to your write-up and will be graded for content and quality.

The slide deck should have no more than 6 content slides + 1 title slide. Here is a suggested outline as you think through the slides; you do not have to use this exact format for the slide deck.

- Title Slide

- Slide 1: Introduce the topic and motivation

- Slide 2: Introduce the data

- Slide 3 - 4: Highlights from exploratory data analysis

- Slide 4 - 5: Inference / modeling

- Slide 6: Conclusions + future work

- Video presentation

- Sometime by August 4th, you/your group will upload a link to your video presentation in sakai discussions. Note that all members must present, and that a ten-minute time limit is strictly enforced.

For the presentation, you can speak over your slide deck, similar to the lecture content videos. I recommend using Zoom to record your presentation; however, you can use whatever platform works best for your group. Below are a few resources to help you record video presentations:

- [Recording presentations in Zoom](https://kb.siue.edu/61721)

- [Apple Quicktime for screen recording](https://support.apple.com/en-gb/guide/quicktime-player/qtp97b08e666/mac)

- [Windows 10 built-in screen recording functionality](https://www.youtube.com/watch?v=OfPbr1mRDuo)

- [Kap for screen recording](https://getkap.co/)

You can post the link directly into sakai discussion or alternatively post the presentation video in Warpwire, which is accessible from the the course Sakai site (bottom of the left-hand tool bar).

**To upload your video to Warpwire:**

- Click the Warpwire tab in the course Sakai site.

- Click the “+” and select “Upload files”.

- Locate the video on your computer and click to upload.

- Once you’ve uploaded the video to Warpwire, click to share the video and make a copy of the video’s URL. You will need this when you post the video in the discussion forum.

**To post the video to the discussion forum:**

- Click the Presentations tab in the course Sakai site.

- Click the Presentations topic.

- Click “Start New Presentation”.

- Make the title “Your Team Name: Project Title”. For example, “Teaching Team: Analysis of Cars in the US”.

- Click the Warpwire icon (between the flag and shopping cart icons).

- Select your video, then click “Insert 1 item.” This will embed your video in the conversation.

- Under the video, paste the URL to your video.

- You’re done!

### Presentation comments `2.5pts`

Each student will be assigned 2 presentations to watch.

Watch the group’s video, then click “Reply” to post a question for the group. You may not post a question that’s already been asked on the discussion thread. Additionally, the question should be (i) substantive (i.e. it shouldn’t be “Why did you use a bar plot instead of a pie chart”?), (ii) demonstrate your understanding of the content from the course, and (iii) relevant to that group’s specific presentation, i.e demonstrating that you’ve watched the presentation.

Questions must be posted by Friday August 5.

This portion of the project will be assessed individually

## Tip

- Ask questions if any of the project expectations are 
unclear.

## Submitting to gradescope

- Select **one** team member to upload the team’s PDF submission to Gradescope.

- Be sure to select every team member's name in  Gradescope.

- Associate all pages with "Full report".
