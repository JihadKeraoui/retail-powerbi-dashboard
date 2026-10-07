# DAX Measures

This document lists the main DAX measures used in the Power BI dashboard.

## 1. Total Sales
```DAX
Total Sales =
SUM(FactSales[Sales])
```

## 2. Total Profit
```DAX
Total Profit =
SUM(FactSales[Profit])
```

## 3. Total Quantity
```DAX
Total Quantity =
SUM(FactSales[Quantity])
```

## 4. Total Orders
```DAX
Total Orders =
DISTINCTCOUNT(FactSales[Order ID])
```

## 5. Average Order Value
```DAX
Average Order Value =
DIVIDE(
    [Total Sales],
    [Total Orders]
)
```

## 6. Profit Margin %
```DAX
Profit Margin % =
DIVIDE(
    [Total Profit],
    [Total Sales]
)
```

## 7. Average Quantity per Order
```DAX
Average Quantity per Order =
DIVIDE(
    [Total Quantity],
    [Total Orders]
)
```

## 8. Sales YTD
```DAX
Sales YTD =
TOTALYTD(
    [Total Sales],
    DimDate[Date]
)
```

## 9. Sales Previous Year
```DAX
Sales Previous Year =
CALCULATE(
    [Total Sales],
    SAMEPERIODLASTYEAR(DimDate[Date])
)
```

## 10. Sales YoY %
```DAX
Sales YoY % =
DIVIDE(
    [Total Sales] - [Sales Previous Year],
    [Sales Previous Year]
)
```

## Summary

These measures support revenue, profitability, order, product, customer, geographic, and time-trend analyses.
