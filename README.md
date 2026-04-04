# mta-fare-evasion-analysis
Predictive modeling and Monte Carlo simulation of MTA fare evasion patterns — Pace University MTA Analytics Expo 2026
# MTA Fare Evasion — Predictive Analytics & Revenue Recovery

> **Pace University | MTA Analytics & Career Discovery Expo 2026**  
> Presented April 10, 2026 · New York City

---

## Overview

The MTA lost an estimated **$918 million** to fare evasion in 2024 — triple the pre-pandemic level — with bus evasion running at 44% and subway evasion at 10% as of early 2025. This project applies predictive modeling and Monte Carlo simulation to identify the operational drivers of fare evasion across MTA buses and subways, and to quantify the revenue recovery potential of targeted enforcement and infrastructure interventions.

**Hypothesis:**
> *Fare evasion rates across MTA buses and subways are predictable using operational variables including service frequency, delays, crowding, and OMNY adoption rates. We hypothesize that service quality and payment accessibility are key drivers of evasion, and that identifying high-risk routes and stations can inform targeted enforcement and infrastructure strategies to help reduce revenue loss across the system.*

---

## Team

| Name | Role |
|---|---|
| **Dare Akinpelu** | Hypothesis design, research, narrative & presentation |
| **Alexis Rivera** | Data cleaning, merging & Python pipeline |
| **Eric Chisala** | Predictive modeling, regression analysis & Tableau visualization |

---

## Datasets

All datasets sourced from the [MTA Open Data Portal](https://data.ny.gov) — no authentication required.

| Dataset | Role | Source |
|---|---|---|
| MTA Bus Fare Evasion: Beginning 2019 | Dependent variable (bus) | [data.ny.gov](https://data.ny.gov/d/uv5h-dfhp) |
| MTA Subway Fare Evasion: Beginning 2018 | Dependent variable (subway) | [data.ny.gov](https://data.ny.gov/d/qvzv-gbap) |
| MTA Bus Customer Journey-Focused Metrics: Beginning 2017 | Service quality predictors | [data.ny.gov](https://data.ny.gov/d/8mkn-d32t) |
| MTA Bus Hourly Ridership: 2020–2024 | Ridership volume + OMNY adoption | [data.ny.gov](https://data.ny.gov/d/kv7t-n8in) |
| MTA Subway Hourly Ridership | Ridership volume + OMNY adoption | [data.ny.gov](https://data.ny.gov/d/wujg-7c2s) |
| MTA Summonses & Arrests: Beginning 2019 | Enforcement intensity proxy | [data.ny.gov](https://data.ny.gov/d/t5gv-5e8q) |
| MTA Subway Additional Platform Time: Beginning 2020 | Subway delay proxy | [data.ny.gov](https://data.ny.gov/d/3qem-6v3v) |

> **Note:** Raw data files are not committed to this repository. All datasets are publicly available at the links above. The pipeline fetches them automatically via the Socrata API.

---

## Analytical Approach

### Variables

**Dependent variable:**
- Quarterly bus fare evasion rate (% of riders who do not pay)

**Independent variables:**
- Additional bus stop time (avg. minutes beyond scheduled wait)
- Additional travel time (avg. minutes beyond scheduled journey time)
- Customer journey time performance (% of journeys within 5 min of schedule)
- OMNY adoption rate (% of rides paid via contactless — payment accessibility proxy)
- Quarterly enforcement intensity (summonses + arrests per quarter)

### Pipeline

```
Data acquisition (Socrata API)
        ↓
Data cleaning & standardization (Python / Pandas)
        ↓
Aggregation to quarterly analysis table
        ↓
Exploratory data analysis + correlation matrix
        ↓
Predictive modeling (Linear Regression + Logistic Regression)
        ↓
Feature importance ranking
        ↓
Monte Carlo simulation (10,000 iterations × 3 scenarios)
        ↓
Dashboard (Tableau / Power BI) + Presentation
```

### Models

- **Linear Regression** — predicts continuous evasion rate from operational variables
- **Logistic Regression** — classifies routes as high / medium / low evasion risk
- **Random Forest + Gradient Boosting** — tested for comparison, feature importance extraction
- **Monte Carlo Simulation** — projects revenue recovery range under pessimistic, baseline, and optimistic enforcement/infrastructure scenarios

---

## Key Findings

*To be updated as analysis progresses.*

| Finding | Value |
|---|---|
| Baseline annual evasion loss (2024) | $918M |
| Bus evasion rate (Q1 2025) | 44% |
| Subway evasion rate (Q1 2025) | 10% |
| Projected recovery — optimistic scenario | $161M–$277M |
| Projected recovery — baseline scenario | $65M–$153M |
| Strongest predictor of evasion | TBD after modeling |

---

## Monte Carlo Simulation Results

Simulating revenue recovery under three scenarios (10,000 iterations each):

| Scenario | Mean Recovery | 5th Percentile | 95th Percentile |
|---|---|---|---|
| Pessimistic (no change) | $35M | $15M | $57M |
| Baseline (current trajectory) | $109M | $65M | $153M |
| Optimistic (OMNY 85% + targeted enforcement) | $219M | $161M | $277M |

![Monte Carlo Simulation](outputs/03_monte_carlo.png)

---

## Project Timeline

| Date | Milestone |
|---|---|
| March 27, 2026 | Team registration deadline |
| April 1, 2026 | Hypothesis + dataset selection submitted |
| April 6, 2026 | Midpoint check — cleaned data + early visualizations |
| April 8, 2026 | Draft dashboard + methodology summary |
| April 10, 2026 | Final submission + **Expo Day (2–5pm)** |

---

## Context

This project was developed for the **MTA Analytics & Career Discovery Expo** hosted by Pace University Career Services in partnership with the Metropolitan Transportation Authority. Student teams analyzed real MTA open datasets and presented findings to MTA analytics professionals and recruiters.

The MTA operates the largest public transportation network in North America, serving 3.4 million subway riders and 2 million bus riders daily across New York City.

---

## License

MIT License — see [LICENSE](LICENSE) for details.

---

## Acknowledgements

- [MTA Open Data Program](https://www.mta.info/open-data) for publicly available datasets
- [Citizens Budget Commission](https://cbcny.org) for fare evasion cost analysis
- [NYS Office of the State Comptroller](https://www.osc.ny.gov) for MTA fiscal reporting
- Pace University Career Services — Mahindra Guman, Associate Director
