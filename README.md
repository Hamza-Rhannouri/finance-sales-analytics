# Finance Sales & Profitability Analysis — Excel + Power BI

## Project overview
An end-to-end finance analytics project built from a deliberately messy sales dataset. The workflow covers data quality remediation in Excel/Power Query, financial calculation logic, star-schema modeling, DAX measures, and Power BI storytelling.

## Workflow
`Raw CSV → Excel/Power Query → Clean Dataset → Star Schema → DAX → Power BI Dashboard → Business Insights`

## Repository structure
- `data/raw/` — original dirty dataset
- `data/clean/` — cleaned dataset
- `excel/` — cleaning methodology and Power Query logic
- `powerbi/` — Power BI report and dashboard screenshots
- `documentation/` — model, lineage and financial logic
- `audit/` — technical review and improvement notes
- `portfolio/` — recruiter-facing project description

## Core transformations
- Standardized inconsistent text values.
- Combined first and last names into a single customer name field.
- Reconciled country/city inconsistencies.
- Removed redundant Quantity.
- Reconstructed Revenue and Profit using financial formulas.
- Imputed missing cost and shipping values using Product + Country averages.

## Model
A star schema was used with a central fact table and Customer, Product, Geography, Payment/Process and Date dimensions.

## Financial logic
Revenue, Profit, Margin, Gross Profit and Gross Profit Margin were implemented using the documented business formulas.

## Dashboard
The Power BI report contains four pages designed to move from performance overview to driver analysis and executive recommendations.

## Data provenance
The datasets are synthetic and were created specifically for portfolio practice; no confidential company data is used.
