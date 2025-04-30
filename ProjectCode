library(corrplot)

# Load the dataset ------------------------------------------------------
setwd("D:/work/Semester3/ProbStats/Project/Final")

# Read the CSV file
data <- read.csv("FinalSubset.csv")
# Display the first few rows of the data
cat("First few rows of the data:\n")
print(head(data))
# Drop Phone Number Column
data <- data[, !(colnames(data) %in% c("Row_Index", "Phone.Number"))]

# 1- Summary Statistics -------------------------------------------------
cat("\nSummary Statistics:\n")
print(summary(data))

# Calculate mode for each variable
mode_calc <- function(x) {
  uniq_vals <- unique(x)
  uniq_vals[which.max(tabulate(match(x, uniq_vals)))]
}
modes <- sapply(data, mode_calc)
cat("\nModes of the variables:\n")
print(modes)

# 2- Box and Whisker Plots ----------------------------------------------
data_transformed <- data
data_transformed$Attendance <- data$Attendance - 80

boxplot(data_transformed, 
        col = rainbow(ncol(data_transformed)), 
        main = "Box and Whisker Plots for All Variables",
        xlab = "Variables", 
        ylab = "Values", 
        las = 1,
        outline = TRUE,
        ylim = c(0, 48),
        cex.axis = 0.7)

legend("topright", 
       legend = c(colnames(data)[1], "Study Hours (Week)", "Attendance", "Screen Time", "CGPA"), 
       fill = rainbow(ncol(data_transformed)),
       cex = 0.5)


# 3- Scatter Plot Matrix ------------------------------------------------
cat("\nScatter Plot Matrix:\n")
pairs(data, main = "Scatter Plot Matrix", pch = 19, col = "blue")

# 4- Correlation Matrix -------------------------------------------------
cat("\nCorrelation Matrix:\n")
cor_matrix <- cor(data)
print(cor_matrix)

# Plot the heatmap of the correlation matrix
cat("\nCorrelation Heatmap:\n")
library(corrplot)
corrplot(cor_matrix, method = "color", type = "upper", addCoef.col = "black",
         title = "Correlation Heatmap", tl.col = "black", number.cex = 0.7)

# 6- Fit the MLRM Model -------------------------------------------------
cat("\nFitting Multiple Linear Regression Model:\n")
model <- lm(CGPA ~ ., data = data) # CGPA as dependent variable
print(summary(model))

# 5- Train-Test Split for MLRM ------------------------------------------
cat("\nTrain-Test Split:\n")
set.seed(123) # For reproducibility
train_indices <- sample(seq_len(nrow(data)), size = 0.8 * nrow(data))
train_data <- data[train_indices, ]
test_data <- data[-train_indices, ]

model <- lm(CGPA ~ ., data = train_data) # CGPA as dependent variable

# 7- Model Evaluation ---------------------------------------------------
cat("\nModel Evaluation:\n")
# Predictions on test data
predictions <- predict(model, test_data)

# Calculate Mean Squared Error (MSE)
mse <- mean((predictions - test_data$CGPA)^2)
cat("Mean Squared Error (MSE):", mse, "\n")

# Calculate R-squared for test data
ss_total <- sum((test_data$CGPA - mean(test_data$CGPA))^2)
ss_residual <- sum((test_data$CGPA - predictions)^2)
r_squared_test <- 1 - (ss_residual / ss_total)
cat("R-squared (Test Data):", r_squared_test, "\n")

