# Bank of America Customer Complaint Analysis (2017-2023)

## Overview
This project analyzes customer complaints submitted to Bank of America (BoA) between 2017 and 2023. Using Power BI, the analysis provides insights into complaint trends, response efficiency, and customer locations to help BoA improve its customer service strategies. Additional data preparation and analysis were conducted in Excel.

## Objective
The main objective is to identify patterns in customer complaints, assess BoA's response timeliness and effectiveness, and provide actionable recommendations for addressing customer issues more efficiently.

---

## Project Workflow

### Data Preparation and Cleaning
1. **Handling Missing Values**:
   - **Timely Response**: Replaced blank cells with "Unknown."
   - **Sub-Issue**: Filled empty cells with corresponding values from the `Issues` column for consistency.

2. **External Data Integration**:
   - Imported a list of U.S. states from Wikipedia to map customer complaint locations and enable regional analysis.

3. **Company Response Data**:
   - Compared the `Company Public Response` and `Company Response to Consumer` columns. Populated blank cells with responses from `Company Public Response` where available, and used "No response yet" for remaining blanks.

4. **Resolution Time Calculation**:
   - Created a `Resolution Time` column to calculate the difference in days between `Date Received` and `Date Submitted`.

5. **Response Status Classification**:
   - Created a `Response Status` column using DAX to classify responses as "Early" (resolved within 3 days) or "Late" (more than 3 days).

### Analysis
The analysis focused on understanding complaint types, response timeliness, and geographic distribution of customers. Visualizations were created in Power BI to communicate key insights effectively.

---

## Key Findings

1. **Complaint Overview**:
   - **Total Complaints**: 62,516
   - **Yearly Trends**: The highest number of complaints was in 2022, with 12,936 complaints, dropping to 9,176 in 2023.

2. **Product and Issue Breakdown**:
   - **Top Complained Product**: Checking or Savings Account, with 24,814 complaints.
   - **Most Common Issue**: "Managing an Account," cited in 15,109 complaints.

3. **Response Timeliness**:
   - **Early Responses**: 92.88% of complaints received a timely response.
   - **Late Responses**: 7.12% received a delayed response.

4. **Submission Channels**:
   - **Most Used Channel**: Web platform, accounting for 45,423 complaints submitted online.

5. **Geographic Distribution**:
   - A map visualization shows the geographic distribution of complaints, providing insights into regions with the highest customer dissatisfaction levels.

---

## Recommendations

Based on the findings, the following recommendations could help BoA enhance its customer service:
- **Optimize Support for High-Complaint Products**: Improve service for checking and savings accounts, as these products generated the most complaints.
- **Enhance Account Management Support**: Streamline account management processes to address the top issue reported by customers.
- **Focus on Timely Resolutions**: Although most responses are timely, BoA should aim to further reduce the percentage of late responses.
- **Improve Web Platform Usability**: Given the high volume of online submissions, enhancing the web platform experience could improve customer satisfaction.

---

## Dataset Limitations

- **Data Completeness**: Some records contained blank values that were filled based on available data, which could slightly impact accuracy.
- **Resolution Time Precision**: Calculated in days, so more granular timing data (hours/minutes) is not available.
- **Lack of Demographic Data**: Customer demographic data was unavailable, limiting insights into complaint trends by demographic groups.

---

## Dashboard and Visuals

### Power BI Dashboard
This project includes a Power BI dashboard with the following key visuals:
- **Complaint Trends**: Yearly trends and product breakdown to highlight significant patterns.
- **Response Timeliness**: A breakdown of early vs. late responses.
- **Submission Channel Distribution**: Analysis of submission methods, showing customer preferences.
- **Customer Location Map**: A map visualization showing the geographic distribution of complaints across U.S. states.

### Visuals
Power BI visuals provide a clear, interactive view of:
- Total complaints and trends over time.
- Top products and issues.
- Timeliness of responses.
- Regional distribution of complaints on a U.S. map.

---

## DAX Formula for Response Status Classification

To classify responses as "Early" or "Late" based on resolution time, the following DAX formula was used in Power BI:

```DAX
ResponseStatus = IF([Resolution Time (in days)] <= 3, "Early", "Late")
```

- **Early**: Responses resolved within 3 days.
- **Late**: Responses taking more than 3 days.

This classification supports analysis of BoA's response efficiency, highlighting areas for potential improvement.

---

## How to Use This Repository

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/godwinogele/BoA-Customer-Complaint-Analysis.git
   ```
   
2. **Data and Power BI File**: The dataset (`complaints_data.xlsx`) and Power BI file (`BoA_Complaint_Dashboard.pbix`) are included in the repository.

3. **Explore the Dashboard**: Open the Power BI file to interact with the dashboard and analyze trends, response times, and geographic distributions.

---

## Future Enhancements

- **Demographic Analysis**: Adding demographic data could reveal insights into customer satisfaction across different groups.
- **Sentiment Analysis**: Analyzing complaint descriptions for sentiment trends could provide deeper insights.
- **Real-Time Monitoring**: Automating data updates would enable real-time tracking of complaints and response effectiveness.

---

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.

---

Contributions are welcome! Feel free to open pull requests or submit issues to enhance this project.
