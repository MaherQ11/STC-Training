# STC Jawwy TV — Viewer Behavior, Forecasting & Recommendations

Analysis of ~1M viewing records from Jawwy TV (STC's streaming service) to answer three business questions:

1. **What do viewers watch, and in what quality (HD vs SD)?**
2. **How much will people watch over the next two months?**
3. **What should we recommend to each viewer next?**

**Tools:** Python (pandas, NumPy, statsmodels, scikit-learn, Plotly) · Power BI

---

## Key Findings

| # | Finding | Number |
|---|---------|--------|
| 1 | Series drive most of the watch time | **71%** of total watch time (255K hrs) vs 29% for movies (103K hrs) |
| 2 | Series viewers are few but heavy; movie viewers are many but light | Series: ~3,900 users averaging **65 hrs** each · Movies: ~11,400 users averaging **9 hrs** each |
| 3 | Series are watched mostly in SD | **87%** of series views are SD |
| 4 | Movies are watched mostly in HD | **68%** of movie views are HD |
| 5 | Viewing peaks at the end of the week | Peak day: **Friday** (~794 hrs on average) |

## Recommendations

1. **Turn movie viewers into series viewers.** Movie viewers outnumber series viewers about 3 to 1, but each series viewer watches ~7x more hours. Using the recommendation engine to suggest series to movie viewers targets the biggest growth gap.
2. **Look into why series are watched in SD.** 87% SD on series vs 68% HD on movies suggests a device or connection pattern (e.g. long sessions on mobile data). Worth checking before investing in more HD series content.
3. **Plan capacity and new releases around Friday.** Use the forecast to schedule releases and server capacity on peak days.

---

## Approach

### 1. Viewer behavior & HD analysis
- Cleaned 1,048,575 viewing records: converted Excel dates, fixed data types, trimmed program names.
- Aggregated by program, program type (series/movie) and HD flag: unique viewers, number of views, total watch hours.

### 2. Watch-time forecasting (SARIMA)
- Daily total watch hours for 86 days (Jan–Mar 2018).
- Grid-searched SARIMA parameters by AIC; selected **SARIMA(0,1,1)x(0,1,1,12)**.
- Forecast the next 60 days with a confidence interval.

### 3. Recommendation engine (collaborative filtering)
- Built a program × user rating matrix (**8,013 programs × 11,578 users**).
- Used K-Nearest Neighbors with cosine similarity to find programs watched by similar audiences.
- Example — viewers of *Moana* get: *Trolls*, *Surf's Up: WaveMania*, *The Mermaid Princess*, *The Boss Baby*.

---

## Power BI Dashboard

KPI cards, actual vs forecast watch time, HD vs SD breakdown, series vs movies, and top recommendations.

<img width="1034" height="586" alt="STC Dashboard" src="https://github.com/user-attachments/assets/d22ad5e8-8515-4225-a70e-71dea75beabe" />

---

## Limitations & Next Steps

- **The data may be cut off.** The viewing file has exactly 1,048,575 rows — the maximum an Excel sheet can hold — so some records were likely lost when it was exported.
- **Weekly pattern in the forecast.** The data is daily, so a 7-day seasonal period would match the weekly cycle (Friday peak) better than 12. Next step: refit with a weekly season and the daily frequency set explicitly.
- **Forecast accuracy is not measured yet.** Next step: hold out the last 2–3 weeks and report the average error (MAE / MAPE).
- **Recommendations are not evaluated yet.** Next step: hide part of each viewer's history and check how often the hidden programs appear in the top-5 recommendations.

---

## How to Run

```bash
pip install pandas numpy matplotlib plotly statsmodels scikit-learn scipy pyxlsb openpyxl
jupyter notebook "STC Jawwy project1.ipynb"
```

The dataset files (`stc TV Data Set_T1.xlsb`, `_T2.xlsx`, `_T3.xlsx`) are not included in this repository.

---

**Author:** Maher Al-Qurashi · [GitHub](https://github.com/MaherQ11) · [LinkedIn](https://www.linkedin.com/in/maher-al-qurashi-69a163351/)
