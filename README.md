# 👥 HR Dashboard — Employee Insights & Workforce Analytics (Power BI) — PB20

## 📌 Project Overview  
This Power BI dashboard analyzes **human resources data** for a fictional multinational organization, focusing on **workforce composition, retention risk, promotion readiness, job satisfaction, tenure, and geographic distribution**.  

Designed as a **strategic HR analytics project**, it demonstrates **DAX-driven employee segmentation, conditional logic, time-based analysis, and executive storytelling** — ideal for showcasing skills in people analytics, talent management, and organizational health reporting.

---

## 👀 Dashboard Preview  
<img width="600" height="347" alt="hr pb1" src="https://github.com/user-attachments/assets/aa674784-2634-4288-920f-14882b600aa3" />
<img width="602" height="337" alt="hr pb2" src="https://github.com/user-attachments/assets/04f4db95-728d-4f0a-8a9d-79827ccf51b6" />
<img width="598" height="338" alt="hr pb 3" src="https://github.com/user-attachments/assets/4b45d004-1208-499e-a5df-b536032cdcb1" />



*(Screenshot captured Febraury  15, 2026)*

---

## 🎯 Objectives  
- Analyze **total headcount, gender distribution, and active workforce**  
- Identify employees **due for retrenchment or promotion**  
- Track **service years, job levels, and satisfaction ratings**  
- Visualize **distance from office** and its correlation with status  
- Practice **multi-tab navigation (Home / Action / Detail)**  
- Apply **business-oriented insight generation** for HR decision-making

---

## 📊 Dashboard Breakdown

### 🔹 Key Metrics (KPIs)
- **Total Employees**: 1,470  
- **Male**: 882 (60%)  
- **Female**: 588 (40%)  
- **Active Workers**: 1,353 (92.0%)  
- **Due for Retrenchment**: 117 (8.0%)  
- **Due for Promotion**: 72 (4.9%)  
- **Not Due for Promotion**: 1,398 (95.1%)  
- **High Satisfaction Rating**: 84.6%  
- **Low Rating**: 0.15%  

→ Indicates a **stable, experienced workforce**, with clear action items for talent development and restructuring.

---

### 🔹 Home Tab
#### 📈 Workforce Overview
- KPI cards: Total employees, gender split, active workers  
- Red alert: **117 employees due for retrenchment**, **72 due for promotion**  
- Red sidebar note: *“Those are the set of employees that would either need to be promoted or retired”*

#### 📊 Services Years (Bar Chart)
- Top tenure: **10 years** → 202 employees  
- Followed by: 6 years (125), 8 years (103), 9 years (96)  
→ Confirms **high retention** and mature workforce

#### 📉 Next Retrenchment & Active Workers
- **117** = employees flagged for potential retrenchment  
- **1,353** = currently active (92% of total)

#### 🗺️ Distance from Office (Donut Chart)
- **Very Far**: 940 (63.95%)  
- **Closs** (likely typo for *Close*): 301 (20.48%)  
- **Very Closs**: 229 (15.58%)  
→ Majority work remotely or far from HQ — supports hybrid/remote policy

#### 📊 Job Levels View (Bar Chart)
- Level 1: ~500 employees  
- Level 2: ~450  
- Level 3: ~200  
- Level 4 & 5: <50 each  
→ Pyramid structure with strong base — healthy for succession planning

---

### 🔹 Action Tab
#### 📋 Due for Retrenchment (Table)
- 117 employees listed (e.g., *Adalberto W Creek*, *Allyn O Farrior*, *Bell N Molinaro*)  
- All have value `1` → binary flag

#### 📋 Due for Promotion (Table)
- 72 employees (e.g., *Adelaide L Harrop*, *Aiko Blossom*, *Brendon E Mone*)  
- Also binary flag (`1`)

#### 📊 Due for Promotion vs Retrenchment by Department
- **Research & Development**: 74 due for promotion, 47 due for retrenchment  
- **Sales**: 36 due for promotion, 23 due for retrenchment  
- **Human Resources**: 7 due for promotion, 1 due for retrenchment  
→ R&D is both high-potential and high-risk — needs targeted talent strategy

