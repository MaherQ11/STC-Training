# STC Jawwy TV — Data Analysis Project

This project was completed as part of the STC Virtual Training Program. It consists of three data analysis tasks on the Jawwy TV platform dataset.

---

## Project Structure

```
├── STC Full Project.ipynb   # Main notebook (all 3 tasks combined)
└── README.md
```

---

## Tasks Overview

### Task 1 — HD Flag & User Behavior Analysis
Analyzing user watching behavior and studying the impact of HD vs SD streaming quality across different content types (Movies vs Series).

### Task 2 — Watch Time Forecasting
Building a forecasting model to predict the expected total watch time for the next two months using a Moving Average approach based on historical daily data.

### Task 3 — Content Recommendation System
Building a collaborative filtering recommendation system based on user ratings to suggest similar programs to users.

---

## Key Findings

- **Task 1:** Most users prefer watching content in HD. Series have a higher session count compared to Movies.
- **Task 2:** Watch time is relatively stable across the week, with Friday showing the highest average. The forecast indicates consistent viewing levels going forward.
- **Task 3:** Users who watched *Moana* are likely to enjoy: Trolls, Surf's Up: WaveMania, The Mermaid Princess, Storks, and The Jetson.

---

## Libraries Used

- `pandas` — Data manipulation
- `numpy` — Numerical operations
- `matplotlib` / `plotly` — Data visualization
- `scikit-learn` — KNN model for recommendations
- `statsmodels` — Time series analysis
- `pyxlsb` / `openpyxl` — Reading Excel files

---

## Dataset

The datasets used are proprietary to STC Jawwy TV and are not included in this repository.
