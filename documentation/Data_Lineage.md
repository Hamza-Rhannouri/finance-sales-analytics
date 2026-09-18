# Data Lineage

```text
Dirty CSV
   ↓
Excel / Power Query
   ├─ standardize text
   ├─ combine names
   ├─ correct country/city mismatches
   ├─ remove redundant Quantity
   ├─ reconstruct Revenue
   ├─ reconstruct Profit
   └─ impute missing cost/shipping values by Product + Country
   ↓
Clean CSV
   ↓
Power BI
   ├─ star schema
   ├─ DAX measures
   ├─ visual analysis
   └─ executive recommendations
```

The raw CSV is retained separately from the processed CSV to preserve traceability.
