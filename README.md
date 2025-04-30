# Predicting Student CGPA using Multiple Linear Regression in R

## Project Overview

This research project explores factors influencing the Cumulative Grade Point Average (CGPA) of university students using Multiple Linear Regression Modeling (MLRM). The study utilized primary data collected from 47 students at FAST NUCES Islamabad through surveys and online forms. Key predictors examined include Semester level, Weekly Study Hours, Attendance Percentage, and Daily Screen Time (non-academic).

This project was developed for the Probability and Statistics (MT-2005) course requirement.

## Key Findings & Model

* **Model:** $CGPA = \beta_{0} + \beta_{1}(Semester) + \beta_{2}(Study Hours) + \beta_{3}(Attendance) + \beta_{4}(Screen Time) + \epsilon$.
* **Significant Predictors (p < 0.05):**
    * **Attendance (%):** Strongest positive predictor ($\beta_3 \approx 0.027$). Higher attendance correlates strongly with higher CGPA.
    * **Screen Time (hours/day):** Significant negative predictor ($\beta_4 \approx -0.032$). More non-academic screen time correlates with lower CGPA.
    * **Study Hours (hours/week):** Significant negative predictor ($\beta_2 \approx -0.014$). This counter-intuitive result suggests potential study inefficiency or stress associated with very high study hours in the sampled group.
* **Marginally Significant Predictor:**
    * **Semester:** Negative association ($\beta_1 \approx -0.058$, $p \approx 0.081$). Suggests CGPA may slightly decrease in later semesters, possibly due to increased difficulty, though not strongly statistically significant in this model.
* **Model Performance:** The MLRM model explains approximately 47.4% of the variance in CGPA ($R^2 \approx 0.4741$). The Mean Squared Error (MSE) was approximately 0.0585.

## Tech Stack

* **Language:** R
* **Core R Packages:** (Verify from `analysis.R`)
    * Base R (`read.csv`, `lm`, `summary`)
    * Potentially `readr`, `dplyr`, `ggplot2` for data handling/visualization.

## Dataset Privacy Note

* The dataset (`Dataset.csv`) used for this analysis was collected directly from students and contains sensitive information.
* **This dataset is NOT publicly available in this repository due to student privacy concerns.**
* The `analysis.R` script is provided for reviewing the methodology and statistical analysis performed.

## Setup

1.  **Prerequisites:** Install R and RStudio.
2.  **Clone:** `git clone https://github.com/ApatheticMioz/student-cgpa-prediction-r.git`
3.  **Install Packages:** Open R/RStudio and install any necessary packages used in `analysis.R`, e.g., `install.packages("dplyr")`.

## Usage

1.  Open `analysis.R` in RStudio.
2.  **(Requires Dataset Access)** If you have authorized access to an anonymized version of `Dataset.csv`, place it in the correct path relative to the script.
3.  Run the script (`source("analysis.R")` or run lines).
4.  Examine console output for model summaries, coefficients, p-values, R-squared, and MSE.

## Project Structure
├── analysis.R          # R script for data analysis and MLRM modeling

└── (Dataset.csv) # Dataset file (NOT INCLUDED - PRIVACY)

---
