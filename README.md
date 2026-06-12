# Mumbai Housing Price Index — Saturation Analysis

## What is this project?

Mumbai's housing prices have been rising for over a decade. But markets don't grow forever — there's always a ceiling. This project tries to find that ceiling.

Using quarterly Housing Price Index data published by the Reserve Bank of India, we fit a logistic growth (S-curve) model to Mumbai's HPI trend and estimate the saturation point — the level where price growth effectively stops.

---

## Dataset

**Source:** Reserve Bank of India — Housing Price Index (City-wise, Quarterly)  
**Coverage:** Q1 2010-11 to Q4 2024-25 (76 quarterly observations)  
**Base Year:** 2010-11 = 100  
**Access:** [data.gov.in](https://data.gov.in) / [Dataful.in](https://dataful.in/datasets/17611/)

---

## What we found

| Parameter | Value |
|---|---|
| Saturation Level (K) | 424.02 |
| Inflection Year (t₀) | 2013.64 |
| Current HPI (Q4 2024-25) | ~418 |
| Remaining gap to saturation | ~1.4% |

Mumbai's HPI is **effectively at saturation** on the 2010-11 base scale. The market grew aggressively between 2010 and 2016, slowed post-2017, and has been flattening since 2019. The COVID period (2020-2022) caused a temporary suppression but did not change the long-term trajectory.

---

## Project Structure

Mumbai-Housing-Saturation/
├── data/
│   ├── raw/                  ← original RBI Excel file
│   └── processed/            ← cleaned Mumbai-only CSV
├── notebooks/
│   ├── 01_data_cleaning.ipynb
│   ├── 02_eda.ipynb
│   └── 03_saturation_model.ipynb
├── outputs/
│   ├── figures/              ← plots
│   └── results/              ← model output JSON
└── README.md

---

## Notebooks

| Notebook | What it does |
|---|---|
| `01_data_cleaning` | Extracts Mumbai HPI from raw RBI Excel, converts quarters to decimal years |
| `02_eda` | Trend plot, year-on-year growth rate analysis |
| `03_saturation_model` | Fits logistic curve, estimates K, r, t₀, plots fitted vs actual |

---

## Tools

Python, Pandas, NumPy, Matplotlib, SciPy

---
Kaggle : https://www.kaggle.com/code/omcaru/mumbai-housing-saturation-analysis
---

## A note on interpretation

Saturation here is relative to the 2010-11 base index. The RBI itself switched to a 2022-23 base covering 18 cities — which effectively resets the index. In absolute rupee terms, Mumbai prices may still rise. What this model captures is the **growth velocity approaching zero** on a consistent long-run series — which is the real signal.
