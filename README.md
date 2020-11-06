# Phase 4 Final Project


## Introduction

In this lesson, we'll review all of the guidelines and specifications for the final project for Phase 4.

## Objectives

* Understand all required aspects of the Final Project for Phase 4
* Understand all required deliverables
* Understand what constitutes a successful project

## Final Project Summary

Final phase down -- you're absolutely crushing it! You've made it all the way through one of the toughest phases of this course. You must have an amazing brain in your head!

<img src='https://raw.githubusercontent.com/learn-co-students/dsc-mod-4-project-seattle-ds-102819/master/images/brain.gif'>

## The Datasets

For this phase's final project, you have the choice of four problems:

- Time Series Modeling
- Recommendation System
- Image Classification with Deep Learning
- Natural Language Processing

For each problem, we have provided a dataset. 

Like Project \#3, the focus here is on *prediction*. It will be up to you to determine how best to evaluate your model, but for any of these projects your goal is to build something that **works**.

When choosing a problem, consider:

1. **Portfolio Depth:** One option is to choose the same type of problem you plan to tackle in Phase 5 (capstone).  This will allow you to practice the necessary skills in a group setting, before diving into your individual project.  You will likely produce a capstone project that is more polished and sophisticated, but your portfolio will demonstrate less breadth.
2. **Portfolio Breadth:** Another option is to choose a type of problem that interests you, but that you don't plan to use in your capstone project.  Each of your individual projects will end up less polished and sophisticated, but you will end up with a portfolio that demonstrates a wider range of skills.

### Problem 1: Time Series Modeling

