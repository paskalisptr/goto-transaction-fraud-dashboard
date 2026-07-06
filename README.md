# GoTo Transaction Analytics Dashboard

A two-page Power BI dashboard analyzing simulated GoTo-style transaction data, covering executive-level revenue monitoring and fraud pattern analysis.

## Overview

This project builds an analytics dashboard for a multi-service digital platform (ride-hailing, food delivery, courier, e-commerce), inspired by real-world case study patterns from a Big Data Management course assignment on transaction monitoring at scale. Since the original case study data was not available for public use, a synthetic dataset of 50,000 transactions was generated in Python to match the statistical patterns described in that case (daily volume, fraud rate, amount distribution, service mix).

## Dashboard Pages

**Page 1: GoTo Transaction Monitoring** (Operations & Fraud Overview)
- KPI cards: 50K total transactions, Rp3.77bn total revenue, 1.88% fraud rate, Rp75.47K average transaction value
- Daily transaction volume trend across January 2024 (line chart)
- Revenue by service type: gosend, goride, tokopedia, gocar, gofood are within a narrow Rp0.75bn-0.76bn range, showing an even distribution of revenue across services (bar chart)
- Transaction share by service type, each service holding roughly 20% of volume (donut chart)

![Transaction Monitoring Dashboard](screenshots/transaction_monitoring.png)

**Page 2: Fraud Detection Analysis** (Fraud & Data Quality Monitoring)
- Fraud rate by service type, ranging from 1.74% (goride) to 2.05% (gofood)
- Daily fraud rate trend, fluctuating between roughly 1.3% and 2.8% across the month
- KPI cards: 969 outliers flagged, 1.94% outlier rate, 50K total transactions
- Top 10 users by transaction count and revenue (table), led by user 22013 with 7 transactions totaling Rp526,056.67

![Fraud Detection Dashboard](screenshots/fraud_detection.png)

## Dataset

- `goto_transactions_v2.csv`: 50,000 synthetic transaction records
- Fields include: transaction ID, user ID, service type (GoRide, GoCar, GoFood, GoSend, Tokopedia-style e-commerce), amount, fraud flag, timestamp
- Generated in Python to reflect realistic daily volume, ~2% fraud rate, and amount distributions consistent with the reference case study
- Note: this is fully synthetic data, not real GoTo transaction data. It was built for portfolio and learning purposes only.

## Tools

- Python (dataset generation)
- Power BI Desktop (data modeling, DAX measures, visualization)

## Key Data Handling Notes

- CSV formatted with semicolon separators and comma decimals to avoid numeric misreads on import
- `user_id` cast to Text type in Power Query since it is used as a dimension, not a measure

## Files

- `porto_goto_transac.pbix`: Power BI project file
- `goto_transactions_v2.csv`: source dataset
- `screenshots/`: exported PNG views of both dashboard pages

## Author

Paskalis Peter — Data Science student, built as part of a self-driven portfolio project for Data Analyst / BI internship applications.
