# Ophthalmology Authorship Gender Trends  
## Data Scraping & Processing

This repository contains the Python implementation used to analyze gender representation in ophthalmology authorship. The project utilizes the **NCBI Entrez API** to fetch publication metadata and custom string-parsing logic to prepare names for gender identification.

---

## 📂 Repository Structure

- **Ophthalmology_Scraper.ipynb**  
  The primary Jupyter Notebook containing the full data pipeline:
  - PubMed Search & Fetch – Queries PubMed for specific journals and timeframes  
  - Data Extraction – Parses XML to extract titles, authors, journals, and publication years  
  - Name Separation – Splits full names into first and last names for API compatibility  
  - CSV Export – Generates standardized output files (e.g., AfterCovidAO.csv)

- **Main Data**  
  Aggregated raw dataset used for final analysis

---

## 🛠️ Technical Stack

- Bio.Entrez – Programmatic access to PubMed  
- Pandas – Data structuring and DataFrame operations  
- NumPy – Numerical operations and data cleaning  
- CSV – Reading and writing structured data  

---

## 🚀 How to Use the Code

### 1. Install Requirements
```bash
pip install biopython pandas numpy
```

### 2. NCBI Authentication
```python
from Bio import Entrez
Entrez.email = "your.email@example.com"
```

### 3. Run the Scraper
- Processes data in chunks of 50 papers to prevent API timeouts  
- Includes `time.sleep(1)` to comply with NCBI rate limits  

### 4. Name Processing
Custom functions:
- `first_separate_name`  
- `last_separate_name`  

Handles:
- Missing values ("N/A")  
- Multi-component names  
- Consistent formatting for gender analysis  

---

## 📊 Data Processing Notes

- Missing Data: Checks for `AuthorList`, `ForeName`, and `LastName` fields to avoid errors  
- Accuracy: Gender classification performed using Gender API (~98% median accuracy)

---

## ✉️ Contact

**Alisa Vendrow**  
alisavendrow@gmail.com  

Monta Vista High School  
Stanford University Department of Ophthalmology  
