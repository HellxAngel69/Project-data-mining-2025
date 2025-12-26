Project_datamining

1. Project Overview

This project is a **Data Mining pipeline implemented in Java** using **Weka**. It supports:

* Data loading and preprocessing
* Data cleaning and feature selection
* Handling imbalanced data with SMOTE
* Classification
* Association & sequence mining

Each major task is controlled by a separate `Main` class so that the program can be run **step-by-step** depending on the experiment.


## 2. Project Structure

Project_datamining
│
├── src
│   ├── analysis
│   │   └── Analysis.java
│   │
│   ├── classification
│   │   └── Classification.java
│   │
│   ├── cleaning
│   │   ├── FeatureSelection.java
│   │   ├── HandleDirty.java
│   │   └── SMOTEPROCESSING.java
│   │
│   ├── prepare
│   │   ├── CSVtoARFF.java
│   │   ├── Load_data.java
│   │   └── NewData.java
│   │
│   └── project
│       ├── Main.java
│       ├── MainApriori.java
│       ├── MainClassification.java
│       └── SequenceMining.java

3. Requirements

* **Java JDK 17**
* **Weka library** (weka.jar added to project build path)
* IDE: Eclipse / IntelliJ (recommended)

> Make sure `weka.jar` is added to **External Libraries** before running.


4. Input & Output Convention

All `Main` classes use **command-line arguments**:


java <MainClass> <input_file_path> <output_file_path>


* **Input**: path to dataset file (CSV or ARFF)
* **Output**: path where the processed/result file will be saved

Example:

```
java Main data/input.csv result/output.arff
```

5. How to Run Each Main Class

5.1 Main.java (Full Pipeline)

Runs the complete data mining workflow:

* Run the CSV to ARFF first
* If you use eclipse, open run configurations in the program arguments tab input the file path of the ARFF file and the output path where you want to save the new file


Command:

```
java project.Main <input_file> <output_file>
```

Example:

"D:/Khoa/2025-2026/Data mining/project/heart_disease.arff" "D:/Khoa/2025-2026/Data mining/project/output"

java project.Main data/raw_data.csv result/final_data.arff


5.2 MainClassification.java

* Load processed ARFF file by using the run configurations like above
* Apply classification model
* You can see some code with // thats mean you can choose when and which model to use and choose between 70/30 or CV 10 folds by delete the // at the model and method you want

Command:

```
java project.MainClassification <input_arff> <output_file>
```

Example:

```
java project.MainClassification data/cleaned.arff result/classification.txt
```
"D:/Khoa/2025-2026/Data mining/project/output/After_Cleaning.arff" "D:\Khoa\2025-2026\Data mining\project"

5.3 MainApriori.java

Runs association rule mining using Apriori.

Command:

```
java project.MainApriori <input_arff>
```

Example:

```
java project.MainApriori data/transaction.arff 
```
"D:/Khoa/2025-2026/Data mining/project/output/After_Cleaning.arff"

5. Description of Core Modules

prepare package

* `CSVtoARFF.java`: Converts CSV files to ARFF format
* `Load_data.java`: Loads dataset into Weka `Instances`
* `NewData.java`: Handles creation of new datasets

cleaning package

* `HandleDirty.java`: Handles missing or dirty data
* `FeatureSelection.java`: Feature selection using Information Gain + Ranker
* `SMOTEPROCESSING.java`: Handles class imbalance using SMOTE

classification package

* `Classification.java`: Implements classification algorithms and evaluation

analysis package

* `Analysis.java`: Performs dataset analysis and statistics

6. Notes & Common Issues

* Ensure correct **file path** (absolute path recommended)
* ARFF files must have a **class attribute** defined for classification


*** MAKE SURE TO USE RUN CONFIGURATIONS FOR EVERY MAIN AND MAKE SURE ALL THE MAIN HAVE THE VM ARGUMENTS ***

--add-opens java.base/java.lang=ALL-UNNAMED
--add-opens java.base/java.lang=ALL-UNNAMED
--add-opens java.base/java.io=ALL-UNNAMED
--add-opens java.base/java.util=ALL-UNNAMED