---

### 🔹 Detail Tab
#### 📊 Total Emp per Job Satisfaction
- High satisfaction: 569  
- Low: 459  
- Medium: 442  
→ Majority are satisfied (569 + 442 = 1,011 → ~69%)

#### 📈 Emp by OverTime (Pie Chart)
- **No**: ~65%  
- **Yes**: ~35%  
→ Moderate overtime usage — monitor burnout risk

#### 📊 High/Low Rating & Job Role Analysis
- Table shows:
  - Sales Executive: 326 total → 16 due for promotion  
  - Research Scientist: 292 → 3 due for promotion  
  - Manufacturing Director: 145 → 4 due for promotion  
→ Promotions concentrated in leadership & sales roles

#### 📊 Due for Promotion et Due for Retrenchment par Department
- Stacked bar chart confirms R&D as highest volume for both actions  
- Visual clarity: orange = promotion, red = retrenchment

---

## 📐 Methodology
- Data modeling: Star schema (`Employees` fact table + `Departments`, `JobLevels`, `Locations` dimensions)  
- DAX measures include:
  - `Total Employees = COUNTROWS(Employees)`
  - `Active Workers = CALCULATE([Total Employees], Employees[Status] = "Active")`
  - `Due for Retrenchment = CALCULATE([Total Employees], Employees[RetrenchmentFlag] = 1)`
  - `Due for Promotion = CALCULATE([Total Employees], Employees[PromotionFlag] = 1)`
  - `% Active Workers = DIVIDE([Active Workers], [Total Employees])`
  - `High Satisfaction = CALCULATE([Total Employees], Employees[Satisfaction] = "High")`
  - `Distance Category = SWITCH(TRUE(), [Distance] > 50, "Very Far", [Distance] > 20, "Closs", "Very Closs")`
- Use of:
  - KPI cards
  - Bar charts
  - Donut/pie charts
  - Tables with conditional formatting
  - Multi-tab navigation (Home / Action / Detail)
- Visual design: Clean corporate theme with red for action items, green/blue for stability

---

## 🛠️ Tools & Technologies
- **Power BI Desktop**
- **Intermediate–Advanced DAX** (CALCULATE, FILTER, SWITCH, DIVIDE, COUNTROWS)
- **Conditional formatting** (for retrenchment/promotion flags)
- **Navigation panes** (custom sidebar with icons)
- **Dashboard layout & storytelling** (role-based views: exec → HRBP → manager)

---

## 📌 Key Insights
✅ **1,470 employees**, with **60% male / 40% female** — room for diversity improvement  
✅ **92% active workforce** — strong retention, but 8% flagged for retrenchment  
✅ **R&D has highest volume of both promotions and retrenchments** — strategic focus area  
✅ **10-year tenure is most common** — experienced team, but watch for stagnation  
✅ **64% work “Very Far” from office** — validates remote/hybrid model  
✅ **High satisfaction (84.6%)** — positive culture, but low-rating outliers need attention  
✅ **Promotions skewed toward Sales & Leadership** — succession planning opportunity  

---

## 📁 Repository Structure
├── HR_Dashboard_PB20.pbix
├── Dataset/
│ └── hr_employees_data.csv
├── Screenshots/
│ └── hr_dashboard_pb20.png
└── README.md


---

## 🚀 Project Purpose
This project was built as a **portfolio Power BI project** to:  
- Practice **people analytics and HR business intelligence**  
- Improve **dashboard design with role-based navigation**  
- Apply **conditional logic and employee segmentation**  
- Simulate **analytics reporting for HR departments in large organizations**

---

## 📬 Contact
**Mustapha Tarfi**  
📍 Morocco  
🔗 LinkedIn: [https://www.linkedin.com/in/mustapha-tarfi-1106b5283/](https://www.linkedin.com/in/mustapha-tarfi-1106b5283/)  
