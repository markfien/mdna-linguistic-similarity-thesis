# mdna-linguistic-similarity-thesis
MSc Thesis – Text-as-Data Study
This repository contains the full computational pipeline used to analyse changes in linguistic similarity across Management Discussion and Analysis (MD&A) disclosures between 2019 and 2024.
The study applies Natural Language Processing (NLP) techniques to measure narrative similarity within and across firms using TF–IDF vectorisation and cosine similarity.
Due to copyright restrictions, annual report PDFs and extracted MD&A texts are not included in this repository.

Full Workflow Overview
The correct execution order of the analysis pipeline is:
1. PDF → Intermediate
2. Intermediate → Clean
3. Clean → Pairwise Outcomes
4. Descriptive Statistics
   
Each step is excecuted using a dedicated script

Required Folders:
1. data_intermediate -> with a folder in it of "pdfs" where you save the pdf's you want to extract
2. data_clean
3. outputs -> with a folder named "similarity_excel" where you save similarity matrixes you make after you have collected all similarity scores out of Pairwise Outcomes
4. Scripts

File naming (crucial)

To ensure compatibility with the scripts use the following naming conventions:
1. PDF Files -> firm_report_year.pdf -> example: ak_report_2019.pdf
2. Always check the firm tickers and the years in the scripts

Description of the scripts:

Step 1: PDF -> Intermediate. 

Purpose:
1. Extract MD&A sections from annual report PDFs
2. Remove tables and non-narritive blocks
3. Apply Structural cleaning
4. Log page ranges and extraction megadata

Step 2: Intermediate -> clean

Purpose:
1. Convert text to lowercase
2. Remove punctuation
3. Remove digits
4. Remove English stopwords
5. Normalize whitespace
6. Produce NLP-ready corpus

Step 3: Clean -> Pairwise outcomes

Purpose:
1. Load all cleaned firm texts for a given year
2. Apply TF-IDF vectorisation
3. Compute cosine similarity matrix
4. Export similarity matrices
5. These data can be filled in a excel document (make a similarity matrix for 2019 and 2024 with all similarity scores) -> needed for descriptive statistics

Step 4: Descriptive statistics

Purpose:
1. Compute descriptive statistics of similarity distributions
2. Calculate year-to-year changes
3. Identify convergence/divergence patterns
4. Generate summary tables
5. Export final Excel file with multiple sheets

Methodological Summary

This study applies a sequential text-processing and similarity-measurement pipeline:

1. Targeted MD&A extraction from PDFs
2. Standardized NLP preprocessing
3. TF–IDF vectorisation
4. Cosine similarity computation
5. Distributional and firm-level descriptive analysis

Reproducibility

To replicate the analysis:

1. Place annual report PDFs in: data_intermediate/pdfs
2. Run scripts in this exact order:

    1. Pdf to intermediate.ipynb
    2. intermediate-_clean.ipynb
    3. clean -_ Pairwise outcomes.ipynb
    4. Descriptive statistics.ipynb

Outputs will automatically populate the outputs/ directory.

Data Availability

Annual reports are publicly available via company investor relations websites.

This repository does not include:

1. Raw PDFs
2. Extracted MD&A text
3. Cleaned corpora

Academic Context

This repository accompanies an MSc thesis investigating changes in linguistic similarity in corporate MD&A reporting between 2019 and 2024.
