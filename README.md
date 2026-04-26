# tableau-factory-downtime-analysis
# Deloitte Australia Data Analytics Job Simulation

## 📌 Project Overview
This project was completed as part of the **Deloitte Australia Data Analytics Virtual Experience**. The simulation involved acting as a Data Analyst to assist **Daikibo**, a global electronics manufacturer, in optimizing their production lines and ensuring workplace equality.

The project is divided into two main workstreams:
1.  **Telemetric Analysis:** Visualizing machine downtime to identify production bottlenecks.
2.  **Equality Analysis:** Processing employee compensation data to monitor corporate fairness.

## 🛠️ Tools Used
* **Tableau:** For interactive dashboarding and data visualization.
* **Microsoft Excel:** For data transformation and logical categorization.
* **JSON:** Handling and structuring raw telemetry data.

---

## 📊 Task 1: Production Line Downtime Analysis
**Objective:** Transform raw JSON telemetry data from four global factories into an interactive dashboard to identify "unhealthy" device statuses.

### Key Actions:
* Parsed complex JSON schemas in Tableau to extract `Status`, `Factory`, and `Device` dimensions.
* Created a **Calculated Field** to quantify downtime: 
    * `IF [Status] = "unhealthy" THEN 10 ELSE 0 END`
* Developed an interactive dashboard allowing users to filter by Factory to see specific device performance.

### Insights:
* Identified **Daikibo-Factory-Seiko** as having the highest cumulative downtime.
* Isolated the **LaserWelder** as the specific device type responsible for the majority of the Seiko factory's production delays.

---

## 📉 Task 2: Employee Equality Categorization
**Objective:** Use Excel logic to classify factory equality scores into actionable categories.

### Key Actions:
* Processed an equality dataset covering various job roles and factories.
* Implemented a **Nested IF formula** to automate the classification of scores:
    * **Fair:** Score within ±10.
    * **Unfair:** Score outside ±10.
    * **Highly Discriminative:** Score outside ±20.

### Formula Used:
```excel
=IF(OR(C2<-20, C2>20), "Highly Discriminative", IF(OR(C2<-10, C2>10), "Unfair", "Fair"))
