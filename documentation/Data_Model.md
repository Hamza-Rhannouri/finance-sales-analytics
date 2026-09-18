# Data Model

The cleaned dataset is modeled in Power BI using a star-schema approach.

## Fact table
- Order_ID
- Sales
- Revenue
- Profit
- Taxes
- Price
- Cost of Product
- Discounts
- Shipping Cost
- ProductID
- GeoID
- PayID
- Date

## Dimensions
### CustomerDim
Customer_ID, Customer_Full_Name

### ProductDim
ProductID, Product_Category, Product_Name

### GeoDim
GeoID, Country, City

### PaymentProcessDim
PayID, Payment_Method, Sales_Channel, Salesperson, Currency

### DateDim
Date, Month, Year

The project covers six country/city pairs: Morocco/Rabat, Spain/Madrid, Germany/Berlin, USA/New York, UAE/Dubai, and France/Paris.
