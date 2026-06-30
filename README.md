# Barcelona Urban Intelligence System

A production-grade data analytics platform built on a **medallion architecture** 
(Bronze → Silver → Gold) that transforms raw Barcelona city data into actionable business intelligence covering urban complaints, traffic accidents, air quality, 
and EV adoption advisory.

## Architecture

The project follows a **Medallion Architecture** with 4 layers:

| Layer | Purpose |
|---|---|
| **Bronze** | Raw ingestion — preserves source data exactly as received |
| **Silver** | Cleaning, standardisation, type casting, deduplication |
| **Gold** | Star schema — dimension & fact tables ready for BI queries |
| **Analytics** | ML models, RAG assistant, EV advisory system |

> Data flows in one direction: Bronze → Silver → Gold → Analytics

## What This System Answers

| Business Question | Gold Table |
|---|---|
| Which districts have the most complaints? | `fct_complaints_daily` |
| Which complaint types take longest to resolve? | `fct_resolution_times` |
| What causes accidents, where and when? | `fct_accidents_by_cause` |
| Is this district's air above EU limits? | `fct_airquality_monthly` |
| Should a citizen buy an EV in their district? | `ev_advisory` |

## Tech Stack

- **Database:** DuckDB (embedded analytical database)
- **Data Processing:** Python, Pandas, NumPy
- **Architecture:** Medallion (Bronze/Silver/Gold)
- **Schema Design:** Star schema with dimension and fact tables
- **ML & AI:** Scikit-learn, RAG indexing
- **Visualisation:** Matplotlib, Seaborn, Plotly

## Project Structure

| Notebook | Layer | Description |
|---|---|---|
| `01_bronze.ipynb` | Bronze | Raw data ingestion |
| `02_silver.ipynb` | Silver | Cleaning & standardisation |
| `03_gold.ipynb` | Gold | Star schema & business tables |
| `04_rag_index.ipynb` | Analytics | RAG AI assistant index |
| `05_ml_analysis.ipynb` | Analytics | ML models & predictions |

## Getting Started

**1. Clone the repository**
```bash
git clone git@github.com:claudia-moliner/barcelona-urban-intelligence.git
cd barcelona-urban-intelligence
```

**2. Install dependencies**
```bash
pip install -r requirements.txt
```

**3. Download the dataset**
The DuckDB database file (`barcelona_urban.db`) is available here:
[Download from Google Drive](YOUR_GOOGLE_DRIVE_LINK)

Place it in the `/data` folder before running the notebooks.

**4. Run the notebooks in order**
01_bronze → 02_silver → 03_gold → 04_rag_index → 05_ml_analysis

## Key Findings

- Identified the top 3 districts by complaint volume and average resolution time
- Built an EV advisory system combining air quality and charging infrastructure data
- Applied regression modelling to predict complaint resolution times by district and channel

## Author

**Claudia Moliner** — Data Analyst
[GitHub](https://github.com/claudia-moliner) · [Email](mailto:cmolinercalvet@gmail.com)
