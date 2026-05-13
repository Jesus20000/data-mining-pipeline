# 🕷️ Data Mining Pipeline — Web Scraping & Analysis

A collection of **5 real-world data mining projects** built with Python, covering web scraping, API integration, text preprocessing, and data visualization. Each task targets a different data source and analytical objective.

---

## 📁 Project Structure

```
data-mining-pipeline/
│
├── task1_job_listings/
│   └── task1_job_listings.ipynb        # Job scraper — JustJoin.it
│
├── task2_news_headlines/
│   └── task2_news_headlines.ipynb      # News analyzer — RSS feeds
│
├── task3_price_tracker/
│   └── task3_price_tracker.ipynb       # Price tracker — books.toscrape.com
│
├── task4_weather/
│   └── task4_weather.ipynb             # Weather analysis — Open-Meteo API
│
├── task5_covid_dashboard/
│   └── task5_covid_dashboard.ipynb     # COVID dashboard — disease.sh API
│
├── requirements.txt
└── README.md
```

---

## 📋 Tasks Overview

| # | Task | Source | Method | Key Output |
|---|------|--------|--------|------------|
| 1 | Job Listings Scraper | JustJoin.it | BeautifulSoup + Pagination | Jobs by city, salary, company |
| 2 | News Headlines Analyzer | BBC, CNN, Al Jazeera + 6 more | RSS XML parsing | Word frequency, word cloud |
| 3 | Product Price Tracker | books.toscrape.com | BeautifulSoup + Simulation | Price trends over 5 sessions |
| 4 | Weather Data Analysis | Open-Meteo API | REST API + JSON | Temp & rainfall — 10 Polish cities |
| 5 | COVID-19 Dashboard | disease.sh API | REST API + JSON | Global EDA + historical trends |

---

## 🗂️ Task Details

