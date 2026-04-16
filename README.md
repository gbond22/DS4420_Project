# DS4420_Project
Group repository for DS4420 final project group 40 (Gavin Bond, Benji Kataoka, Preetish Paul)

The raw Survey files were too large for this repository; they were initially
added, but the "data" file now only holds the schema and survey files. The 
required files are: 

- `data/stack-overflow-developer-survey-2024/survey_results_public.csv`
- `data/stack-overflow-developer-survey-2025/survey_results_public.csv`

Which can both be downloaded from this URL:
https://survey.stackoverflow.co/

Once downloaded, please place the files in the directories listed in the file
names above.

Project File Run Order & Explanation:
1. preprocessing.ipynb: 
- Libraries: numpy, pandas
- Description: combines 2024 & 2025 survey data, harmonizes columns across years, filters for pro devs only, drops rows with missing target variable.
- Output: data/combined_survey.csv

2. cf_model.ipynb:
- Implementation Specifics: User-User Collaborative Filtering, Manual, Python
- Libraries: numpy, pandas, matplotlib
- Description: runs user-user CF on combined survey data after minimal preprocessing, reports results.
- Relevant Metrics & Plots: MAE & binary accuracy, predicted score histogram, mean predicted trust by AI sentiment classification, mean predicted trust by AI complexity belief classification mean predicted trust by seniority level. 
- Outputs: all scores and plots contained inside notebook.

3. DS4420_Final_Bayes.Rmd:
- Implementation Specifics: Bayesian Logistic Regression, w/ libraries, R
- Libraries: readr, dplyr, ggplot2, brms
- Description: runs Bayesian logistic regression on combined survey data after minimal preprocessing, reports results.
- Relevant Metrics & Plots: Bayesian coefficient summary, SEs, 95% CI, Rhat, ESS, fitted probability summary, conditional effects plots for feature set, posterior probability scatter plot, prediction histogram, and boxplots.
- Outputs: DS4420_Final_Bayes.pdf (knitted Rmd), figures/bayes_coef_forest.png, figures/bayes_conditional_aisent.png

4. DS4420_NN_MLP_Classifier.ipynb:
- Implementation Specifics: Multi-Layer Perceptron Neural Network, w/ libraries, python
- Libraries: numpy, pandas, matplotlib, seaborn, scikit-learn (MLPClassifier, train_test_split, StandardScaler, LabelEncoder, classification_report, confusion_matrix, ConfusionMatrixDisplay, accuracy_score, resample, permutation_importance)
- Description: runs MLP classifier on combined survey data after minimal preprocessing, reports results.
- Relevant Metrics & Plots: T-T split, out of sample accuracy, 5 class classification report, confusion matrix, training loss curve, distribution of predicted probabilities, feature permutation importance plot.
- Outputs: all scores and plots contained inside notebook.

5. POC_model.ipynb:
- Not necessary to run; initial Phase 1 proof of concept NN model on 2025 data only.