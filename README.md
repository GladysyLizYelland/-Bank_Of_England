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

```text
.
├── bank_data/                   # Data storage layer
│   ├── raw/                     # Raw, unstructured transcripts and documents
│   ├── parsed/                  # Structured formats extracted from raw text
│   ├── preprocessed/            # Cleaned, tokenised text data optimized for NLP
│   ├── sentimented/             # Preprocessed data with sentiment scores/metrics added
│   └── topics/                  # Final processed text mapped with dominant themes/topics
│
├── notebooks/                   # R&D and analysis environment
│   ├── parser/                  # Raw text extraction and structured parsing pipelines
│   ├── eda/                     # Exploratory Data Analysis notebooks
│   ├── preprocessing/           # Text cleansing, tokenisation, and normalization routines
│   ├── sentiment_analysis/      # Sentiment scoring models and implementation i.e. Finbert
│   ├── topic_modeling/          # Latent Dirichlet Allocation (LDA) / BERTopic models +/ FinTextSim
│   ├── llm/                     # LLM prompting and fine-tuning experiments i.e FinGPT, Gemma, Falcon 8
│   ├── consolidate/             # Data merging, alignment, and schema aggregation
│   ├── summarisation.ipynb      # Text summarisation methods (extractive/abstractive)
│   └── visualization/           # Notebooks for generating analytical plots and charts
│
├── reports/                     # Generated insights, final documentation, and project findings
├── requirements.txt             # Python dependencies and library versions
├── .gitignore                   # Specified files and directories hidden from version control
└── README.md                    # Project documentation
```