### 📌 Task 1 — Web Scraping of Job Listings
**Source:** [JustJoin.it](https://justjoin.it) — largest Polish IT/tech job board

**What it does:**
- Scrapes all job listings across all Polish cities using pagination
- Extracts: job title, company, city, salary range, remote status, category tags
- Cleans and normalizes data (deduplication, salary parsing, text normalization)
- Analyzes top hiring companies, cities, salary distribution, remote vs on-site ratio

**Libraries:** `requests`, `beautifulsoup4`, `pandas`, `matplotlib`, `seaborn`

**Outputs:** 4 charts + `justjoin_jobs_cleaned.csv`

---

### 📌 Task 2 — News Headlines Analyzer
**Sources:** BBC, CNN, Al Jazeera, Sky News, NPR, Reuters, Fox News, NBC, ABC, Guardian, DW, Euronews, France24, AP, TIME

**What it does:**
- Fetches RSS feeds from 15 major international news sources simultaneously
- Parses XML to extract headlines, descriptions, and publication dates
- Performs text preprocessing: lowercasing → punctuation removal → tokenization → stopword filtering
- Analyzes word frequency globally and per news source separately

**Libraries:** `requests`, `beautifulsoup4`, `pandas`, `matplotlib`, `seaborn`, `wordcloud`

**Outputs:** 4 charts (including word cloud) + `news_headlines_cleaned.csv` + `news_word_frequency.csv`

---

### 📌 Task 3 — Product Price Tracker
**Source:** [books.toscrape.com](https://books.toscrape.com) — sandbox e-commerce site

**What it does:**
- Scrapes all 1000 books across 50 pages (title, price, star rating, availability)
- Records Session 1 as the real scraped baseline
- Simulates 4 additional weekly scraping sessions with ±15% realistic price fluctuations
- Tracks price changes per product over time and identifies most volatile items

**Libraries:** `requests`, `beautifulsoup4`, `pandas`, `numpy`, `matplotlib`, `seaborn`

**Outputs:** 5 charts + `price_tracker_all_sessions.csv` + `price_tracker_changes.csv`

---

### 📌 Task 4 — Weather Data Collection and Analysis
**Source:** [Open-Meteo](https://open-meteo.com) — free public weather archive API (no key required)

**Cities:** Warsaw, Kraków, Gdańsk, Wrocław, Poznań, Łódź, Katowice, Szczecin, Lublin, Białystok

**What it does:**
- Fetches 30 days of historical daily weather data for 10 major Polish cities
- Collects: max/min/mean temperature, precipitation, wind speed, rainfall, snowfall
- Classifies each day into weather conditions (Sunny, Mild, Rainy, Heavy Rain, Snowy)
- Identifies warmest, coldest, wettest, driest, and windiest cities

**Libraries:** `requests`, `pandas`, `numpy`, `matplotlib`, `seaborn`

**Outputs:** 6 charts (including temperature heatmap) + `poland_weather_daily.csv`

---

### 📌 Task 5 — COVID-19 Public Health Data Dashboard
**Source:** [disease.sh](https://disease.sh) — Open Disease Data API (no key required)

**What it does:**
- Fetches global summary, per-country breakdown (~200 countries), continental aggregation, and 90-day historical trend
- Computes derived metrics: case fatality rate, recovery rate, cases per million population
- Identifies most affected countries by raw cases and by deaths per million (population-adjusted)
- Plots 7-day rolling averages to smooth out daily reporting noise

**Libraries:** `requests`, `pandas`, `numpy`, `matplotlib`, `seaborn`

**Outputs:** 7 charts + `covid_countries.csv` + `covid_continents.csv` + `covid_historical_90days.csv`

---

## 🛠️ Libraries Used

| Library | Purpose |
|---------|---------|
| `requests` | HTTP requests to websites and APIs |
| `beautifulsoup4` | HTML and XML parsing |
| `pandas` | Data storage, cleaning, and analysis |
| `numpy` | Numerical operations |
| `matplotlib` | Data visualization |
| `seaborn` | Statistical visualizations |
| `wordcloud` | Word cloud generation (Task 2 only) |
| `lxml` | XML parser backend for BeautifulSoup |

---

## ⚙️ Requirements

**Python:** 3.10+

Install all dependencies:

```bash
pip install -r requirements.txt
```

---

## 🚀 How to Run

**1. Clone the repository**
```bash
git clone https://github.com/your-username/data-mining-pipeline.git
cd data-mining-pipeline
```

**2. Install dependencies**
```bash
pip install -r requirements.txt
```

**3. Navigate to any task folder**
```bash
cd task1_job_listings
jupyter notebook task1_job_listings.ipynb
```

**4. Run the notebook**

In Jupyter: **Kernel → Restart & Run All**

> Each notebook is fully self-contained — no shared files or dependencies between tasks.

---

## 📊 Data Sources

| Task | Source | Type | API Key |
|------|--------|------|---------|
| Task 1 | justjoin.it | Web scraping | ❌ Not required |
| Task 2 | BBC, CNN, Al Jazeera + 12 more | RSS feeds | ❌ Not required |
| Task 3 | books.toscrape.com | Web scraping | ❌ Not required |
| Task 4 | Open-Meteo API | REST API | ❌ Not required |
| Task 5 | disease.sh API | REST API | ❌ Not required |

---

## 💡 Key Insights

- **Task 1:** Warsaw and Kraków dominate Polish job listings; SQL and Python remain the top demanded skills
- **Task 2:** Word frequency analysis across 15 sources reveals which global topics dominate news cycles
- **Task 3:** Price volatility simulation shows ~15% fluctuation range typical of dynamic e-commerce pricing
- **Task 4:** Coastal cities (Gdańsk, Szczecin) receive more rainfall; southern cities (Kraków, Katowice) are slightly warmer
- **Task 5:** Europe and North America account for the majority of global COVID-19 cases despite lower case fatality rates than Africa

---

## 👤 Author

**Isa Zeynalov**
Data Analyst | WSB University Warsaw — Data Science M.Sc.

---

## 📄 License

This project is for academic purposes — WSB University, Semester 4 Team Project.
