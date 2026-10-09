# The Complaint Resolution Bottleneck

## Overview

An exploratory data analysis project using the Consumer Financial Protection Bureau (CFPB) complaint database to examine complaint routing delays and company response timeliness.

## Business Questions

* Does routing time differ across submission channels?
* Which financial products have higher untimely response rates?
* How do response timeliness rates vary across high-volume companies?
* What outcomes are most commonly recorded in the dataset?

## Tools Used

Python, Pandas, NumPy, Matplotlib, Seaborn, Google Colab

## Methodology

* Filtered complaints received between January 2023 and December 2025.
* Checked duplicate complaint IDs, missing values, and date inconsistencies.
* Calculated routing time using the dates received and sent to the company.
* Compared response timeliness across products, channels, and companies.
* Created visualizations to highlight differences in the data.

## Key Findings

See the analysis notebook for the results, comparisons, and visualizations.

## Limitations

Routing time measures the time between complaint receipt and sending the complaint to a company. It does not measure the company's total resolution time or consumer satisfaction. Company comparisons are limited to those meeting the selected minimum complaint volume.

## Files

* `CFPB_Complaint_Analysis.ipynb` — analysis and visualizations
* `cfpb_bottlenecks_clean.png` — summary chart

## Data Source

[CFPB Consumer Complaint Database](https://www.consumerfinance.gov/data-research/consumer-complaints/)
