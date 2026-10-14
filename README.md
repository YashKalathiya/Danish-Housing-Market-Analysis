# Danish Housing Market Analysis — Power BI Dashboard

An interactive **Power BI report** exploring housing transactions in Denmark. The project combines housing transaction data with macroeconomic indicators to examine sales trends, property types, regional differences, and the relationship between offer prices and purchase prices.

## Project Overview

This project is designed to help explore questions such as:

- How have housing sales changed over time and across sales types?
- How do offer prices compare with final purchase prices?
- How do sales and average price per square metre vary by region?
- How do average offer and purchase prices differ by property type?
- How do interest rates, inflation, and mortgage-bond yields vary alongside housing indicators?
- How do results change when filtering by area in the report?

The report is intended for descriptive analysis and exploration. Patterns in the dashboard do not establish causation or provide a guarantee of future market performance.

## Power BI Report Pages

The PBIX file contains three report pages.

### 1. House Market Overview

Provides a high-level view of market activity, including:
- Year-over-year sales growth by sales type
- Offer price versus purchase price
- Units sold in the latest year and quarter
- Sales over a 12-month period
- Additional overview visuals

### 2. Sales Performance

Explores geographical and transaction performance, including:
- Sales by region
- Average price per square metre by region
- Offer-to-square-metre ratio by sales type
- Key-driver analysis and a supporting detail table

### 3. House Type Analysis

Compares property types and market indicators, including:
- Average offer price versus purchase price by house type
- Inflation, interest rate, and mortgage-bond yield indicators by house type
- Average property area (`sqm`) and price per square metre
- Area slicers for interactive filtering

Open `PowerBi Report.pbix` in Power BI Desktop to interact with the complete report. Visual titles and available interactions are defined in the PBIX file.

## Files in This Repository

| File | Description |
|---|---|
| `PowerBi Report.pbix` | Power BI report containing the visuals, report pages, and model configuration |
| `Housing_Data.csv` | Main housing transaction dataset |
| `Housing+Data+Column+Definitions.xlsx` | Data dictionary describing the fields in the CSV |
| `README.md` | Project documentation |

## Dataset

### `Housing_Data.csv`

The supplied CSV contains **100,000 rows and 19 columns**, with transaction dates ranging from **January 1992 to October 2024**.

| Column | Description |
|---|---|
| `date` | Date the transaction or record was recorded |
| `quarter` | Quarter associated with the transaction, such as `2024Q4` |
| `house_id` | Identifier for a house/transaction record |
| `house_type` | Property type, such as Apartment, Farm, Summerhouse, Townhouse, or Villa |
| `sales_type` | Type of sale, such as regular sale, auction, family sale, or other sale |
| `year_build` | Year the property was built |
| `purchase_price` | Recorded purchase price |
| `%_change_between_offer_and_purchase` | Percentage change between offer and purchase price |
| `no_rooms` | Number of rooms |
| `sqm` | Property area in square metres |
| `sqm_price` | Price per square metre |
| `address` | Property street address |
| `zip_code` | Property postal code |
| `city` | City/locality of the property |
| `area` | Area or district associated with the property |
| `region` | Broader region category |
| `nom_interest_rate%` | Nominal mortgage interest rate, expressed as a percentage |
| `dk_ann_infl_rate%` | Annual inflation rate in Denmark, expressed as a percentage |
| `yield_on_mortgage_credit_bonds%` | Yield on mortgage-credit bonds, expressed as a percentage |

### `Housing+Data+Column+Definitions.xlsx`

This workbook provides a definition for each of the 19 dataset columns. Use it alongside the CSV when interpreting fields and validating calculations.

### Data-quality notes

- The supplied CSV has **11 blank values** in `city`.
- The macroeconomic columns `dk_ann_infl_rate%` and `yield_on_mortgage_credit_bonds%` each have **77 blank values**. Review the intended handling of these blanks before using the fields in calculations.
- The sample `date` values use a month/day/year style (for example, `10/24/2024`). Confirm the locale and data type in Power BI when importing or refreshing the CSV.
- Treat `house_id` as an identifier, not a measure to sum. Confirm its uniqueness and intended meaning before using it as a transaction count.

## Tools and Technologies

- **Microsoft Power BI Desktop** — dashboard design and interactive reporting
- **CSV** — housing transaction data
- **Microsoft Excel (`.xlsx`)** — column definitions/data dictionary

## Getting Started

1. Clone or download this repository.
2. Open `PowerBi Report.pbix` in **Microsoft Power BI Desktop**.
3. If Power BI cannot locate the source data, update the source path to the local `Housing_Data.csv` file.
4. Use **Transform data** or **Data source settings** to review the CSV path, locale, and data types.
5. Apply changes and refresh the report.
6. Navigate between **House Market Overview**, **Sales Performance**, and **House Type Analysis**. Use the available slicers and visual interactions to explore the data.

Power BI menu names may differ slightly between versions. The column-definitions workbook is a reference document and may not be connected to the report's data model.

## Suggested Repository Structure

```text
.
├── PowerBi Report.pbix
├── Housing_Data.csv
├── Housing+Data+Column+Definitions.xlsx
├── README.md
└── images/
    └── dashboard-preview.png
```

The `images/` folder is optional. Add a screenshot named `dashboard-preview.png` and uncomment the preview section below if you want the dashboard to appear on the GitHub repository page.

<!--
## Dashboard Preview

![Housing Market Dashboard](images/dashboard-preview.png)
-->

## Notes and Limitations

- Dashboard results depend on the measures, transformations, filters, and data types configured in the PBIX file.
- Validate the definitions and calculation logic for year-over-year growth, 12-month sales, offer-to-purchase changes, and price-per-square-metre metrics before using them for formal reporting.
- Macroeconomic indicators may be missing for some records; check whether the blanks reflect source availability, join logic, or data preparation.
- The dataset contains property addresses and postal codes. **Before publishing the CSV publicly, confirm that you have the right to share location-level transaction data** and remove or generalize fields if required.
- This project is for exploratory analysis and should not be treated as professional real-estate, investment, or financial advice.

## Potential Improvements

- Add a screenshot or GIF of the dashboard.
- Document key DAX measures and Power Query transformations.
- Explain the calculation logic for the sales-growth and price metrics.
- Add a short methodology section describing cleaning, missing-value handling, and date parsing.
- Include a section describing the source and update frequency of the housing and macroeconomic data.
