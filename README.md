# 📊 Beginner’s Guide to R for Public Health 🚑🧪

Welcome to your **first steps in R programming** made for **public health heroes, biology brains**, and curious minds 💡. This guide is so simple, even a 6-year-old could start learning!

> 🎯 Goal: Help you explore, clean, and visualize real public health data using R — no experience needed!

---

## 🚀 Getting Started

### 🖥️ 1. Install R & RStudio

- 💾 [Download R](https://cran.r-project.org/)
- 💻 [Download RStudio (interface)](https://posit.co/download/rstudio-desktop)

Once installed, open RStudio. You'll see:
- 📜 Console (where code runs)
- 📝 Script Editor (where you write code)
- 📊 Environment (variables, data)
- 🖼️ Plots/Viewer (for graphs and charts)

---

## 👋 Say Hello to R

```r
print("Hello, Public Health World! 🌍🦠")


⸻

➕ Basic Math in R

2 + 2         # ➕ Addition
10 - 4        # ➖ Subtraction
5 * 3         # ✖️ Multiplication
8 / 2         # ➗ Division


⸻

📦 Variables

cases <- 20
population <- 1000

You just created a “box” named cases and put the number 20 inside it.

⸻

🧺 Vectors — Lists of Data

daily_cases <- c(5, 7, 8, 6, 9)  # Cases over 5 days

Do calculations:

sum(daily_cases)     # ➕ Total
mean(daily_cases)    # 📉 Average


⸻

📊 Data Frame — Like a Table

data <- data.frame(
  day = 1:5,
  cases = c(5, 7, 8, 6, 9),
  deaths = c(0, 1, 0, 0, 2)
)
print(data)


⸻

🔎 Explore the Data

head(data)       # 👀 First 6 rows
summary(data)    # 📊 Stats like mean, max
str(data)        # 🧱 Structure

Access a column:

data$cases


⸻

📈 Make Graphs 🖼️

📊 Bar Plot

barplot(data$cases,
        names.arg = data$day,
        col = "skyblue",
        main = "📊 Cases by Day",
        xlab = "Day",
        ylab = "Cases")

📈 Line Plot

plot(data$day, data$cases,
     type = "o",
     col = "darkgreen",
     main = "📈 Daily Case Trend",
     xlab = "Day",
     ylab = "Number of Cases")


⸻

📁 Import Real Data (CSV)

mydata <- read.csv("data/malaria_cases.csv")  # Example file
head(mydata)

📂 Place your .csv file in a folder named data/

⸻

📤 Save Your Output

write.csv(data, "data/output_cases.csv", row.names = FALSE)


⸻

🧪 Run a Simple Test

Check if average daily cases > 5:

t.test(data$cases, mu = 5, alternative = "greater")


⸻

🛠️ Useful Commands Cheatsheet

🧠 Function	🧰 Use	📝 Example
print()	Show text/output	print("Hello!")
<-	Assign values	x <- 10
c()	Combine values (vector)	c(1, 2, 3)
data.frame()	Create a table	data.frame(day=1:3)
sum()	Total	sum(c(5,6,7))
mean()	Average	mean(c(5,6,7))
barplot()	Bar chart	barplot(c(5,6,7))
plot()	Line chart	plot(1:3, c(5,6,7), type="o")
read.csv()	Load CSV data	read.csv("file.csv")
write.csv()	Export data to CSV	write.csv(data, "out.csv")
t.test()	Statistical t-test	t.test(data$cases, mu=5)


⸻

🧪 Practice Time! 💪

Try this beginner challenge:
	1.	Create a vector of new case numbers:

new_cases <- c(3, 5, 7, 2, 4)

	2.	Calculate total & mean:

sum(new_cases)
mean(new_cases)

	3.	Visualize with a barplot:

barplot(new_cases,
        main = "🦟 Malaria Cases This Week",
        xlab = "Day",
        ylab = "Cases",
        col = "orange")


⸻

📂 Sample Datasets (Optional)

Add a folder in your repo:

📁 data/
├── malaria_cases.csv
├── covid_data.csv
└── hospital_visits.csv

Need real datasets? Try:
	•	WHO Datasets
	•	Our World in Data
	•	Kaggle Health Data

⸻

📚 Learn More
	•	📘 R for Data Science (Free Book)
	•	📎 RStudio Cheatsheets
	•	🌐 Tidyverse.org
	•	📊 WHO Public Health Data

⸻

🧠 Made for Pre-Master Students

This project is ideal if you’re:
	•	✅ New to R
	•	✅ Studying Biology, Public Health, Epidemiology
	•	✅ Wanting a safe space to play with data 🧸

⸻


# chapter 2: 🧪 R for Public Health & Biology: Beginner's to Advanced

*A step-by-step introduction to R programming for public health professionals and biologists with no coding experience.*

---

## 🛠️ **Installation**
1. Download **[R](https://cran.r-project.org/)**
2. Download **[RStudio](https://posit.co/download/rstudio-desktop/)**
3. Install both (R first, then RStudio)

---

## 📚 **Basic R Syntax**
### Working with Variables
```r
# Basic math
2 + 2
5 * 10

# Storing values
weight_kg <- 70
weight_lb <- weight_kg * 2.2
print(weight_lb)

Output: [1] 154

Working with Vectors

# Create a vector of patient ages
ages <- c(25, 30, 35, 40, 45)

# Calculate mean age
mean_age <- mean(ages)
print(mean_age)

Output: [1] 35

⸻

📊 Importing and Exploring Data

Loading a CSV File

# Read data
covid_data <- read.csv("covid_data.csv")

# View first 6 rows
head(covid_data)

Basic Data Exploration

# Summary statistics
summary(covid_data$Cases)

# Count unique countries
unique(covid_data$Country)

# Filter for specific country
usa_data <- covid_data[covid_data$Country == "USA", ]


⸻

🔍 Basic Data Analysis

T-Test (Comparing Two Groups)

# Generate sample data
treatment <- c(120, 125, 130, 135, 140)
control <- c(130, 135, 140, 145, 150)

# Run t-test
t.test(treatment, control)

Key Output:
	•	p-value < 0.05 → statistically significant difference

⸻

📈 Data Visualization

Bar Plot (Cases by Country)

barplot(cases_by_country$Cases,
        names.arg = cases_by_country$Country,
        xlab = "Country",
        ylab = "Total Cases",
        main = "COVID-19 Cases by Country",
        col = "steelblue")

Scatter Plot (Cases vs Deaths)

plot(covid_data$Cases, covid_data$Deaths,
     xlab = "Cases",
     ylab = "Deaths",
     main = "Cases vs Deaths",
     pch = 19,
     col = "red")


⸻

⸻

📚 Resources
	•	R for Data Science
	•	Public Health R Examples
	•	R Cheat Sheets

⸻

chapter Two

Here’s the GitHub-ready Markdown version of your advanced R guide, formatted with proper code blocks, sections, and GitHub-friendly styling:

⸻


# 🔬 Advanced R for Public Health & Biology

*Professional-level R techniques for epidemiological analysis, biostatistics, and health data science*

---

## 🧰 **Prerequisites**
```r
# Install required packages
install.packages(c("dplyr", "tidyr", "survival", "ggplot2", "sf", "leaflet", "randomForest", "shiny"))


⸻

1️⃣ Advanced Data Wrangling

Reshaping Data with tidyr

library(tidyr)

# Wide to long (for time series)
long_data <- pivot_longer(
  data = my_data,
  cols = c("Jan", "Feb", "Mar"),
  names_to = "Month",
  values_to = "Cases"
)

# Long to wide (for summaries)
wide_data <- pivot_wider(
  data = long_data,
  names_from = "Month",
  values_from = "Cases"
)

Conditional Logic with case_when()

library(dplyr)

risk_data <- covid_data %>%
  mutate(Risk_Category = case_when(
    Cases > 1000 & Deaths > 50 ~ "🔴 High Risk",
    Cases > 500 ~ "🟡 Medium Risk",
    TRUE ~ "🟢 Low Risk"
  ))


⸻

2️⃣ Advanced Statistical Modeling

Logistic Regression (Binary Outcomes)

model <- glm(
  Mortality ~ Age + Comorbidity + Treatment,
  data = patient_data,
  family = binomial()
)

# Get odds ratios
exp(coef(model))

Survival Analysis (Kaplan-Meier)

library(survival)

km_fit <- survfit(Surv(Time, Status) ~ Treatment, data = cancer_data)
plot(km_fit, col = c("red", "blue"), 
     main = "Survival Probability by Treatment")


⸻

3️⃣ Geospatial Health Mapping

library(sf)
library(leaflet)

# Create interactive disease map
leaflet(geo_data) %>%
  addTiles() %>%
  addCircleMarkers(
    lng = ~Longitude,
    lat = ~Latitude,
    radius = ~sqrt(Cases)*2,
    color = ~colorQuantile("Reds", Cases)(Cases),
    popup = ~paste(Location, "<br>Cases:", Cases)
  )


⸻

4️⃣ Machine Learning for Public Health

Random Forest Prediction

library(randomForest)

rf_model <- randomForest(
  Disease ~ Age + Blood_Pressure + BMI,
  data = train_data,
  importance = TRUE
)

# Variable importance plot
varImpPlot(rf_model, main = "Predictive Factors")


⸻

5️⃣ Automated Reporting

RMarkdown Template

```{r}
# Analysis chunk
summary_stats <- health_data %>%
  group_by(Region) %>%
  summarize(Mean_Cases = mean(Cases))

knitr::kable(summary_stats)




⸻

---

## 6️⃣ **Interactive Dashboards with Shiny**
```r
library(shiny)

ui <- fluidPage(
  titlePanel("Disease Outbreak Dashboard"),
  sidebarLayout(
    sidebarPanel(
      selectInput("region", "Select Region:", 
                 choices = unique(data$Region))
    ),
    mainPanel(
      plotOutput("outbreak_plot"),
      tableOutput("summary_table")
    )
  )
)

server <- function(input, output) {
  output$outbreak_plot <- renderPlot({
    data %>%
      filter(Region == input$region) %>%
      ggplot(aes(Date, Cases)) + geom_line()
  })
}

shinyApp(ui, server)
```

---

## 📂 **Project Structure**
```
/my_project
├── /data
│   ├── raw_data.csv
│   └── cleaned_data.rds
├── /scripts
│   ├── 01_cleaning.R
│   └── 02_analysis.R
├── /outputs
│   ├── figures/
│   └── reports/
└── README.md
```

---
Here's the **third-level GitHub Markdown guide**, focusing on cutting-edge techniques for public health and biological data science with R:

```markdown
# 🧬 R for Genomic Epidemiology & Advanced Biostatistics

*High-performance computing, genomic data analysis, and AI applications in public health*

---

## 🧩 **Prerequisites**
```r
install.packages(c("BiocManager", "DESeq2", "phyloseq", "caret", "mlr3", "furrr"))
BiocManager::install(c("limma", "edgeR", "VariantAnnotation"))
```

---

## 1️⃣ **High-Performance Computing**
### Parallel Processing with `furrr`
```r
library(furrr)
plan(multisession, workers = 8) # Use 8 CPU cores

# Parallelized t-tests across 1000 genes
results <- future_map_dfr(1:1000, ~{
  data <- rnorm(100)
  t.test(data)$p.value
})
```

### Memory Optimization
```r
library(bigmemory)
big_data <- read.big.matrix("genomic_data.csv", 
                          type = "double",
                          backingfile = "genomic.bin")
```

---

## 2️⃣ **Genomic Data Analysis**
### RNA-Seq with DESeq2
```r
library(DESeq2)

dds <- DESeqDataSetFromMatrix(
  countData = counts,
  colData = metadata,
  design = ~ Condition
)

dds <- DESeq(dds)
res <- results(dds)
plotMA(res, main="Differential Expression")
```

### GWAS Visualization
```r
library(qqman)
manhattan(gwasResults, 
          chr = "CHR", 
          bp = "BP", 
          p = "P", 
          snp = "SNP",
          main = "Genome-Wide Association Study")
```

---

## 3️⃣ **Microbiome Analysis**
### Phyloseq Pipeline
```r
library(phyloseq)

physeq <- phyloseq(
  otu_table(OTU, taxa_are_rows = TRUE),
  sample_data(META),
  tax_table(TAX)
)

plot_richness(physeq, measures = c("Shannon", "Simpson"))
```

---

## 4️⃣ **AI for Public Health**
### Deep Learning with `keras`
```r
library(keras)

model <- keras_model_sequential() %>%
  layer_dense(units = 64, activation = "relu") %>%
  layer_dropout(0.2) %>%
  layer_dense(units = 1, activation = "sigmoid")

model %>% compile(
  optimizer = "adam",
  loss = "binary_crossentropy",
  metrics = "accuracy"
)
```

### XGBoost for Disease Prediction
```r
library(xgboost)

dtrain <- xgb.DMatrix(data = as.matrix(train_x), label = train_y)
model <- xgb.train(data = dtrain, 
                  nrounds = 100,
                  objective = "binary:logistic")
```

---

## 5️⃣ **Reproducible Research**
### Docker Integration
```dockerfile
FROM rocker/r-ver:4.2.0
RUN R -e "install.packages('renv')"
COPY . .
RUN R -e "renv::restore()"
```

### Workflow Automation
```r
library(targets)
tar_script({
  list(
    tar_target(raw_data, read.csv("data.csv")),
    tar_target(clean_data, preprocess(raw_data)),
    tar_target(model, fit_model(clean_data))
  )
})
```

---

## 🗂️ **Advanced Project Structure**
```
/advanced_project
├── /notebooks
│   ├── 01_RNAseq_analysis.Rmd
│   └── 02_ML_pipeline.ipynb
├── /containers
│   ├── Dockerfile
│   └── singularity.def
├── /workflows
│   ├── Snakefile
│   └── nextflow.config
└── /reports
    ├── manuscript.Rmd
    └── supplement.html
```

---

## 🚀 **Cutting-Edge Resources**
- [Bioconductor Workflows](https://www.bioconductor.org/help/workflows/)
- [AI in Epidemiology Course](https://www.coursera.org/specializations/ai-public-health)
- [High-Performance R Book](https://www.highperfr.com/)

---

![Genomics](https://img.shields.io/badge/Genomics-109989?style=flat)
![AI](https://img.shields.io/badge/AI_Health-FF6F61?style=flat)
![HPC](https://img.shields.io/badge/HPC-4051B5?style=flat)

*For computational biologists and digital epidemiologists*
```

*Created with ❤️ for public health and biology students*
````
