# Project-data-mining-2025
A Java-based data mining framework implementing preprocessing, feature selection, SMOTE, Resample, classification, and sequence mining using Weka.

## Features
- Data overview
- Data cleaning (missing values, noise handling)
- Feature selection (Info-Gain)
- SMOTE oversampling, Resampling
- Classification: RandomForest, Naive Bayes
- Sequence mining
- CSV to ARFF converter

## Structure
project-datamining-2025/
 ├── src/
 ├── data/
 ├── results/
 ├── docs/
 └── README.md

## How to Run
1. Import project into Eclipse/IntelliJ
2. Add Weka JAR to classpath
3. Select run configurations, in the arguments tab, paste your input file path and output path
4. Run Main.java in src/project/

## Thinking Process
1. Identify dataset issues  
2. Preprocess with Info-Gain + SMOTE + Resampling 
3. Train classifiers  
4. Evaluate metrics  
5. Compare performance  
