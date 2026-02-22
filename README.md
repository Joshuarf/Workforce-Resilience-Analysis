# Workforce Resilience Analysis
## Overview
This project develops a Workforce Resilience framework to evaluate structural labor market stability and downside risk across major industry segments using publicly available JOLTS and CES data.

The analysis constructs a composite Resilience Index, evaluates its relationship with employment growth, and translates industry-level signals into simulated employer-level exposure metrics.

The objective is to demonstrate applied workforce analytics capabilities including:

* Metric design
* Time-series and panel modeling
* Simulation-based exposure modeling
* Employment-weighted risk aggregation
* Visualization

---

## Research Questions

1. Can hiring volatility signal labor market dynamism rather than distress?
2. How can industry-level resilience signals be translated into employer-level workforce exposure?
3. How concentrated is sensitivity-adjusted workforce risk across sectors?

---

## Methodology
**1. Workforce Resilience Index**

The Workforce Resilience Index combines two complementary labor market signals:

* **Hiring Volatility (Stability Signal)** <br>
Rolling hiring volatility captures instability in workforce dynamics.

* **Net Hiring Strength (Expansion Signal)** <br>
Net hiring captures structural workforce growth momentum.

Both components are min–max scaled within industry and combined using equal weighting:

Resilience = 0.5 × (1 − Volatility_scaled) + 0.5 × NetHiring_scaled

Equal weights provide a neutral baseline. In a production environment, weights could be empirically optimized.

<br><br>
**2. Panel Analysis**

A descriptive panel regression evaluates the relationship between lagged hiring volatility and subsequent employment growth.

Results suggest that elevated hiring volatility may reflect labor market dynamism rather than fragility in certain sectors.

(Standard errors are clustered at the industry level; results should be interpreted as directional rather than causal.)

<br><br>
**3. Firm-Level Simulation**

To translate industry-level signals into employer-level insight, firms are simulated with:

* Archetype-based industry exposure portfolios
* Firm-specific labor sensitivity
* Employment-weighted exposure aggregation

Two complementary metrics are constructed:

**RAES (Resilience-Adjusted Employment Share)**<br>
Employment-weighted structural workforce stability

**ARES (Adjusted Risk-Exposed Share)**<br>
Employment-weighted downside vulnerability adjusted for labor sensitivity


---
## Key Findings

* Hiring volatility is positively associated with subsequent employment growth in this sample period.
* Sector concentration can amplify aggregate workforce risk.
* Healthcare-dominant firms exhibit lower structural resilience and higher sensitivity-adjusted risk exposure in the simulated environment.
* Aggregate workforce stability can mask uneven distribution of firm-level vulnerability.

---
## Repository Structure
````
workforce-resilience-analysis/
│
├── README.md
├── requirements.txt 
├── data
│   └── ces.csv
│   └── jots.csv   
└── notebook
    └── workforce_resilience_analysis.ipynb
````
----
## Reproducibility

Install dependencies:
````
pip install -r requirements.txt
````
---
## Primary libraries used:
* pandas
* numpy
* matplotlib
* seaborn
* statsmodels
* scikit-learn

---
## Data Sources

Publicly available data from the U.S. Bureau of Labor Statistics (BLS):
* Job Openings and Labor Turnover Survey (JOLTS)
* Current Employment Statistics (CES)

Data can be downloaded directly from:

https://www.bls.gov/

---
## Skills Demonstrated

* Labor market time-series analysis
* Index construction and normalization
* Panel regression modeling
* Simulation-based employer exposure modeling
* Employment-weighted risk aggregation
* Data storytelling

---
## Author

Josh Russell-Fritch

Data Professional | Economist | Workforce Analytics
