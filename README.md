# SCMS Supplier Delivery Analysis

## Summary
[problem, method, insight, rec, limit]

## Charts
![Late rate by supplier](images/chart1_late_rate.png)
![Spend at risk](images/chart2_spend_risk.png)

## Cleaning log
1. Dates converted from text (d-Mon-yy, two-digit years); 0 failed in both columns.
2. Freight Cost (USD) left out: 4,126 text entries (40%), e.g. "Freight Included in Commodity Cost" (1,442).
3. Outliers found: 224 lines more than 90 days early (min -372), 40 more than 90 days late (max 192). Decision: keep. Early lines count as on time either way, and late days are reported with the median.
4. SCMS from RDC (5,404 lines) separated from suppliers. 

## Checks and limits
- [check line]
- Except for the three large suppliers, rates rest on 1 to 4 late lines.
- Freight cost not analysed (4,126 text entries).
- Data ends in 2015, so findings describe history.

## Files
data/raw and data/clean hold the original and cleaned CSVs; notebooks has the cleaning and analysis; images has the charts.

## Data source
USAID / PEPFAR SCMS Delivery History (Supply Chain Shipment Pricing Data). Copy from GitHub repo MatheusNelvam/DB2-RDF-Project.

## How to rerun
The notebooks read from a Google Drive folder. Upload the files from data/ and change the path.
