# Consumer Shopping Trends 2026 — R Analysis

> Exploratory data analysis of nearly 12,000 customer records examining how digital habits, geography, income, and psychology shape modern purchasing behaviour.

---

## Dataset

**Consumer Shopping Trends 2026** · 11,791 observations · 25 variables

| Variable group | Examples |
|---|---|
| Demographics | `age`, `gender`, `city_tier` |
| Digital behaviour | `daily_internet_hours`, `social_media_hours`, `smartphone_usage_years` |
| Shopping activity | `monthly_online_orders`, `avg_online_spend`, `shopping_preference` |
| Attitudes & scores | `impulse_buying_score`, `tech_savvy_score`, `environmental_awareness` |
| Returns | `return_frequency`, `free_return_importance` |

---

## Research questions

| # | Question | Visualisation |
|---|---|---|
| 1 | How does online presence affect the intensity of online shopping? | Bubble chart + facets |
| 2 | How do personal factors affect shopping preference? | Violin + jitter plot |
| 3 | How are shopping decisions different across city tiers? | Diverging bar chart |
| 4 | Does income level drive return behaviour? | Faceted jitter + stat_summary |
| 5 | What factors most encourage impulse buying? | Lollipop chart |
| 6 | Does "need to touch" stop tech-savvy users from buying online? | Stacked bar + quadrants |
| 7 | How does free return importance affect actual return rate? | Ribbon + trend line |

---

## Key findings

- **Time pressure** is the strongest predictor of impulse buying — outperforming income and online spend.
- **Age** separates shopping preferences: online shoppers skew younger, store shoppers older, hybrid is the most age-diverse segment.
- **Tier 1 cities** show higher online payment trust; **Tier 3 cities** unexpectedly score higher on environmental awareness.
- **Income and return frequency** are nearly uncorrelated — returns are driven by product experience, not financial capacity.
- Even **tech-savvy users who prefer to touch products** still choose online shopping as their plurality preference.

---

## Tech stack

```r
library(tidyverse)   # data manipulation pipeline
library(ggplot2)     # all visualisations
library(dplyr)       # grouped summaries, filtering
```

**Techniques used:** `group_by()` + `summarise()`, `pivot_longer()` / `pivot_wider()`, `slice_sample()`, `case_when()`, `cor()`, `weighted.mean()`, `geom_violin`, `geom_ribbon`, `geom_smooth`, `facet_wrap`, `stat_summary`, `scale_color_gradient2`

---

## Project structure

```
consumer-shopping-r/
├── project.R                              # full analysis script
├── Consumer_Shopping_Trends_2026.csv      # dataset
├── index.html                             # portfolio page (GitHub Pages)
└── README.md
```

---

## Setup

```r
# Install required packages
install.packages(c("tidyverse", "ggplot2", "dplyr"))

# Load dataset
ds <- read.csv("Consumer_Shopping_Trends_2026.csv")

# Run full analysis
source("project.R")
```

---

## Visual design system

All plots share a unified theme and three-colour palette:

```r
pal3 <- c("#00B4D8", "#7209B7", "#F72585")

my_theme <- theme_minimal() +
  theme(
    plot.title    = element_text(face = "bold", size = 16),
    plot.subtitle = element_text(color = "gray40", size = 12),
    strip.text    = element_text(face = "bold", size = 12),
    legend.position = "bottom"
  )
```

---

*R Programming course project · 2026*
