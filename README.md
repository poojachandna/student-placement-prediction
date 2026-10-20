# College Student Placement Prediction | Binary Logistic Regression

An econometric analysis of the academic, technical, and interpersonal factors associated with college student placements, using binary logistic regression in GNU PSPP.

## Project Overview

This project investigates the factors associated with college students' placement outcomes using a binary logistic regression model. The analysis examines how academic performance, cognitive ability, practical experience, communication skills, and extracurricular involvement relate to the probability of securing a placement.

Using a dataset of 10,000 student records, the study identifies statistically significant predictors, evaluates classification performance, and interprets the relationships between student characteristics and placement outcomes.

**Statistical Method:** Binary Logistic Regression  
**Software:** GNU PSPP  
**Dataset:** College Student Placement Factors (Kaggle)

## Dataset Description

The dataset consists of **10,000 observations and 10 variables**, including a student identifier, eight explanatory variables, and a binary placement outcome.

**Dependent Variable:**
- `Placement` — Student placement status (1 = Placed, 0 = Not Placed)

**Independent Variables:**

| Variable | Description |
|---|---|
| IQ | Student intelligence quotient |
| CGPA | Cumulative Grade Point Average |
| Prev_Sem_Result | Previous semester academic result |
| Academic_Performance | Academic performance score |
| Internship_Experience | Whether the student has internship experience |
| Extra_Curricular_Score | Extracurricular involvement score |
| Communication_Skills | Communication skills rating |
| Projects_Completed | Number of completed projects |

All 10,000 observations were included in the analysis, with no missing cases reported.

## Methodology

The analysis was conducted using **binary logistic regression** in GNU PSPP.

Logistic regression was selected because the dependent variable, placement status, is binary. Unlike ordinary linear regression, logistic regression models the log-odds of an outcome and produces predicted probabilities between 0 and 1.

The analytical process involved:

1. Importing and examining the student placement dataset.
2. Identifying the dependent variable and eight explanatory variables.
3. Estimating a binary logistic regression model using PSPP.
4. Evaluating model fit using Cox & Snell and Nagelkerke pseudo-R² statistics.
5. Examining regression coefficients, p-values, and odds ratios to identify significant predictors.
6. Assessing classification performance using a confusion matrix.
7. Interpreting the findings in the context of student employability.

A classification threshold of 0.5 was used.

## Model Results

| Evaluation Metric | Result |
|---|---|
| Observations | 10,000 |
| Overall Classification Accuracy | 90.2% |
| Non-Placement Classification Accuracy | 96.0% |
| Placement Classification Accuracy | 60.8% |
| Cox & Snell Pseudo-R² | 0.37 |
| Nagelkerke Pseudo-R² | 0.62 |
| −2 Log Likelihood | 4,372.52 |

The model achieved an **in-sample classification accuracy of 90.2%**.

However, classification performance differed across the two outcomes. The model correctly classified 96.0% of non-placed students but only 60.8% of placed students, indicating substantially weaker sensitivity to successful placements.

The Nagelkerke pseudo-R² of 0.62 indicates relatively strong model fit under this measure, although pseudo-R² values are not directly equivalent to the proportion of variance explained in ordinary linear regression.

## Key Findings

Four explanatory variables were statistically significant at the 5% significance level.

| Predictor | Odds Ratio | Statistical Significance |
|---|---:|---|
| IQ | 1.11 | p < 0.001 |
| CGPA | 2.86 | p < 0.001 |
| Communication Skills | 1.91 | p < 0.001 |
| Projects Completed | 1.97 | p < 0.001 |

**Interpretation:**

- **CGPA:** A one-unit increase in CGPA was associated with approximately 2.86 times the odds of placement, holding the other predictors constant.
- **Communication Skills:** A one-unit increase in communication skills was associated with approximately 91% higher placement odds.
- **Projects Completed:** Each additional completed project was associated with approximately 97% higher placement odds.
- **IQ:** A one-point increase in IQ was associated with approximately 11% higher placement odds, based on the reported rounded odds ratio.

Previous semester results, academic performance scores, internship experience, and extracurricular scores were not statistically significant at the 5% level after controlling for the other variables.

These findings suggest that academic performance, communication skills, and practical project experience are important correlates of placement outcomes in the analyzed dataset.

The reported relationships are statistical associations and should not be interpreted as causal effects.

## Model Limitations

Several considerations are important when interpreting the findings:

- **Class imbalance:** Approximately 83.4% of observations represent non-placed students. Overall accuracy can therefore overstate the model's effectiveness in identifying successful placements.
- **In-sample evaluation:** The reported classification results were obtained from the analyzed dataset. Performance on unseen student records was not independently established.
- **Omitted variables:** Placement outcomes may also depend on factors not represented in the model, including institution-specific recruitment opportunities, labor market conditions, and interview performance.
- **Interpretation:** Logistic regression identifies associations between explanatory variables and placement odds, rather than establishing causality.

Future extensions could involve out-of-sample validation, precision and recall analysis, alternative classification thresholds, and comparison with other classification methods.

## Repository Structure

```text
student-placement-prediction/
├── README.md
├── results/
│   └── pspp_output.pdf
└── presentation/
    └── placement_analysis.pdf
```

## Project Files

- **[PSPP Regression Output](results/pspp_output.pdf):** Original statistical output containing the logistic regression specification, model summary, classification table, and coefficient estimates.
- **[Project Presentation](presentation/placement_analysis.pdf):** Academic presentation documenting the research objective, dataset, methodology, and findings.

## Conclusion

The analysis identified **CGPA, IQ, communication skills, and completed projects** as statistically significant predictors of student placement outcomes.

The project demonstrates the application of binary logistic regression to a practical employability question, with an emphasis on hypothesis testing, interpreting odds ratios, evaluating classification performance, and communicating statistical findings.

*Originally developed as a collaborative academic project and documented here as an individual portfolio case study.*
