# 📌 Bank of England Employer Project: NLP Analysis of G-SIB Announcements

# 📖 Overview
This project is part of the University of Cambridge Career Accelerator, in collaboration with the Bank of England. The goal is to analyse quarterly earnings announcements from Global Systemically Important Banks (G-SIBs) using advanced Natural Language Processing (NLP) techniques.

By leveraging NLP methods such as topic modelling, sentiment analysis, and summarisation, we aim to provide insights that support financial stability assessments and risk monitoring.

# 🎯 Objectives
Extract and process textual data from G-SIB earnings calls.
Identify key themes (topics) and emerging trends.
Conduct sentiment analysis.
Generate summary insights with instruction-tuned models.
Provide a structured dashboard or reporting format for key stakeholders.

# 📂 Project Structure
'''
├── Bank Data/                    # Raw and processed data
│   ├── raw/                 # Unprocessed transcripts & reports
|   ├── parsed/              # parsed unstructured data to structure format
│   ├── Preprocessed/             # parsed data that has Preprocessed text data
|   ├─- Sentimented/           # Preprocessed text data that have sentiment metrics added
|   ├─- Topics/           # Preprocessed text data that have sentiment metrics added with topics.
├── Notebooks/               # Jupyter/Colab notebooks for analysis
│   ├── Parser/          
│   ├── EDA/             # Exploratory Data Analysis
│   ├── Prerprocessing/        
│   ├── Sentiment analysis/
│   ├── Topic Modeling/
│   ├── LLM/
│   ├── Conolidate/
│   ├── Summarisation.ipynb    # Text summarisation methods
│   ├── Visualization         # Data visualisation scripts
├── reports/                 # Documentation and findings
├── requirements.txt         # Required Python libraries
├── README.md                # This file
└── .gitignore               # Ignored files
'''
