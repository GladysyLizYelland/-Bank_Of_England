# 📌 Bank of England Employer Project: NLP Analysis of G-SIB Announcements

# 📖 Overview
This project is part of the University of Cambridge Career Accelerator, in collaboration with the Bank of England. The goal is to analyse quarterly earnings announcements from Global Systemically Important Banks (G-SIBs) using advanced Natural Language Processing (NLP) techniques.

By leveraging NLP methods such as topic modelling, sentiment analysis, and summarisation, we aim to provide insights that support financial stability assessments and risk monitoring.

*Note: This repository originated as a collaborative group project. I have since extended the codebase, expanded the scope, and integrated domain-specific architectures as an independent learning initiative.*

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
│   ├── topic_modeling/          # BERTopic pipelines optimised with FinTextSim vs. BGE baselines
│   ├── llm/                     # Prompt engineering and fine-tuning experiments (e.g., FinGPT, Gemma, Falcon)
│   ├── consolidate/             # Data merging, alignment, and schema aggregation
│   ├── summarisation.ipynb      # Text summarisation methods (extractive/abstractive)
│   └── visualization/           # Notebooks for generating analytical plots and charts
│
├── reports/                     # Generated insights, final documentation, and project findings
├── requirements.txt             # Python dependencies and library versions
├── .gitignore                   # Specified files and directories hidden from version control
└── README.md                    # Project documentation
```
## 🤖 Embedding Model Selection

This pipeline uses sentence-transformer embeddings to vectorize text for downstream sentiment analysis and topic modeling. Before running the scripts, you must select the model that fits your data source.

As a team we chose to use `BAAI/bge-base-en-v1.5` , but I wanted to modify it to use `JehnenS/FinTextSim`, to observe if we obtain better outcomes. Due to a bit more research, I did that stated the reasons why.

> [!TIP]
> **Recommended Baseline:** Use `JehnenS/FinTextSim` for structural financial analysis and `BAAI/bge-base-en-v1.5` if expanding into general news text.

### 📊 Model Comparison

| Feature / Metric | `JehnenS/FinTextSim` (Default) | `BAAI/bge-base-en-v1.5` |
| :--- | :--- | :--- |
| **Primary Domain** | **Strictly Financial Texts** (10-Ks, Earnings Calls) | **General Purpose Texts** (News, Web Data) |
| **Training Focus** | S&P 500 10-K Filings (Items 7 & 7A) | Broad multi-domain corpus pairs |
| **Clustering Performance** | +81% Intratopic Similarity | Standard broad baseline groupings |
| **Noise Reduction** | -100% Intertopic Overlap | Susceptible to semantic overlap in finance jargon |
| **Architecture / Specs** | 384 Dimensions / 256 Context Window | 768 Dimensions / 512 Context Window |

---

### 🔍 Selection Logic

* **Use `JehnenS/FinTextSim` for `Notebooks/Topic Modeling/`**
  This model is optimized for corporate financials. When paired with `BERTopic`, it forms sharp, distinct economic clusters. Running standard models without financial tuning introduces high misclassification rates due to dense domain terminology.
  
* **Use `BAAI/bge-base-en-v1.5` for `Notebooks/Sentiment analysis/` & General Retrieval**
  If your `Bank Data/raw/` directory expands to include broad macroeconomic news articles, customer letters, or generic texts, use the BGE base model to ensure out-of-domain robustness.

---

### ⚙️ How to Configure

Toggle the model initialization string inside your configuration or initialization cells:

```python
# Configuration parameters for your execution pipeline

# 1. Use for deep financial text parsing & topic extraction
MODEL_PATH = "JehnenS/FinTextSim"

# 2. Uncomment to switch to broad general-purpose semantic tasks
# MODEL_PATH = "BAAI/bge-base-en-v1.5"
```

