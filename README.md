# Swiggy Restaurant Analytics Dashboard

A Power BI project analysing restaurant performance data across 9 Indian cities using real-world Swiggy data, focused on understanding what separates high-performing restaurants from the rest — and where the platform has gaps in quality, cuisine representation, and city-level delivery experience.

---

## Project Overview

This dashboard was built to answer a question that matters to anyone in the food-tech or restaurant industry:

> *Across 8,680 unique restaurants (86,810 records) on Swiggy, what patterns actually predict customer satisfaction — and where are the biggest gaps between what the platform promotes and what actually performs?*

The analysis covers restaurants across 9 major Indian cities, surfacing patterns in delivery time, ratings, cuisine distribution, and city-level engagement that aren't visible from looking at individual listings.

---

## Dataset

| Attribute | Detail |
|---|---|
| Total rows | 86,810 records |
| Unique restaurants | 8,680 |
| Cities covered | 9 major Indian metros |
| Time period | Cross-sectional snapshot (no date column) |
| Grain | One row = one restaurant-cuisine combination (multiple rows per restaurant) |

**Columns:** Restaurant ID, Area, City, Restaurant Name, Price Range, Delivery Time, Average Rating (1–5 scale), Total Ratings (volume), Food Type, Address

**Important data note:** This dataset does not contain individual order or transaction data. Average Rating reflects quality score (scale of 2–5, platform average 3.63). Total Ratings reflects review volume (range 20–10,000, platform average 156.63). These are two distinct measures and were analysed separately.

---

## Business Objective

Restaurant aggregator platforms generate enormous amounts of performance data. This project translates that data into three specific business questions:

1. Which cuisine type delivers the best customer experience — and is Swiggy promoting it?
2. Which cities are strong vs struggling on quality and engagement — and what does that mean for platform investment?
3. Does price range predict customer satisfaction, or are cheaper restaurants punching above their weight?

---

## Key Findings

### Finding 1 — Swiggy's most common cuisines are its worst performers

Across the top 5 cuisine types, South Indian is the only cuisine that outperforms the platform average on both quality and speed:

| Cuisine | Avg Rating | vs Platform (3.63) | Avg Delivery Time | vs Platform (53.97 min) |
|---|---|---|---|---|
| South Indian | 3.70 | ↑ above | 52 min | ↑ faster |
| North Indian | 3.55 | ↓ below | 52 min | ↑ faster |
| Fast Food | 3.55 | ↓ below | 53 min | on par |
| Indian | 3.52 | ↓ below | 55 min | ↓ slower |
| Chinese | 3.43 | ↓ below | 55 min | ↓ slower |

**The gap:** Indian and Chinese are the two most common cuisines on the platform and both rank last on quality score and delivery speed. South Indian — the best performer on both metrics — is significantly underrepresented in the restaurant mix.

**Business implication:** Swiggy is heavily promoting cuisines that deliver a below-average customer experience while undervaluing its strongest performing category. There is a clear case for actively onboarding more South Indian restaurant partners.

---

### Finding 2 — City performance splits into three distinct tiers

Comparing all 9 cities against platform averages (3.63 rating, 156.63 total ratings):

| City | Avg Rating | Total Ratings | Tier |
|---|---|---|---|
| Chennai | 3.78 | 161.72 | Strong |
| Bangalore | 3.76 | 148.52 | Strong |
| Hyderabad | 3.70 | 307.22 | Strong — standout |
| Kolkata | 3.70 | 163.30 | Strong |
| Ahmedabad | 3.60 | 103.86 | Struggling |
| Surat | 3.58 | 117.81 | Struggling |
| Mumbai | 3.60 | 118.21 | Struggling |
| Pune | 3.55 | 112.83 | Struggling |
| Delhi | 3.53 | 133.26 | Struggling |

**Hyderabad is the standout city.** With 307.22 average total ratings — nearly double the platform average — Hyderabad has both the highest customer engagement and an above-average quality score. It is the platform's strongest market by both measures.

**Mumbai is the most concerning finding.** As India's largest city and likely Swiggy's highest order volume market, Mumbai sits below average on both rating (3.60) and engagement (118.21 total ratings). Customers there are having a below-average experience and reviewing less than other cities — a signal of low satisfaction or low engagement that warrants investigation.

**Business implication:** Swiggy should promote South Indian cuisine specifically in the five struggling cities — Delhi, Mumbai, Pune, Surat, and Ahmedabad — and target reducing delivery times in those markets from the current platform average of 54 minutes toward 40 minutes to improve customer experience where it is weakest.

### Finding 3 — Price does not predict customer satisfaction on Swiggy

Across 119 distinct price bands, the relationship between price and rating is almost flat in the realistic price range where the vast majority of restaurants sit:

| Price Band | Avg Rating | vs Platform (3.63) |
|---|---|---|
| ₹150 | 3.73 | ↑ above |
| ₹250 | 3.62 | at average |
| ₹350 | 3.69 | ↑ above |
| ₹450 | 3.77 | ↑ above |

