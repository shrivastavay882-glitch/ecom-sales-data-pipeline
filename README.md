# ecom-sales-data-pipeline


Project Overview

Faced with a fragmented dataset containing 20,000 records, I built an end-to-end data pipeline. I leveraged Python for programmatic data cleaning, established an in-memory SQL database engine to run business logic aggregations, and engineered a data model inside Power BI using explicit DAX calculations to deploy an interactive Executive Performance Dashboard.

Dashboard Visual Preview


Repository Architecture

• notebooks/retail_sales_analysis.ipynb: Python data cleaning and verification scripts.

Data Pipeline Phases


Phase 1: Automated Data Engineering (Python)

Instead of manual validation, I engineered a reproducible cleaning script. The pipeline normalized date formats, removed duplicate entries, and dropped missing rows to isolate 19,965 verified records. I used case formatting and typo dictionary mapping to permanently merge variations in brands and categories. Additionally, I applied boundary profiling to discover a 500-unit transactional bulk-order outlier, validating it as a legitimate B2B corporate purchase rather than a human typo.

Phase 2: Relational Data Aggregations (SQL)

I migrated the clean schema into an in-memory database to run performance queries. I built case-insensitive conditional filters to calculate exact product return rates across categories, identifying which sectors hold the highest operational risk. I also evaluated order weights and Average Order Value metrics across checkout channels to spot consumer purchasing thresholds.

Phase 3: Interactive Visualization (Power BI & DAX)

I imported the clean dataset into Power BI and locked down the calculations using explicit DAX measures, avoiding standard default metric errors. This includes building a safe-fail return rate metric to handle missing targets cleanly. The final report features an structured dashboard layout dividing top-level KPI summary cards from brand revenue leaderboards, category risk vertical bars, payment method matrices, and an interactive city filter tool.
