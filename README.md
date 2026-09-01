# 🏥 Hospital-Management-Analytics-Dashboard

![Home](https://github.com/shivrajsinghsisodiya9351-alt/Hospital-Management-Analytics-Dashboard/blob/main/Home.png)
| Doctor Page | Patients Page | Finance Page | Stock & Medicines Page |
|---|---|---|---|
| ![Patients](https://github.com/shivrajsinghsisodiya9351-alt/Hospital-Management-Analytics-Dashboard/blob/main/Patient%20Dashboard.png) | ![Doctors](https://github.com/shivrajsinghsisodiya9351-alt/Hospital-Management-Analytics-Dashboard/blob/main/Doctor%20Dashboard.png) | ![Finance](https://github.com/shivrajsinghsisodiya9351-alt/Hospital-Management-Analytics-Dashboard/blob/main/Finance%20Dashboard.png) | ![Stock](https://github.com/shivrajsinghsisodiya9351-alt/Hospital-Management-Analytics-Dashboard/blob/main/Stock%20%26%20Medicine.png) |

> Replace the image paths above with your actual screenshot files placed inside an `assets/` folder in the repo.

---

## 📌 Project Description
The **Hospital Operations Dashboard** is an end-to-end Power BI project built for **City General Hospital**, designed to give management a single, interactive view of hospital performance across **Doctors, Patients, Finance, and Stock & Medicines**. The dashboard consolidates revenue, doctor performance, patient admissions, payment behavior, and inventory movement into one navigable report, enabling faster, data-driven operational decisions.

---

## 🗂️ Tables Used (Data Model)
The report is built on a **star schema** with the following tables:

| Table | Type | Description |
|---|---|---|
| `Patients` | Dimension | Patient master data — name, gender, insurance, symptoms, room no., total bill |
| `Doctors` | Dimension | Doctor master data — name, gender, qualification, specialization |
| `Appointments` | Fact | Appointment records, status, consultant type (Online/Walk-in) |
| `Bills` | Fact | Room, test, medicine, consultation charges |
| `Tests` | Fact | Test-related billing |
| `Medicine_Dispensing` | Fact | Medicine dispensed by day/month, quantity, price |
| `Stock_Management` | Fact | Stock volume, current stock, over/low stock status |
| `Finance_Charges` | Derived (Power Query, unpivoted) | Charge-type breakdown for finance analysis |
| `Calender_table` | Date Dimension | Calendar table used across all DAX time-intelligence measures |
| `Measure_Table` | Measures | Dedicated table holding all DAX measures |

---

## 📊 KPIs Tracked

**Patients Page**
- Total Patients: **5,000**
- Avg. Stay Days: **3.9 Days**
- Admitted Patients: **640**
- Discharged Patients: **2,571**
- Scheduled Patients: **1,474**

**Finance Page**
- Total Revenue: **$52,887,754**
- Avg. Revenue: **10.58K**
- Total Room Charge: **25.33M**
- Total Test Charge: **15.98M**
- Total Medicine Charge: **7.56M**
- Total Consultation Charge: **6M**
- Revenue by Insurance Provider (Not Insured, ICICI Lombard, HDFC Ergo, Star Health)
- Payment Split (Cash, Card, UPI, Insurance)

**Doctor Page**
- Appointments: **7,000**
- Commission Rate: **15%**
- Commission Amount: **7.93M**
- Avg. Fees: **1.20K**
- Avg. Rating: **3.86**

**Stock & Medicines Page**
- Total Stock Volume: **600.7M**
- Total Stock: **986.1K**
- Current Stock: **968.7K**
- Dispensed Stock: **17.4K**
- Dispensed Amount: **4.3M**

---

## ⚙️ Process

1. **Data Collection** — Gathered hospital operational data across patients, doctors, billing, appointments, and stock/medicine dispensing.
2. **Data Preparation** — Structured raw data into fact and dimension tables suitable for a star schema.
3. **Data Cleaning** — Fixed inconsistencies including a Calendar table date-range mismatch that was causing ~21M in revenue to appear as blank/unmapped rows.
4. **Data Modeling** — Built a star schema (patients/doctors as dimensions; appointments, bills, tests, medicine dispensing, stock as facts) with relationships and a dedicated Measure Table for DAX.
5. **Dashboard Development** — Designed 5 pages (Home, Doctor, Patients, Finance, Stock & Medicines) with KPI cards, trend charts, donut/bar visuals, and conditional-formatted tables (SVG pill-badge status tags).
6. **Testing & Deployment** — Validated measures (`SELECTEDVALUE`, `LASTNONBLANKVALUE`), cross-checked KPI totals against source tables, and finalized theme/branding before publishing.

---

## ❓ Business Questions Answered
- What is the total revenue generated, and how does it trend month-over-month?
- Which charge category (Room, Test, Medicine, Consultation) contributes most to revenue?
- How do patients pay — Cash, Card, UPI, or Insurance — and which insurer contributes the most?
- How many patients are admitted, discharged, or scheduled at any given time, and what is the average stay duration?
- Which age group and insurance provider make up the largest share of patients?
- Which doctors and specializations generate the highest billing and commission?
- What is the doctor performance split by consultation type (Online vs Walk-in) and gender?
- Which medicines are dispensed most, and what is the current stock health (in stock / low stock / overstock)?
- How does patient volume and medicine dispensing vary by day of week and month?

---

## 🔍 Observations & Data Highlights
- Total revenue stood at **$52.89M**, up **68.2% MoM** with a swing of **+$21.45M** vs. last month.
- **Room Charges (47.90%)** are the single largest revenue contributor, followed by Test Charges (30.22%).
- **Cash (36.19%)** is the leading payment mode, followed by UPI (22.95%) and Card (28%); Insurance-based payments are comparatively low (12.86%).
- Revenue is highly seasonal — a sharp dip in **June-July** followed by a strong recovery (**+19.4%**) in **August**.
- Of **5,000 total patients**, **2,571 have been discharged**, **640 are currently admitted**, and **1,474 are scheduled**, with an average stay of **3.9 days**.
- Patient insurance coverage is fairly evenly split across **HDFC Ergo, ICICI Lombard, Star Health, and Not Insured** (each roughly 24-26%).
- **Senior Citizens (1,306) and Pediatric patients (1,032)** form the largest age-group segments, ahead of Young Adult and Middle Age groups.
- **ENT** has the highest appointment volume by specialization (900), ahead of Dermatology and Urology.
- Medicine stock shows a healthy split, though a visible **"Over stock" (11.9K)** segment flags potential overstocking risk in specific items.

---

## 📈 Visuals & Analytics Used
- KPI cards for patients, revenue, appointments, commissions, and stock metrics
- Line chart with variance callouts — Revenue by Month
- Column chart — Total Patients by Month, Total Patients by Age Group
- Donut charts — Payment Split, Consultant Type, Doctors by Gender, Insurance by Patients, Medicine Stock Status
- Horizontal bar charts — Appointment by Specialization, Dispensed Qty by Medicine Name/Type
- Matrix/table visuals with conditional formatting (SVG pill badges) — Patients Overview, Doctor Performance, Medicine Status
- Heatmap-style table — Medicine by Day and Month
- Patient/Doctor Information cards with photo, symptom/specialization, gender, age, blood group, and star rating
- Custom Deneb/Vega-Lite visuals and a custom Power BI theme (JSON) for consistent branding
- Interactive month slicers and page navigation buttons across all report pages

---

## 💡 Actionable Insights
- Since Room and Test charges drive ~78% of revenue, pricing or capacity optimization here has outsized financial impact.
- Low insurance-based revenue (12.86%) suggests an opportunity to onboard more insurance tie-ups to reduce cash dependency.
- The June-July revenue dip is a candidate for a seasonal-demand investigation (staffing, promotions, or referral drop-off).
- A high share of Senior Citizen and Pediatric patients points to a need for age-specific staffing and resource planning (geriatric/pediatric wards).
- Overstocked medicine categories should be reviewed to reduce holding costs and avoid expiry-related wastage.
- High-commission, top-performing doctors (flagged "Top perf.") could be leveraged for mentoring or scheduling more Online consultations, which appear to be a growing channel.

---

## 🎯 Expected Outcomes
- Faster, centralized visibility into hospital financial and operational performance for management.
- Reduced manual reporting effort by replacing static spreadsheets with a live, interactive dashboard.
- Better-informed decisions on staffing, insurance partnerships, patient care planning, and inventory management.
- A reusable, scalable star-schema model that can extend to future hospital data sources.

---

## ✅ Conclusion
This project demonstrates a complete Power BI workflow — from raw data modeling to a polished, multi-page, decision-ready dashboard — applied to a real-world hospital operations use case. It combines strong data modeling (star schema, DAX), clean UX (navigation, conditional formatting, custom visuals), and business-focused storytelling (KPIs tied directly to actionable questions) across Patients, Doctors, Finance, and Stock & Medicines.

---

## 📬 Contact Me
**Shivraj Singh Sisodiya**
📍 Jaipur, Rajasthan, India
🌐 Portfolio: [datascienceportfol.io/shivraj](https://datascienceportfol.io/shivraj)
💻 GitHub: [github.com/shivrajsinghsisodiya9351-alt](https://github.com/shivrajsinghsisodiya9351-alt)

---

## 📂 Explore the Full Project
Want to see the complete model, DAX measures, and interactions live? **Download the `.pbix` file** from this repository and open it in **Power BI Desktop** to explore all pages, drill-throughs, and measures in detail.

👉 [Download the .pbix file](# 🏥 Hospital Operations Dashboard — Power BI

![Home](assets/home.png)
| Doctor Page | Patients Page | Finance Page | Stock & Medicines Page |
|---|---|---|---|
| ![Doctor](assets/doctor.png) | ![Patients](assets/patients.png) | ![Finance](assets/finance.png) | ![Stock](assets/stock.png) |

> Replace the image paths above with your actual screenshot files placed inside an `assets/` folder in the repo.

---

## 📌 Project Description
The **Hospital Operations Dashboard** is an end-to-end Power BI project built for **City General Hospital**, designed to give management a single, interactive view of hospital performance across **Doctors, Patients, Finance, and Stock & Medicines**. The dashboard consolidates revenue, doctor performance, patient admissions, payment behavior, and inventory movement into one navigable report, enabling faster, data-driven operational decisions.

---

## 🗂️ Tables Used (Data Model)
The report is built on a **star schema** with the following tables:

| Table | Type | Description |
|---|---|---|
| `Patients` | Dimension | Patient master data — name, gender, insurance, symptoms, room no., total bill |
| `Doctors` | Dimension | Doctor master data — name, gender, qualification, specialization |
| `Appointments` | Fact | Appointment records, status, consultant type (Online/Walk-in) |
| `Bills` | Fact | Room, test, medicine, consultation charges |
| `Tests` | Fact | Test-related billing |
| `Medicine_Dispensing` | Fact | Medicine dispensed by day/month, quantity, price |
| `Stock_Management` | Fact | Stock volume, current stock, over/low stock status |
| `Finance_Charges` | Derived (Power Query, unpivoted) | Charge-type breakdown for finance analysis |
| `Calender_table` | Date Dimension | Calendar table used across all DAX time-intelligence measures |
| `Measure_Table` | Measures | Dedicated table holding all DAX measures |

---

## 📊 KPIs Tracked

**Patients Page**
- Total Patients: **5,000**
- Avg. Stay Days: **3.9 Days**
- Admitted Patients: **640**
- Discharged Patients: **2,571**
- Scheduled Patients: **1,474**

**Finance Page**
- Total Revenue: **$52,887,754**
- Avg. Revenue: **10.58K**
- Total Room Charge: **25.33M**
- Total Test Charge: **15.98M**
- Total Medicine Charge: **7.56M**
- Total Consultation Charge: **6M**
- Revenue by Insurance Provider (Not Insured, ICICI Lombard, HDFC Ergo, Star Health)
- Payment Split (Cash, Card, UPI, Insurance)

**Doctor Page**
- Appointments: **7,000**
- Commission Rate: **15%**
- Commission Amount: **7.93M**
- Avg. Fees: **1.20K**
- Avg. Rating: **3.86**

**Stock & Medicines Page**
- Total Stock Volume: **600.7M**
- Total Stock: **986.1K**
- Current Stock: **968.7K**
- Dispensed Stock: **17.4K**
- Dispensed Amount: **4.3M**

---

## ⚙️ Process

1. **Data Collection** — Gathered hospital operational data across patients, doctors, billing, appointments, and stock/medicine dispensing.
2. **Data Preparation** — Structured raw data into fact and dimension tables suitable for a star schema.
3. **Data Cleaning** — Fixed inconsistencies including a Calendar table date-range mismatch that was causing ~21M in revenue to appear as blank/unmapped rows.
4. **Data Modeling** — Built a star schema (patients/doctors as dimensions; appointments, bills, tests, medicine dispensing, stock as facts) with relationships and a dedicated Measure Table for DAX.
5. **Dashboard Development** — Designed 5 pages (Home, Doctor, Patients, Finance, Stock & Medicines) with KPI cards, trend charts, donut/bar visuals, and conditional-formatted tables (SVG pill-badge status tags).
6. **Testing & Deployment** — Validated measures (`SELECTEDVALUE`, `LASTNONBLANKVALUE`), cross-checked KPI totals against source tables, and finalized theme/branding before publishing.

---

## ❓ Business Questions Answered
- What is the total revenue generated, and how does it trend month-over-month?
- Which charge category (Room, Test, Medicine, Consultation) contributes most to revenue?
- How do patients pay — Cash, Card, UPI, or Insurance — and which insurer contributes the most?
- How many patients are admitted, discharged, or scheduled at any given time, and what is the average stay duration?
- Which age group and insurance provider make up the largest share of patients?
- Which doctors and specializations generate the highest billing and commission?
- What is the doctor performance split by consultation type (Online vs Walk-in) and gender?
- Which medicines are dispensed most, and what is the current stock health (in stock / low stock / overstock)?
- How does patient volume and medicine dispensing vary by day of week and month?

---

## 🔍 Observations & Data Highlights
- Total revenue stood at **$52.89M**, up **68.2% MoM** with a swing of **+$21.45M** vs. last month.
- **Room Charges (47.90%)** are the single largest revenue contributor, followed by Test Charges (30.22%).
- **Cash (36.19%)** is the leading payment mode, followed by UPI (22.95%) and Card (28%); Insurance-based payments are comparatively low (12.86%).
- Revenue is highly seasonal — a sharp dip in **June-July** followed by a strong recovery (**+19.4%**) in **August**.
- Of **5,000 total patients**, **2,571 have been discharged**, **640 are currently admitted**, and **1,474 are scheduled**, with an average stay of **3.9 days**.
- Patient insurance coverage is fairly evenly split across **HDFC Ergo, ICICI Lombard, Star Health, and Not Insured** (each roughly 24-26%).
- **Senior Citizens (1,306) and Pediatric patients (1,032)** form the largest age-group segments, ahead of Young Adult and Middle Age groups.
- **ENT** has the highest appointment volume by specialization (900), ahead of Dermatology and Urology.
- Medicine stock shows a healthy split, though a visible **"Over stock" (11.9K)** segment flags potential overstocking risk in specific items.

---

## 📈 Visuals & Analytics Used
- KPI cards for patients, revenue, appointments, commissions, and stock metrics
- Line chart with variance callouts — Revenue by Month
- Column chart — Total Patients by Month, Total Patients by Age Group
- Donut charts — Payment Split, Consultant Type, Doctors by Gender, Insurance by Patients, Medicine Stock Status
- Horizontal bar charts — Appointment by Specialization, Dispensed Qty by Medicine Name/Type
- Matrix/table visuals with conditional formatting (SVG pill badges) — Patients Overview, Doctor Performance, Medicine Status
- Heatmap-style table — Medicine by Day and Month
- Patient/Doctor Information cards with photo, symptom/specialization, gender, age, blood group, and star rating
- Custom Deneb/Vega-Lite visuals and a custom Power BI theme (JSON) for consistent branding
- Interactive month slicers and page navigation buttons across all report pages

---

## 💡 Actionable Insights
- Since Room and Test charges drive ~78% of revenue, pricing or capacity optimization here has outsized financial impact.
- Low insurance-based revenue (12.86%) suggests an opportunity to onboard more insurance tie-ups to reduce cash dependency.
- The June-July revenue dip is a candidate for a seasonal-demand investigation (staffing, promotions, or referral drop-off).
- A high share of Senior Citizen and Pediatric patients points to a need for age-specific staffing and resource planning (geriatric/pediatric wards).
- Overstocked medicine categories should be reviewed to reduce holding costs and avoid expiry-related wastage.
- High-commission, top-performing doctors (flagged "Top perf.") could be leveraged for mentoring or scheduling more Online consultations, which appear to be a growing channel.

---

## 🎯 Expected Outcomes
- Faster, centralized visibility into hospital financial and operational performance for management.
- Reduced manual reporting effort by replacing static spreadsheets with a live, interactive dashboard.
- Better-informed decisions on staffing, insurance partnerships, patient care planning, and inventory management.
- A reusable, scalable star-schema model that can extend to future hospital data sources.

---

## ✅ Conclusion
This project demonstrates a complete Power BI workflow — from raw data modeling to a polished, multi-page, decision-ready dashboard — applied to a real-world hospital operations use case. It combines strong data modeling (star schema, DAX), clean UX (navigation, conditional formatting, custom visuals), and business-focused storytelling (KPIs tied directly to actionable questions) across Patients, Doctors, Finance, and Stock & Medicines.

---

## 📬 Contact Me
**Shivraj Singh Sisodiya**
📍 Jaipur, Rajasthan, India
🌐 Portfolio: [datascienceportfol.io/shivraj](https://datascienceportfol.io/shivraj)
💻 GitHub: [github.com/shivrajsinghsisodiya9351-alt](https://github.com/shivrajsinghsisodiya9351-alt)

---

## 📂 Explore the Full Project
Want to see the complete model, DAX measures, and interactions live? **Download the `.pbix` file** from this repository and open it in **Power BI Desktop** to explore all pages, drill-throughs, and measures in detail.

👉 [Download the .pbix file](https://github.com/shivrajsinghsisodiya9351-alt/Hospital-Management-Analytics-Dashboard/blob/main/Hospital_dashboard.pbix))

> Replace the path above with the actual `.pbix` file location in your repo.
