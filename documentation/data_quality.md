# Data Quality

## Dataset

The Power BI project uses the `superstore.csv` dataset.

- 1,530 rows
- 21 columns
- Sales transaction data
- Customer, product, geographic, order, and shipping information

## Data Quality Checks

### Missing Values

No missing values were identified in the dataset.

### Duplicate Records

No duplicate rows were identified in the dataset.

### Data Types

Main columns were assigned appropriate data types:

- Order Date → Date
- Ship Date → Date
- Sales → Decimal Number
- Profit → Decimal Number
- Discount → Decimal Number
- Quantity → Whole Number
- Postal Code → Text
- IDs and descriptive fields → Text

### Text Cleaning

Relevant text fields were cleaned in Power Query using:

- Remove Spaces
- Clean

### Dimension Tables

The model includes:

- `FactSales`
- `DimProduct`
- `DimCustomer`
- `DimDate`

### DimProduct Validation

- 29 Product IDs
- 29 unique Product IDs
- 29 unique Product Names
- 3 Categories
- 15 Sub-Categories

### DimCustomer Validation

- 120 Customer IDs
- 120 unique Customer IDs
- 3 Segments
- 1 Country
- 20 Cities
- 16 States
- 4 Regions

### DimDate Validation

- 1,454 dates
- Unique dates
- Years 2022–2025
- 4 quarters
- 12 months
- 48 Year-Month values

## Data Model

The final model follows a star-schema structure.

Relationships:

- `DimProduct[Product ID]` 1 → * `FactSales[Product ID]`
- `DimCustomer[Customer ID]` 1 → * `FactSales[Customer ID]`
- `DimDate[Date]` 1 → * `FactSales[Order Date]`

All relationships are active with one-to-many cardinality and single-direction filtering.
