# HSE Dashboard - Power BI Project

## 📊 Project Summary
This project presents an interactive Power BI dashboard that analyzes Occupational Health and Safety data. The data is simulated for confidentiality reasons.

## 🔍 Main Features
- **TRIR** (Total Recordable Incident Rate)  **TRIR Target** chosen = 2
- **LTI Rate** (Lost Time injury Rate)  **LTIR** target chosen = 0.2
- Total Lost days
- Days from last LTI 
- Filter by **Year**, **Contractor/Company**, **Incident Type** and **Cause**

## Main calculations used 
🔹**LTIR (Lost Time Injury Rate)**
		LTIR =
		(FAT + LTI) / Total Hours Worked × 1,000,000
<img width="506" height="82" alt="image" src="https://github.com/user-attachments/assets/9210e2f9-85fd-49b1-8830-777c84f77f73" />
🔹 **TRIR (Total Recordable Injury Rate)**
	TRIR =
	(FAT + LTI + RWC + MTC) / Total Hours Worked × 1,000,000
<img width="568" height="82" alt="image" src="https://github.com/user-attachments/assets/0490c847-7a47-4857-8eb4-a3f98d791955" />

## Some DAX measures 
Days Since Last LTI = 
VAR _lastLTIDate = [Last LTI Date]
RETURN
    IF(
        ISBLANK(_lastLTIDate),
        BLANK(), // 
        DATEDIFF(_lastLTIDate, TODAY(), DAY)
    )

Last LTI Date = 
CALCULATE(
    MAX(Incidents[IncidentDate]),
    FILTER(
        ALL(Incidents),
        Incidents[IncidentType] = "LTI"
    )
)
<img width="671" height="340" alt="image" src="https://github.com/user-attachments/assets/d9c739cf-3966-4076-86de-efd301c83ba3" />

## 📁 Data
The project uses three CSV files with randomly generated data:
- `Incidents.csv`
- `WorkedHours.csv`

## 📷 Final report
![Dashboard Overview](HSEDashboardReport.pdf)
![Screenshot](HSE_Dashboard.mp4)


## 🛠 Tools Used
- Microsoft Power BI
- Excel Power Query and SQL (for data cleaning)
- Simulated data

## 📬 Contact
- LinkedIn: [www.linkedin.com/in/meryem-kacem]
- Email: [kacem.meryem02@gmail.com]
