# E-Commerce Conversion Funnel Analysis

End-to-end analysis of an e-commerce clickstream dataset in Python, tracing users from **Browse → Add to Cart → Checkout → Purchase** to find where they drop off and which channels, regions, devices, and product categories convert best. Outputs a multi-sheet Excel report and a set of charts.


## Overview

Most e-commerce traffic never converts. This project quantifies exactly *where* that loss happens and *who* it happens to, then turns the numbers into concrete recommendations — which channel deserves more budget, which region's playbook to copy, and how much revenue is sitting in abandoned carts.

**Key questions answered:**

- At which funnel stage do we lose the most sessions?
- Which marketing channel delivers the highest conversion rate and AOV?
- How does performance vary by region, device, and product category?
- What do daily and hourly traffic patterns look like?
- What is the bounce rate, and what is the recoverable revenue opportunity?

---

## Dataset
It is a synthetic dataset generated using the following libraries:python, pandas, numpy

| Column | Description |
|---|---|
| `Session_ID` | Unique identifier per browsing session |
| `User_ID` | Unique identifier per user |
| `Timestamp` | Event datetime |
| `Channel` | Acquisition channel (Organic, Paid, Social, Email, …) |
| `Region` | Geographic region of the session |
| `Device` | Device type (Desktop, Mobile, Tablet) |
| `Product_Category` | Product category viewed or purchased |
| `Funnel_Stage` | Stage reached by the event |
| `Revenue` | Revenue attributed to the event |
| `Session_Duration_Min` | Session length in minutes |
| `Bounce_Flag` | Whether the session bounced (`Yes` / `No`) |


## Analysis Performed

**1. Feature engineering**
Derives `Date`, `DayOfWeek`, `Hour`, and `WeekNumber` from the raw timestamp, then rolls events up into a session-level table with each session's `Max_Funnel_Stage`.

**2. Overall funnel**
Stage-by-stage session counts, conversion rates, and drop-off rates.

**3. Segment breakdowns**
The same funnel logic applied across channel, region, device, and product category — each with conversion rate, total revenue, and average order value.

**4. Time-series trends**
Daily sessions, users, revenue, and conversion rate; hourly traffic and conversion patterns to reveal peak windows.

**5. KPIs and insights**
Overall conversion rate, AOV, bounce rate, average session duration, stage-to-stage conversion, revenue per session at each stage, and automatically generated recommendations naming the biggest drop-off point and best-performing segments.

**6. Reporting**
Exports every analysis table to a multi-sheet Excel workbook and saves charts as high-resolution PNGs.

---

## Tech Stack

- **Python 3.9+**
- **pandas** — data manipulation and aggregation
- **matplotlib** / **seaborn** — visualization
- **openpyxl** — Excel export
- **Jupyter Notebook** — analysis environment

---

## Project Structure

```
.
├── data/
│   └── funnel_analysis_data.csv          # raw dataset (or download instructions)
├── notebooks/
│   └── funnel_analysis.ipynb         # main analysis notebook
├── outputs/
│   ├── funnel_analysis_report.xlsx   # multi-sheet Excel report
│   └── funnel_conversion_rates.png   # saved charts
├── requirements.txt
└── README.md