**The gap is only 0.04 points** between ₹150 and ₹450 restaurants — a three-times difference in price producing virtually no difference in customer satisfaction. Note: the ₹0 price band (5 restaurants, likely data errors) and ₹2,500 band (3 restaurants, insufficient sample) were excluded from this analysis as unreliable outliers.

**Business implication:** Since price does not predict customer satisfaction on Swiggy, customers are better off choosing lower-priced restaurants of the same rating rather than paying more for a marginally better score. For Swiggy, this means price alone is not a reliable signal of restaurant quality — the platform should surface rating and delivery time more prominently than price in its ranking and recommendation logic.

---

## Key Performance Indicators

| Metric | Value |
|---|---|
| Total restaurants analysed | 8,680 unique restaurants across 86,810 records |
| Cities covered | 9 |
| Platform avg delivery time | 53.97 minutes |
| Platform avg rating | 3.63 / 5.0 |
| Platform avg total ratings | 156.63 reviews per restaurant |
| Platform avg price | ₹348.44 |
| Best performing city | Hyderabad (3.70 rating, 307 avg reviews) |
| Most underperforming city | Mumbai (3.60 rating, 118 avg reviews) |
| Best performing cuisine | South Indian (3.70 rating, 52 min delivery) |
| Weakest performing cuisine | Chinese (3.43 rating, 55 min delivery) |

> **Note:** The Power BI dashboard KPI card labelled "Avg. Rating" currently displays 156.63, which is the average Total Ratings (review volume), not the quality score. The correct average rating score is 3.63. This will be corrected in the next dashboard update.

---

## Dashboard Preview

### Dashboard Overview
![Dashboard](Images/dashboard_home.png)

### Restaurant Analysis
![Restaurant](Images/restaurant_analysis.png)

### Price Analysis
![Price](Images/price_analysis.png)

### KPI Summary
![KPI](Images/kpi_summary.png)

---

## Dashboard Features

The Power BI dashboard is a descriptive overview of the Swiggy restaurant landscape. It covers distribution and concentration across areas and cities — not performance analysis.

**What the dashboard shows:**
- 4 interactive filter slicers — drill into any city, area, restaurant, or address
- Top 5 most served food types by restaurant count
- Top 10 areas with the highest restaurant concentration
- Top 10 cities by restaurant count — displayed on an India map
- Most expensive areas by average price

**What the dashboard does not show:**
- Cuisine performance by rating or delivery time (Finding 1)
- City-level quality and engagement benchmarking (Finding 2)
- Price vs rating relationship (Finding 3)

The three key findings above were produced through deeper pivot table analysis in Excel, separate from the Power BI dashboard. Updating the dashboard to incorporate these findings is planned as a future enhancement.

---

## Tools Used

| Tool | Purpose |
|---|---|
| Power BI | Dashboard development and visualisation |
| Power Query | Data cleaning and transformation |
| DAX | Custom calculated measures |
| Microsoft Excel | Initial data inspection and pivot analysis |

---

## Analytical Approach

1. Dataset profiling — row count, column audit, null checks, data type validation
2. Distribution analysis — rating range (2–5), total ratings range (20–10,000), delivery time range
3. Cuisine-level analysis — average rating and delivery time across top 5 food types vs platform baseline
4. City-level analysis — quality score and engagement volume across all 9 cities, segmented into performance tiers
5. Anomaly identification — Hyderabad's outsized engagement, Mumbai's underperformance relative to city size
6. Recommendation framing — specific cities, specific cuisines, specific measurable targets

**Key analytical limitation:** The dataset is a cross-sectional snapshot with no date column, so trend analysis over time was not possible. All findings reflect a single point-in-time view of restaurant performance. Individual order-level transaction data was also not available, so findings are based on restaurant-level aggregates.

---

## Business Recommendations

1. **Promote South Indian cuisine in underperforming cities.** Delhi, Mumbai, Pune, Surat, and Ahmedabad are all below platform average on rating and engagement. South Indian is the only top-5 cuisine that outperforms on both quality and speed — it is the most defensible cuisine to expand in struggling markets.

2. **Target delivery time reduction in the five struggling cities.** The platform average is 54 minutes. A target of 40 minutes in the bottom-tier cities would bring them in line with customer satisfaction benchmarks and likely improve both rating scores and review volume.

3. **Investigate Mumbai specifically.** As India's largest city, Mumbai's below-average performance on both quality and engagement is the most strategically important finding in this dataset. Whether it reflects logistics challenges, restaurant partner quality, or customer behaviour, it warrants a dedicated deep-dive.

4. **Replicate the Hyderabad model.** Hyderabad's 307 average total ratings — nearly double the platform average — suggests a highly engaged customer base and strong restaurant partner quality. Understanding what drives that engagement could inform platform strategy in other cities.

5. **Deprioritise price as a quality signal.** Since price and rating are almost uncorrelated across the realistic price range (0.04 rating difference between ₹150 and ₹450), Swiggy's recommendation algorithm should weight rating score and delivery time more heavily than price when surfacing restaurants to customers.

---

## Author

**Harshit Kaishwar**
📧 kaishwarsid@gmail.com
🔗 [LinkedIn](https://www.linkedin.com/in/harshit-kaishwar-7286112b9)
🐙 [GitHub](https://github.com/Harshit-Kai)
