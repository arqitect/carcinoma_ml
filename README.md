# Machine Learning for Breast Cancer Subtype Classification
A data science project to classify breast cancer subtypes from TCGA gene expression data using a Random Forest model. This project demonstrates data cleaning, feature analysis, model training, and in-depth evaluation in a bioinformatics context.

## Project Objective
The goal of this project was to build a machine learning model capable of accurately predicting the molecular subtype of a breast cancer tumor (e.g., Luminal A, Luminal B, Basal, HER2-positive) using its gene expression profile. This is a crucial task in oncology as the subtype largely determines a patient's prognosis and treatment path.

## Dataset
The data was sourced from The Cancer Genome Atlas (TCGA) via the cBioPortal.

Dataset: Breast Invasive Carcinoma (TCGA, PanCancer Atlas)

Features: Normalized mRNA expression levels (RNA-Seq z-scores) for over 20,000 genes.

Labels: Clinical data containing the molecular subtype for each patient sample.

The complete dataset can be explored and downloaded from cBioPortal.
https://www.cbioportal.org/study/summary?id=brca_tcga_pan_can_atlas_2018

## Methodology
The project was implemented in a Python environment using Google Colab. The main steps were:

1. Data Loading & Preprocessing: Loaded the clinical and gene expression text files. The data was cleaned by handling metadata, transposing the expression matrix, and standardizing patient IDs for merging.

2. Data Cleaning: The merged dataset was further cleaned by removing samples with missing subtype labels and filtering out non-tumor ("Normal") tissue samples.

3. Model Training: A Random Forest Classifier was chosen for its strong performance and interpretability. The data was split into an 80% training set and a 20% testing set to ensure a fair evaluation of the model's performance on unseen data.

4. Model Evaluation: The model was evaluated using overall accuracy, a confusion matrix, and a detailed classification report (including precision, recall, and F1-score for each subtype).

5. Feature Importance Analysis: The feature_importances_ attribute of the trained Random Forest model was used to identify and visualize the top 10 most influential genes in the classification task.

## Results
The trained model achieved a final accuracy of 81.48% on the unseen test set, demonstrating a strong ability to distinguish between cancer subtypes based on gene expression patterns.

Key Visualizations
Confusion Matrix: The matrix shows high performance on the diagonal, with most misclassifications occurring between the biologically similar Luminal A and Luminal B subtypes.

Top 10 Important Genes: The feature importance analysis identified several genes known to be critical in breast cancer biology, confirming that the model learned biologically relevant patterns.

## How to Run
You can run this project yourself directly in your browser using Google Colab.

Download the two data files (data_clinical_patient.txt and data_mrna_seq_v2_rsem_zscores_ref_all_samples.txt) from the cBioPortal link above.

Open the .ipynb file from this repository in Google Colab.

Upload the two data files to the Colab environment.

Run the cells sequentially from top to bottom.
