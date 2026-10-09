# The Complaint Resolution Bottleneck

### Analyzing Consumer Complaint Routing Delays and Response Timeliness

## 1. Overview

Millions of consumer complaints are submitted to the Consumer Financial Protection Bureau (CFPB). However, complaint data can be difficult to interpret without examining patterns across products, submission channels, and companies.

This project analyzes CFPB complaints received between January 2023 and December 2025 to investigate routing delays, untimely response rates, and recorded company response outcomes.

Using Python and exploratory data analysis, the project identifies patterns that may help highlight areas requiring further investigation or process improvement.

## 2. Business Problem

**Where do potential bottlenecks appear in the consumer complaint handling process, and which areas may need closer attention?**

Financial institutions and analysts need visibility into how complaints move through the initial handling process and how recorded response timeliness varies across products and companies.

This project investigates three key areas:

* **Routing delays:** Do some submission channels have longer delays before complaints are sent to companies?
* **Response timeliness:** Which financial products have higher rates of responses marked as untimely?
* **Company comparisons:** Which high-volume companies have comparatively high untimely response rates?

The objective is to identify patterns and potential problem areas that could help stakeholders prioritize further investigation. The analysis does not establish the causes of these patterns or directly resolve complaint-handling issues.

### Who Could Use These Insights?

* **Operations teams** could investigate channels associated with longer routing times.
* **Management and data analysts** could compare response timeliness across products and high-volume companies.
* **Compliance teams** could examine areas with elevated untimely response rates.

These are potential applications of the analysis rather than confirmed outcomes from a real-world business deployment.

## 3. Dataset

**Source:** [CFPB Consumer Complaint Database](https://www.consumerfinance.gov/data-research/consumer-complaints/)

* **Period:** January 1, 2023, to December 31, 2025, based on complaint receipt date.
* **Initial dataset size:** Approximately 9.47 million records retained during data ingestion.
* **Data fields:** Complaint dates, financial products, issues, companies, states, submission channels, response categories, and response timeliness.

The dataset includes complaints received in late 2025 that were sent to companies in 2026. These records are retained because the analysis is based on the complaint receipt date.

## 4. Tools and Technologies

* **Python** — analysis and data processing
* **Pandas** — data cleaning, transformation, and aggregation
* **NumPy** — numerical operations and feature creation
* **Matplotlib and Seaborn** — data visualization
* **Google Colab** — development environment

## 5. Methodology

1. **Data ingestion:** Loaded the large dataset in chunks, selected relevant columns, and filtered records by receipt date.
2. **Data quality audit:** Checked complaint ID uniqueness, missing values, date ranges, and date inconsistencies.
3. **Data cleaning:** Handled missing categorical values and excluded records without a recorded company response.
4. **Feature engineering:** Calculated routing time in calendar days and created fields for untimely responses, monthly trends, and response outcome categories.
5. **Exploratory analysis:** Compared routing times across submission channels and response timeliness across products and companies.
6. **Visualization and validation:** Created charts and checked key metrics for consistency.

## 6. Key Metrics

| Metric                 | Definition                                                               |
| ---------------------- | ------------------------------------------------------------------------ |
| Routing time           | Calendar days between complaint receipt and sending to the company       |
| Untimely response rate | Percentage of records marked `No` in the `Timely response?` field        |
| Same-day routing       | Complaints sent to companies on the same calendar day they were received |
| Long routing delays    | Complaints with routing times greater than seven calendar days           |
| Response outcomes      | Categories based on the recorded company response                        |

## 7. Visualizations

The analysis includes comparisons of:

* Monthly untimely response rates for student loans and other financial products.
* Average routing time across submission channels.
* Untimely response rates among high-volume companies.

<img width="1191" height="1584" alt="cfpb_bottlenecks_clean" src="https://github.com/user-attachments/assets/d7f7dead-3098-46ab-a554-36e1da30bc78" />

## 8. Key Findings

The notebook contains the calculations and detailed results for each analysis.

The main areas investigated are differences in routing time by submission channel, variation in untimely response rates across financial products, company-level comparisons, and the distribution of recorded response outcomes.

For company comparisons, the analysis uses a minimum threshold of 10,000 complaints to focus on high-volume companies and reduce the influence of small sample sizes.

## 9. Limitations

* **Routing time is not resolution time.** The analysis measures the time between complaint receipt and sending to the company, not the time taken to resolve the complaint.
* **Timeliness is based on recorded data.** The project uses the CFPB's `Timely response?` field and does not independently verify each response.
* **Response outcomes do not establish satisfaction.** A recorded response category does not prove that the consumer was satisfied with the result.
* **Company comparisons require context.** Differences in complaint volumes, product mix, and other factors may influence the results. Higher untimely response rates alone do not establish misconduct or explain the cause.
* **Cleaning choices affect the analysis.** Excluding records without a recorded company response may affect the calculated rates.
* **Findings are descriptive.** The analysis identifies patterns and potential areas for investigation; it does not establish causation or prove that a particular operational change would improve outcomes.

## 10. Repository Contents

* `CFPB_Complaint_Analysis.ipynb` — notebook containing the analysis, calculations, and visualizations.
* `cfpb_bottlenecks_clean.png` — summary visualization.

---

*An exploratory data analysis project using publicly available CFPB consumer complaint data for portfolio and learning purposes.*
