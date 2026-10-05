# Last-Mile Operations Analytics

## Project overview

This project analyzes last-mile delivery operations in Excel using seven source files covering orders, payments, deliveries, stores, channels, drivers and hubs.

The main goal was to understand order volume, completion, order value, delivery cycle time and operational data quality while keeping the analysis at one row per order.

## Tools used

- Microsoft Excel
- Power Query workflow and M code
- PivotTable-style summary analysis
- Data validation and QA checks
- Dashboard design

## Dataset

Public dataset: *Delivery Center: Food & Goods orders in Brazil*

The analysis, data preparation workflow, KPI design and dashboard were created by Muhammad Rizwan.

The analysis covers 368,999 orders from January to April 2021.

The source data includes:

- Orders
- Payments
- Deliveries
- Stores
- Channels
- Drivers
- Hubs

## Data preparation

A major part of the project was protecting the grain of the Orders table.

Two source tables required special handling:

- **Payments:** some orders had multiple payment rows, so payments were aggregated to one row per `payment_order_id` before joining.
- **Deliveries:** some orders had multiple delivery attempts, so a repeatable final-attempt rule was applied before joining to Orders.

I also checked duplicate keys, unmatched joins, negative duration values and extreme cycle-time records before using the results in the dashboard.

## KEY KPIs

| KPI | Result |
| --- | ---: |
| Total Orders | 368,999 |
| Completion Rate | 95.4% |
| Finished Order Value | R$ 35.29M |
| Average Order Value | R$ 100.26 |
| Median Cycle Time | 42.18 min |
| P90 Cycle Time | 83.17 min |
| Average Delivered Distance | 10.11 km |
| Unmatched Payment Rate | 5.1% |

## Dashboard

![Last-Mile Operations Dashboard](dashboard.png)

The dashboard focuses on:

- Monthly order volume
- Channel concentration
- Hourly demand patterns
- Store-segment order mix
- Delivery-cycle performance
- Payment coverage

## Key findings

- 352,020 of 368,999 orders were completed, resulting in a 95.4% completion rate.
- March recorded the highest monthly order volume with 112,223 orders, followed closely by April.
- FOOD PLACE was the dominant ordering channel, contributing substantially more orders than any other channel.
- Order demand showed clear time-of-day patterns, with major peaks around 15:00 and 22:00.
- FOOD stores generated the vast majority of orders compared with the GOOD store segment.
- Median delivery cycle time was 42.18 minutes, while the P90 cycle time reached 83.17 minutes, indicating that the slowest 10% of orders took considerably longer to complete.
- Average delivered distance was 10.11 km.
- 18,665 orders had no matching payment record, representing approximately 5.1% of all orders.
- 10,345 orders had no matching delivery record. These unmatched records were retained as missing values rather than incorrectly treating them as zero.

## Workbook structure

The Excel workbook includes:

- Project overview
- Source audit
- Data dictionary
- Power Query build steps
- M code library
- Model design
- Fact-table sample
- KPI definitions
- Report build steps
- Validated summary tables
- Dashboard
- Key findings
- QA checklist
- Modeling notes

## Portfolio note

This repository contains a compact portfolio workbook. The full seven-file dataset was analyzed, but external CSV connections are not embedded in the shared workbook. The transformation workflow and M code are documented inside the workbook, and the dashboard uses validated full-data summary outputs.

## Author

**Muhammad Rizwan**  
Data Analyst Portfolio Project
