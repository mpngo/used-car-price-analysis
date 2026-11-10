# Used Car Price Analysis

Which vehicle characteristics are associated with used-car asking prices in India? This R Markdown analysis examines CarDekho listings and models price using model year, kilometers driven, and vehicle specifications.

## Methods

- Explore price and vehicle characteristics with summary tables and plots.
- Fit linear regressions, use stepwise selection, and check for multicollinearity with variance inflation factors.
- Compare random forest models that use engine displacement, maximum power, or maximum torque with 10-fold cross-validation.
- Check the linear model residuals and fit a final model with a base-10 log transformation of price.

The final regression used 1,750 listings after filtering. It explained about 88% of the variation in log asking prices in the fitted sample (adjusted R² = 0.877). Its predictors were model year, kilometers driven, seating capacity, fuel tank capacity, maximum power, and vehicle height. The analysis converted INR to USD using a fixed rate of 83 INR per USD.

## Run the analysis

From the repository root, run the following in R. Rendering requires Pandoc, which is included with RStudio.

```r
install.packages(c(
  "rmarkdown", "knitr", "dplyr", "ggplot2", "gridExtra", "kableExtra",
  "car", "readr", "GGally", "ggpubr", "caret", "tidyr", "MASS",
  "randomForest"
), repos = "https://cloud.r-project.org")

rmarkdown::render("used-car-price-analysis.Rmd")
```

Open `used-car-price-analysis.html` to view the report.

## Data and credits

`car details v4.csv` is the CarDekho listing data distributed in [Vehicle dataset on Kaggle](https://www.kaggle.com/datasets/nehalbirla/vehicle-dataset-from-cardekho) by Nehal Birla and collaborators. The source lists the [Open Database License](https://opendatacommons.org/licenses/odbl/1-0/) for the database and the [Database Contents License](https://opendatacommons.org/licenses/dbcl/1-0/) for its contents.

Analysis contributors include Tommy Ngo, Bimi Amao, Wanqing Zhang, and Xiyan Zeng.
