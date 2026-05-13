
# Demand Management - Resource Utilization Project

## Project Overview
This project involves the automated processing and reshaping of multi-sheet employee resource data from Excel. The primary goal is to calculate key performance indicators (KPIs) for resource management across different regions and departments.

## Data Pipeline
The notebook executes the following steps:
1. **Data Loading**: Imports an 8-sheet Excel workbook containing raw demand data.
2. **Cleaning**: Removes header overhead (first two rows) and handles unstructured layouts.
3. **Extraction**: Iterates through the sheets to identify unique employee records (`EMP_xxxx`) and their corresponding:
   - **Contracted Hours**: The total capacity assigned to an employee.
   - **Allocated Hours**: The total workload currently assigned.
4. **Transformation**: Calculates derived metrics:
   - `Total Remaining Capacity` = Contracted Hours - Allocated Hours
   - `Average Utilization Rate` = (Allocated / Contracted) * 100
5. **Export**: Generates structured Excel files for each region/sheet (e.g., `central_usa_df.xlsx`, `Lat_pa_df.xlsx`, `af_df.xlsx`, etc.).

## Calculated Metrics
| Metric | Description |
| :--- | :--- |
| **Employee Code** | Unique identifier for each staff member. |
| **Total Contracted Hours** | Sum of baseline hours available per period. |
| **Total Allocated Hours** | Sum of hours committed to specific tasks. |
| **Total Remaining Capacity** | Surplus or deficit of available time. |
| **Average Utilization %** | Efficiency ratio of work vs. capacity. |

## Dependencies
- Python 3.x
- Pandas
- NumPy
- Matplotlib / Seaborn (for EDA)
- Openpyxl (for Excel I/O)

## Usage
Run the notebook cells sequentially to process the `Case 3 - Demand Management.xlsx` file. The output files will be generated in the local directory for downstream reporting.
```
