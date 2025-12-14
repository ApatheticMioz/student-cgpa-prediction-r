# Student CGPA Prediction R

A Multiple Linear Regression analysis in R to predict student CGPA based on academic and behavioral factors.

## Description

This project explores factors influencing the Cumulative Grade Point Average (CGPA) of university students using Multiple Linear Regression Modeling (MLRM). The analysis examines key predictors including:

- **Semester Level** - Current academic semester
- **Weekly Study Hours** - Time spent studying per week
- **Attendance Percentage** - Class attendance rate
- **Daily Screen Time** - Non-academic screen time

### Key Findings

| Predictor | Effect | Significance |
|-----------|--------|--------------|
| Attendance (%) | Positive (+0.027) | p < 0.05 |
| Screen Time (hrs/day) | Negative (-0.032) | p < 0.05 |
| Study Hours (hrs/week) | Negative (-0.014) | p < 0.05 |
| Semester | Negative (-0.058) | p ≈ 0.081 |

**Model Performance:** R² ≈ 0.474, MSE ≈ 0.059

## Project Structure

```
.
├── analysis.R          # Main R script for MLRM analysis
├── LICENSE             # MIT License
├── CONTRIBUTING.md     # Contribution guidelines
├── CHANGELOG.md        # Version history
├── .editorconfig       # Editor configuration
├── .gitignore          # Git ignore rules
└── README.md           # This file
```

## Installation

### Prerequisites

- [R](https://cran.r-project.org/) (version 4.0 or higher recommended)
- [RStudio](https://posit.co/downloads/) (optional but recommended)

### Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/ApatheticMioz/student-cgpa-prediction-r.git
   cd student-cgpa-prediction-r
   ```

2. Install required R packages:
   ```r
   install.packages("corrplot")
   ```

## Usage

1. Open `analysis.R` in RStudio or your preferred R IDE

2. **Dataset Note:** The original dataset is not included due to privacy concerns. To run the analysis, provide a CSV file with the following columns:
   - `Semester` - Numeric (1-8)
   - `Study.Hours.Week` - Numeric (hours per week)
   - `Attendance` - Numeric (percentage 0-100)
   - `Screen.Time` - Numeric (hours per day)
   - `CGPA` - Numeric (0-4.0)

3. Update the file path in `analysis.R`:
   ```r
   setwd("your/data/path")
   data <- read.csv("your_dataset.csv")
   ```

4. Run the script:
   ```r
   source("analysis.R")
   ```

5. View outputs:
   - Summary statistics
   - Box and whisker plots
   - Scatter plot matrix
   - Correlation heatmap
   - MLRM model summary
   - Model evaluation metrics (MSE, R²)

## Dependencies

| Package | Purpose |
|---------|---------|
| `corrplot` | Correlation matrix visualization |

## Status

**Archived / Refactored**

This project has been standardized for public archival.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
