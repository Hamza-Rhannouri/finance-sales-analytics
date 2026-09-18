# Excel / Power Query Cleaning Logic

## Source
The project began from a deliberately messy finance/sales CSV. The raw file is preserved under `data/raw/` and is never overwritten.

## Cleaning performed
1. Standardized misspellings in `Sales_channel`, `Salesperson`, `product-name`, `product-category`, and `city`.
2. Combined `first_name` and `last_name` into `Full_name`, then removed the redundant source columns.
3. Reconciled city/country inconsistencies using an explicit business rule for the six-country dataset:
   - Germany → Berlin
   - Morocco → Casablanca
   - France → Paris
   - Spain → Madrid
   - USA → New York
   - UAE → Dubai
4. Removed `Quantity` because it duplicated `Sales` and therefore added no analytical information.
5. Reconstructed missing Revenue with:

   `Revenue = Price × (1 − Discount) × Sales`

6. Reconstructed missing Profit with:

   `Profit = Revenue − (Cost of Product × Sales) − Taxes − Shipping`

7. Missing cost-of-production and shipping values were imputed using averages aligned to Product Name + Country.

## Power Query M rule used for city standardization
```powerquery
if [country] = "Germany" and [City] <> "Berlin" then "Berlin"
else if [country] = "Morocco" and [City] <> "Casablanca" then "Casablanca"
else if [country] = "France" and [City] <> "Paris" then "Paris"
else if [country] = "Spain" and [City] <> "Madrid" then "Madrid"
else if [country] = "USA" and [City] <> "New York" then "New York"
else if [country] = "UAE" and [City] <> "Dubai" then "Dubai"
else [City]
```

> Note: the exact original Excel workbook was not supplied as a separate `.xlsx` file in this package. This document preserves the cleaning methodology and M logic you described. If the workbook is later provided, it can be added without changing the project structure.
