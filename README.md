# Global Transmission Project Pipeline Dashboard:-

## 1\. Executive Summary

This Power BI dashboard analyzes the global high-voltage power transmission market using project-level data spanning **2025 to 2034**. The primary objective was to transform complex, multi-layered raw data into a clean, interactive tool focused on **market leadership, financial viability, and project delivery trends.**

The final dashboard is presented across three interconnected pages, designed with a consistent **Red, Green, Blue** theme for maximum executive clarity.

## 2\. Data Modeling & Methodology

The data required significant cleaning due to sparsity (missing data) and structural issues (wide columns containing multiple metrics).

### Key Modeling Decisions (Power Query):

  * **Ranking Integrity:** Preserved **`Developer_1`** and **`Contactor_1`** as the primary keys for all Top 10 ranking charts. Redundant source columns (e.g., `Developer_2` to `5`) were removed.
  * **Analytical Separation (Unpivot):** **Interconnector Lengths** were isolated and unpivoted into a separate **`Interconnector Lengths`** table. This mandatory step allows for accurate summation and filtering of cross-border line lengths.
  * **Metric Extraction:** Cleaned and extracted numerical values for **Voltage** (`Final Voltage (kV)`), removed ambiguous general length columns, and focused on component lengths (`Length (km) - OHL`, etc.).
  * **Time Dimension:** The **Project Completion Forecast** line chart was stabilized by setting the X-axis type to **Categorical** in Power BI, using the clean year number for accurate trending.

### Key Performance Indicators (DAX):

| KPI | Measure | Use Case |
| :--- | :--- | :--- |
| **Total Estimated Investment** | `[Total Cost (BUSD)]` | Primary financial metric. |
| **Total Calculated Length** | `[Total Length (km) - OHL]` | Physical scale of the portfolio. |
| **Total Interconnector Length** | `SUM('Interconnector Lengths'[Interconnector Length (km)])` | Cross-border activity and scale. |
| **Efficiency Benchmark** | `[Avg Cost per KM (MUSD)]` | Project efficiency metric scaled to Millions USD/km. |

## 3\. Dashboard Structure & Screenshots

The layout follows the standard executive flow: Overview $\rightarrow$ Technical Detail $\rightarrow$ Financial Action.

### Page 1: Status & Market Trend

**Title:** Global Transmission Project Pipeline: Status & Market Trend

  * **Focus:** Immediate market health, geographic activity, and investment direction.
  * **Key Visuals:** Global Project Volume Map (colored by **Region**), Pipeline Status Bar Chart (colored by **Status**), Investment Split Donut Chart (HVDC vs. AC).

    ![Page 1: Status & Market Trend](<https://github.com/Ansu0612/Infrastructure-Assignment/blob/main/Page%201.png>)

### Page 2: Technical Feasibility & Project Delivery Forecast

**Title:** Technical Feasibility & Project Delivery Forecast

  * **Focus:** Project scale, infrastructure type, and future delivery timeline.
  * **Key Visuals:** Project Completion Forecast (Line Chart), Line Type Breakdown (Stacked Bar), Voltage Capacity Distribution.

    ![Page 2: Technical Feasibility](<[Link_to_your_GitHub_Screenshot_005026.jpg](https://github.com/Ansu0612/Infrastructure-Assignment/blob/main/Page%203.png)>)

### Page 3: Market Leadership & Project Financing Breakdown

**Title:** Market Leadership & Project Financing Breakdown

  * **Focus:** Identifying key companies and analyzing capital sources.
  * **Key Visuals:** Top 10 Developer Ranking, Top 10 Contractor Ranking, Funding Breakdown by Primary Agent (BUSD).

    ![Page 3: Stakeholder & Finance Breakdown](<https://github.com/Ansu0612/Infrastructure-Assignment/blob/main/Page%204.png>)



