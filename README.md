# RDAMP-Sales-Analysis
**Analyst**: Tongai Zinaka
**Tools Used**: Power BI (DAX, Power Query), Excel 
**Dataset**: Ace Superstore Retail and Store Locations Dataset

# Key Insights
## 1. Regional Performance Contrast. 
![image](https://github.com/user-attachments/assets/2f6903f6-e003-490f-b207-237b26d2a39c)
- **Top Performer**: East Midlands (£498K revenue, 18 762 quantity sold)
- **Significant Gap**: North East has the highest discounts (16.66%) but the lowest revenue at (£30.5K)
- **Possible Action**: Launch targeted promotions in the North East with product bundles.

## 2. Sales Distribution: Online vs In-Store
-![image](https://github.com/user-attachments/assets/8bf05501-5dd6-41c2-876c-77f6ac6de904)
- **Near-even Split**: Online (51.5%) compared to In-Store (48.5%)
- **Opportunity**: Push In-Store growth with exclusive in-person offers.

## 3. Product Optimisation Opportunities
-![image](https://github.com/user-attachments/assets/9ea369d6-403c-40da-88a5-064c4c658adb)
- **Expand**: Portable Solar Generators ($44K revenue)
- **Discontinue**: Bottom 5 products (combined revenue is less than £46)

# Recommendations  
1. **Regional Strategy**: Enhance North East presence through localised promotions.  
2. **Product Portfolio**: Discontinue low-revenue items; scale high-margin electronics.  
3. **Channel Mix**: Introduce in-person exclusive bundles to increase the physical share. 
    
## Data Cleaning & Quality Assurance 
![Discount](https://github.com/user-attachments/assets/10a2e34c-9b31-4666-b219-33128685ee96)
![Category](https://github.com/user-attachments/assets/957384fa-da07-4fb7-99db-f62abf732185)
![Country](https://github.com/user-attachments/assets/3628a253-9c7b-4420-a4c9-90df9a175355)
![Region](https://github.com/user-attachments/assets/015312e0-eb66-4e21-b93e-391bebcec9ac)

1. **Handling Missing Values**:  
   - **Discount**: 8% of records had null discounts → Replaced with 0% (`Table.ReplaceValue(null, 0)`)  
   - **Category**: 2% of products had missing categories → Flagged as "Unknown" for review  
   - **Region/Country**: Records had missing geo-data → Resolved via:  
     - Merging with `Store_Locations.xlsx` using Postal Code in Power Query

2. **Anomaly Correction**:  
   - Capped discounts >100% at 100%  
   - Corrected inconsistent region names (e.g., "Yorkshire & the Humber" standardization)  

3. **Data Quality Flags**:  
   - Created `Needs Review` column for:  
     - Products with "Unknown" category  
   - *Impact*: 198 records flagged for business review 
