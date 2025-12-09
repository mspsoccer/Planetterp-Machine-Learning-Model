## CMSC Professor Rating Predictor
Predicting professor ratings using PlanetTerp reviews, grade distributions, and machine learning

This project develops a machine learning system that predicts University of Maryland CMSC professor ratings without using star ratings as an input. Instead, the model uses review sentiment, grade distributions, and engagement metrics extracted from the PlanetTerp API.

# Overview

  Automatically collects professor data from the PlanetTerp REST API
  
  Filters for instructors who have taught CMSC courses

  Builds a feature-rich dataset with review sentiment, grade patterns, and teaching volume

  Trains and evaluates three machine learning models

  Identifies which factors most strongly drive professor ratings

  Provides visualizations for exploratory analysis and model interpretation

# Data Collection

  The pipeline retrieves the following from PlanetTerp:

    Professor metadata

    All review text

    Grade distributions for each course section taught

    Average professor rating (for supervised learning only)

The dataset includes:

    Review sentiment scores computed using TextBlob

    Complete distributions of A–F letter grades

    Withdrawal counts
  
    Section counts and total students taught

    Average GPA derived from grade distributions

    Only CMSC-affiliated professors with both ratings and grade data are included.

# Feature Engineering

Each professor is represented by the following features:

Sentiment Features

    Average sentiment polarity of all student comments (review_sentiment)

Grade Features

    Average GPA based on weighted grade counts (avg_gpa)

    Fraction of letter grades:
    
      frac_A, frac_B, frac_C, frac_D, frac_F

    Course withdrawal rate (withdraw_rate)

Engagement Features

    Number of sections with grade data (num_sections_with_grades)

    Total students taught (num_students_total)

    Number of reviews submitted on PlanetTerp (num_reviews)

# Machine Learning Models

Three regression models were trained and evaluated:

    Linear Regression

    Ridge Regression

    Random Forest Regressor

The models use an 75/25 train–test split.

# Model Performance (Representative Results)

    Random Forest achieved the strongest predictive accuracy (R² ≈ 0.716)

    Linear Regression showed moderate performance (R² ≈ 0.523)

    Ridge Regression performed poorly (R² ≈ 0.10)

Random Forest was selected as the most effective model.

# Key Visualizations

Histogram of CMSC professor rating distribution

Scatter plot of GPA vs. rating

Predicted vs. actual ratings for the best model

Random Forest feature importance ranking

These plots support the analysis and interpretation of predictive behavior.

# Insights

Sentiment of student comments is the dominant predictor of ratings

Grade distributions alone do not strongly correlate with how students rate instructors

Engagement metrics (students taught, number of sections) contribute minimally

A nonlinear model (Random Forest) captures relationships that linear models do not


Author

Milan Patel
University of Maryland
Machine Learning and Data Analysis
