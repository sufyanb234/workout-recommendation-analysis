# Workout Recommendation Analysis Using Python

## Overview

This project is a Python-based data analysis and workout recommendation system built using an exercise dataset containing **1,324 exercise records**.

The project focuses on cleaning and exploring exercise data, identifying patterns across target muscles and equipment types, and building a simple rule-based recommendation system that suggests exercises based on user preferences.

## Project Goals

The main goals of this project were to:

- Explore and understand an exercise dataset
- Clean and prepare the data for analysis
- Perform exploratory data analysis (EDA)
- Analyse exercise distribution across muscles and equipment
- Build a workout recommendation system
- Rank exercises based on user-selected preferences

## Dataset Features

The dataset includes information such as:

- Exercise name
- Body part
- Target muscle
- Equipment
- Muscle group
- Secondary muscles
- Exercise instructions
- Instruction steps

After cleaning, unnecessary and redundant columns were removed.

## Data Cleaning

The main preprocessing steps included:

- Removing completely empty `image` and `gif_url` columns
- Removing the redundant `category` column
- Extracting English exercise instructions from multilingual fields
- Standardising equipment names such as `band` and `resistance band`
- Investigating repeated exercise names
- Keeping useful duplicate records when they contained different information

## Exploratory Data Analysis

The EDA section examines:

- Number of exercises by target muscle
- Exercise distribution by equipment type
- Exercise distribution by body part
- Most common secondary muscles

Some observations from the dataset include:

- Abs, pectorals, biceps, glutes, delts, and triceps have high exercise coverage
- Bodyweight and dumbbell exercises are the most common
- Shoulders, hamstrings, forearms, and triceps frequently appear as secondary muscles
- Some smaller muscle groups have significantly fewer available exercises

## Workout Recommendation System

The recommendation system uses the following user preferences:

- Target muscle
- Available equipment
- Body part
- Preferred secondary muscle

Exercises are ranked using a simple scoring system:

| Feature | Score |
|---|---:|
| Target muscle match | 3 |
| Equipment match | 2 |
| Body part match | 1 |
| Secondary muscle match | 1 |

The maximum recommendation score is **7**.

The selected target muscle is required to match before an exercise can be recommended.

## Example

A user can enter:

```text
Target Muscle: Chest
Equipment: Dumbbell
Body Part: Chest
Secondary Muscle: Triceps
```

The system converts common terms such as:

```text
Chest → Pectorals
Shoulders → Delts
Core → Abs
Dumbbells → Dumbbell
Bands → Resistance Band
Bodyweight → Body Weight
```

It then ranks the matching exercises and returns the highest-scoring recommendations.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Jupyter Notebook

## Project Structure

```text
workout-recommendation-analysis/
│
├── data/
│   └── Excersise Dataset.json
│
├── workout_recommendation_analysis.ipynb
├── project_notes.txt
└── README.md
```

## System Evaluation

The recommender was tested using different workout profiles, including:

- Chest exercises with dumbbells
- Biceps exercises with cables
- Glute exercises using bodyweight
- Shoulder exercises using resistance bands
- Calf exercises using a Smith machine

Several test cases returned exercises with the maximum recommendation score of **7**, meaning all selected preferences were matched.

## Limitations

The current system has several limitations:

- The dataset does not include exercise difficulty levels
- User experience level is not included
- Recommendation weights are manually defined
- Some muscle groups have limited exercise coverage
- The system is rule-based rather than trained using user behaviour

## Future Improvements

Possible future improvements include:

- Beginner, intermediate, and advanced exercise levels
- Fitness goals such as strength, hypertrophy, or fat loss
- More advanced recommendation algorithms
- User feedback and preference history
- Streamlit web interface
- Machine learning or content-based recommendation methods

## AI Assistance

AI was used mainly to assist with the development of the recommendation-system code, debugging, input validation, and improvement of the scoring logic.

The dataset exploration, cleaning decisions, exploratory data analysis, visualisations, interpretation of results, and other data-analysis-related work were completed as part of my own analysis and learning process.

## Author

**Muhammad Sufyan Baig**

Computer Science (Data Analytics) Student  
Asia Pacific University of Technology & Innovation