If you choose the Time Series option, you will be forecasting real estate prices of various zip codes using data from [Zillow](https://www.zillow.com/research/data/). However, this won't be as straightforward as just running a time-series analysis -- you're going to have to make some data-driven decisions and think critically along the way!

For this project, you will be acting as a consultant for a fictional real-estate investment firm. The firm has asked you what seems like a simple question:

> What are the top 5 best zip codes for us to invest in?

This may seem like a simple question at first glance, but there's more than a little ambiguity here that you'll have to think through in order to provide a solid recommendation. Should your recommendation be focused on profit margins only? What about risk? What sort of time horizon are you predicting against?  Your recommendation will need to detail your rationale and answer any sort of lingering questions like these in order to demonstrate how you define "best".

As mentioned previously, the data you'll be working with comes from the [Zillow Research Page](https://www.zillow.com/research/data/). However, there are many options on that page, and making sure you have exactly what you need can be a bit confusing. For simplicity's sake, we have already provided the dataset for you in this repo -- you will find it in the file `time-series/zillow_data.csv`.

The goal of this project is to have you complete a very common real-world task in regard to time series modeling. However, real world problems often come with a significant degree of ambiguity, which requires you to use your knowledge of statistics and data science to think critically about and answer. While the main task in this project is time series modeling, that isn't the overall goal -- it is important to understand that time series modeling is a tool in your toolbox, and the forecasts it provides you are what you'll use to answer important questions.

In short, to pass this project, demonstrating the quality and thoughtfulness of your overall recommendation is at least as important as successfully building a time series model!

#### Starter Jupyter Notebook

For this project, you will be provided with a Jupyter notebook, `time-series/starter_notebook.ipynb`, containing some starter code. If you inspect the Zillow dataset file, you'll notice that the datetimes for each sale are the actual column names -- this is a format you probably haven't seen before. To ensure that you're not blocked by preprocessing, we've provided some helper functions to help simplify getting the data into the correct format. You're not required to use this notebook or keep it in its current format, but we strongly recommend you consider making use of the helper functions so you can spend your time working on the parts of the project that matter.

#### Evaluation

In addition to deciding which quantitative metric(s) you want to target (e.g. minimizing mean squared error), you need to start with a definition of "best investment".  Consider additional metrics like risk vs. profitability, or ROI yield.

### Problem 2: Recommendation System

If you choose the Recommendation System option, you will be making movie recommendations based on the [MovieLens](https://grouplens.org/datasets/movielens/latest/) dataset from the GroupLens research lab at the University of Minnesota.  Unless you are planning to run your analysis on a paid cloud platform, we recommend that you use the "small" dataset containing 100,000 user ratings (and potentially, only a particular subset of that dataset).

Your task is to:

> Build a model that provides top 5 movie recommendations to a user, based on their ratings of other movies.

The MovieLens dataset is a "classic" recommendation system dataset, that is used in numerous academic papers and machine learning proofs-of-concept.  You will need to create the specific details about how the user will provide their ratings of other movies, in addition to formulating a more specific business problem within the general context of "recommending movies".

#### Collaborative Filtering

At minimum, your recommendation system must use collaborative filtering.  If you have time, consider implementing a hybrid approach, e.g. using collaborative filtering as the primary mechanism, but using content-based filtering to address the [cold start problem](https://en.wikipedia.org/wiki/Cold_start_(recommender_systems)).

#### Evaluation

The MovieLens dataset has explicit ratings, so achieving some sort of evaluation of your model is simple enough.  But you should give some thought to the question of metrics.  Since the rankings are ordinal, we know we can treat this like a regression problem.  But when it comes to regression metrics there are several choices: RMSE, MAE, etc. [Here](https://towardsdatascience.com/evaluation-metrics-for-recommender-systems-df56c6611093) are some further ideas.

### Problem 3: Image Classification with Deep Learning

If you choose this option, you'll put everything you've learned together to build a deep neural network that trains on a large dataset for classification on a non-trivial task.  In this case, using x-ray images of pediatric patients to identify whether or not they have pneumonia.  The dataset comes from Kermany et al. on [Mendeley](https://data.mendeley.com/datasets/rscbjbr9sj/3), although there is also a version on [Kaggle](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia) that may be easier to use.

Your task is to:

> Build a model that can classify whether a given patient has pneumonia, given a chest x-ray image.

#### Aim for a Proof of Concept

With Deep Learning, data is king -- the more of it, the better. However, the goal of this project isn't to build the best model possible -- it's to demonstrate your understanding by building a model that works. You should try to avoid datasets and model architectures that won't run in reasonable time on your own machine. For many problems, this means downsampling your dataset and only training on a portion of it. Once you're absolutely sure that you've found the best possible architecture and other hyperparameters for your model, then consider training your model on your entire dataset overnight (or, as large a portion of the dataset that will still run in a feasible amount of time).

At the end of the day, we want to see your thought process as you iterate and improve on a model. A project that achieves a lower level of accuracy but has clearly iterated on the model and the problem until it found the best possible approach is more impressive than a model with high accuracy that did no iteration. We're not just interested in seeing you finish a model -- we want to see that you understand it, and can use this knowledge to try and make it even better!

#### Evaluation

Evaluation is fairly straightforward for this project.  But you'll still need to think about which metric to use and about how best to cross-validate your results.

### Problem 4: Natural Language Processing (NLP)

If you choose this option, you'll build an NLP model to analyze Twitter sentiment about Apple and Google products. The dataset comes from CrowdFlower via [data.world][]. Human raters rated the sentiment in over 9,000 Tweets as positive, negative, or neither.

Your task is to:

> Build a model that can rate the sentiment of a Tweet based on its content.

#### Aim for a Proof of Concept

There are many approaches to NLP problems - start with something simple and iterate from there. For example, you could start by limiting your analysis to positive and negative Tweets only, allowing you to build a binary classifier. Then you could add in the neutral Tweets to build out a multiclass classifier. You may also consider using some of the more advanced NLP methods in the Phase 4 Appendices.

#### Evaluation

Evaluating multiclass classifiers can be trickier than binary classifiers because there are multiple ways to mis-classify an observation, and some errors are more problematic than others. Use the business problem that your NLP project sets out to solve to inform your choice of evaluation metrics.

## DELIVERABLES

1. A public GitHub repository.

2. An `environment.yml` file that contains all the necessary packages needed to recreate your conda environment.
3. A standalone `src/` directory that stores all relevant source code.
    - All functions have docstrings that act as [professional-quality documentation](http://google.github.io/styleguide/pyguide.html#381-docstrings). 
    - If applicable, [well documented](https://www.sqlstyle.guide/) SQL queries with appropriate single-line or multiline comments.
    - Quality classification model
       - Whenever necessary, briefly explain in comments the changes made from one iteration to the next, and why you made these choices


4. A standalone `data/` directory that stores all relevant raw and processed data files.
    - **Be sure to include how the data was obtained!**
    - All large files are labeled in the `.gitignore` file to avoid having them accidentally live in your commit history.
    

5. A standalone `references/` directory that stores all relevant literature, data dictionaries, or useful references that were used to help you during the project.
    - Use this directory to store physical copies of the `.pdf` files; or
    - Create a `README.md` file that cites external resources that were used.
    
    
6. A standalone `reports/` directory that stores your `presentation.pdf` files


7. A standalone `notebooks/` directory that stores both your exploratory and report notebooks
    - A record of your workflow should be stored in `notebooks/exploratory`. Don't be afraid to leave in error messages, so you know what didn't work!


8. A user-focused `README.md` file that briefly covers your process, methodology and findings.
    - Someone with no context on your project should be able to use this document to understand the structure of your project, and adapt your code for their needs.
    - Implied above is a schema which diagramming the route to important files.


9. One final Jupyter Notebook file stored in `notebooks/report` that focuses on visualization and presentation
    - The very beginning of the notebook contains a description of the purpose of the notebook.
       - This is helpful for your future self and anyone of your colleagues that needs to view your notebook. Without this context, you’re implicitly asking your peers to invest a lot of energy to help solve your problem. Help them to jump into your project by providing them the purpose of this Jupyter Notebook.
    - Explanation of the data sources and where one can retrieve them
       - Whenever possible, link to the corresponding data dictionary
    - Custom functions and classes are imported from Python modules and are not created directly in the notebook. As soon as you have a working function in one of your exploratory notebooks, copy it over to `src` so it is reusable.
    - At least 4 meaningful data visualizations, with corresponding interpretations. All visualizations are well labeled with axes labels, a title, and a legend (when appropriate)
    - Take the time to make sure that you craft your story well, and clearly explain your process and findings in a way that clearly shows both your technical expertise and your ability to communicate your results!


10. An "Executive Summary" Keynote/PowerPoint/Google Slide presentation (delivered as a PDF export) that explains what you have found.
    - Make sure to also add and commit this file as presentation.pdf of your non-technical presentation to your repository with a file name of `reports/presentation.pdf`.
    - Contain between 5-10 professional quality slides detailing:
       - A high-level overview of your methodology
       - The results you’ve uncovered
       - Any real-world recommendations you would like to make based on your findings (ask yourself--why should the executive team care about what you found? How can your findings help the company/stakeholder?)
       - Avoid technical jargon and explain results in a clear, actionable way for non-technical audiences.
    - The slides should use visualizations whenever possible, and avoid walls of text
    - All visualizations included in this presentation should also be exported as image files (e.g. with `plt.savefig`, not by taking a screenshot) and saved under `reports/figures/`
   - All visualizations included in this presentation should also be exported as image files (e.g. with `plt.savefig`, not by taking a screenshot) and saved under `reports/figures/`
### 1. Business Understanding

Start by reading this document, and making sure that you understand the kinds of questions being asked.  In order to narrow your focus, you will likely want to make some design choices about your specific audience, rather than attempting to address all potentially-relevant concerns. Think about what kinds of predictions you want to be able to make, and about which kinds of wrong predictions are most concerning.

Three things to be sure you establish during this phase are:

1. **Objectives:** what questions are you trying to answer, and for whom?
2. **Project plan:** you may want to establish more formal project management practices, such as daily stand-ups or using a Trello board, to plan the time you have remaining.  Regardless you should determine the division of labor, communication expectations, and timeline.
3. **Success criteria:** what does a successful project look like?  How will you know when you have achieved it?  At this point you should be able to establish at least one quantitative success metric, before you even decide on which model(s) you are going to try.

### 2. Data Understanding

Write a script to download the data (or instructions for future users on how to manually download it), and explore it.  Do you understand what the columns mean?  If the dataset has more than one table, how do they relate to each other?  How will you select the subset of relevant data?  What kind of data cleaning is required?

It may be useful to generate visualizations of the data during this phase.

### 3. Data Preparation

Through SQL and Pandas, perform any necessary data cleaning and develop a query that pulls in all relevant data for modeling, including any merging of tables.  Be sure to document any data that you choose to drop or otherwise exclude.  This is also the phase to consider any feature scaling or one-hot encoding required to feed the data into your particular model.

### 4. Modeling

Similar to the Mod 3 project, the focus is on prediction. Good prediction is a matter of the model generalizing well. Steps we can take to assure good generalization include: testing the model on unseen data, cross-validation, and regularization. What sort of model should you build?

Here you will also likely encounter problems with computational capacity.  Figure out how to use smaller samples of your data in order to tweak hyperparameters.  Investigate cloud tools with hardware acceleration (e.g. Google Colab is a free one) in order to run your analysis with larger sets of data and more versions of the model.

### 5. Evaluation

Recall that there are many different metrics we might use for evaluating a classification model. Accuracy is intuitive, but can be misleading, especially if you have class imbalances in your target. Perhaps, depending on you're defining things, it is more important to minimize false positives, or false negatives. It might therefore be more appropriate to focus on precision or recall. You might also calculate the AUC-ROC to measure your model's *discrimination*.

### 6. Deployment

In this case, your "deployment" comes in the form of the deliverables listed above. Make sure you can answer the following questions about your process:

 - "How did you pick the question(s) that you did?"
 - "Why are these questions important from a business perspective?"
 - "How did you decide on the data cleaning options you performed?"
 - "Why did you choose a given method or library?"
 - "Why did you select these visualizations and what did you learn from each of them?"
 - "Why did you pick those features as predictors?"
 - "How would you interpret the results?"
 - "How confident are you in the predictive quality of the results?"
 - "What are some of the things that could cause the results to be wrong?"



## Citation

1. "What is the CRISP-DM Methodology?" Smart Vision Europe. Available at: https://www.sv-europe.com/crisp-dm-methodology/

[data.world]: https://data.world/crowdflower/brands-and-product-emotions
