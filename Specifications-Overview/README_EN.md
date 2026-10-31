# BI Project – End-of-Module Satisfaction Surveys

## 1. Project Overview

This project aims to implement a structured satisfaction survey process for students enrolled in long-term training programs within the C&D Group.

Its objective is to measure student satisfaction at the end of each training module, monitor teaching quality, and identify key strengths and areas for improvement.

The solution relies on automated survey distribution, response collection and data processing, supported by interactive Power BI dashboards.

## 2. Business Objectives

| ID | Objective | Success Indicator | Target |
|---|---|---|---|
| O1 | Design survey forms based on the defined analytical dimensions. | Survey forms validated and available | 100% of required forms |
| O2 | Automate questionnaire distribution to eligible students. | Automated questionnaire delivery rate | 100% of eligible students |
| O3 | Automate survey response collection and centralization. | Rate of responses correctly received and recorded | ≥ 95% of submitted responses |
| O4 | Clean, transform, and prepare data for analysis. | Rate of compliant and usable data | ≥ 95% |
| O5 | Develop interactive dashboards to monitor student satisfaction. | Availability of priority indicators | 100% |
| O6 | Enable stakeholders to identify trends and improvement opportunities. | Coverage of priority analytical needs | 100% |

## 3. Functional Scope and Business Process

The project covers the complete process, from reference data preparation to reporting and analysis.

1. **Reference Data Preparation**
   - Validate and clean student registration data.
   - Identify students and training modules within the survey scope.
   - Extract data from IGOR and transfer it to a dedicated SQL Server database.

2. **Survey Form Design**
   - Create satisfaction questionnaires for each training module.
   - Configure questions and analytical dimensions.
   - Associate survey forms with the relevant student populations.

3. **Survey Process Automation**
   - Distribute questionnaires to eligible students.
   - Monitor received responses.
   - Automatically send reminders.
   - Receive and record survey responses.

4. **Data Centralization and Preparation**
   - Store survey responses in a dedicated database.
   - Match responses with reference data.
   - Perform data cleaning, quality checks, and normalization.
   - Calculate satisfaction indicators and scores.

5. **Reporting and Analysis**
   - Develop interactive Power BI dashboards.
   - Monitor participation and satisfaction by module.
   - Compare results and identify the highest- and lowest-rated modules.

## 4. Key Performance Indicators (KPIs)

| KPI | Definition | Formula / Rule | Target |
|---|---|---|---|
| **KPI 01 – Number of Responses Received** | Number of responses recorded for a survey campaign. | Count of valid responses after deduplication. | Ongoing monitoring |
| **KPI 02 – Response Rate** | Proportion of invited students who submitted a response. | (Number of valid respondents ÷ Number of students invited) × 100 | ≥ 70% as an indicative target |
| **KPI 03 – Number of Notifications Sent** | Total number of invitations and reminders sent. | Count of notifications by type and campaign. | 100% of planned notifications processed |
| **KPI 04 – Satisfaction Rate by Module** | Proportion of students satisfied with each module. | (Number of satisfied responses ÷ Number of responses received) × 100, by module. | To be defined after the first campaign |
| **KPI 05 – Module Ranking** | Identification of the highest- and lowest-rated modules. | Average overall satisfaction score by module, ranked in Top 10 and Bottom 10 lists. | To be defined |

KPIs are refreshed at each Power BI data refresh.

## 5. Data Sources and Technologies

### Data Sources

- **IGOR / SQL Server:** Student registration, student, training program, and analytical dimension data. Read-only access according to granted permissions.
- **Dedicated Data Analytics SQL Server Database:** Storage of prepared data and survey responses. Controlled read and write access according to processing requirements.

### Technologies Used

- SQL Server: Data storage and centralization.
- Power BI: Data modeling, KPI calculations, and visualization.
- Automation tools: Survey distribution, reminders, and response processing.

## 6. Main Business Rules

| ID | Category | Rule |
|---|---|---|
| **RG-DEF-001** | Definition | An eligible recipient is a student registered in IGOR, associated with a training period included in the survey campaign, and with the information required for questionnaire distribution. |
| **RG-CAL-001** | Calculation | The response rate is calculated using recipients who received the questionnaire and submitted a valid response. |
| **RG-PER-001** | Scope | Surveys cover the programs, school brands, and training periods included in the campaign. Ineligible students and cancelled campaigns are excluded. |
| **RG-QUA-001** | Data Quality | Mandatory information, including student ID, training period, and email address, must be validated before distribution. |
| **RG-EXC-001** | Exceptions | Missing data, unlinked responses, and detected duplicates are flagged as anomalies and excluded from the relevant calculations until verified. |
| **RG-TMP-001** | Timing | Initial questionnaire distribution takes place at J-7 before the end of the training module, with reminders at J-3 and J-2. No reminder is sent after a valid response or after campaign closure. |
| **RG-SEC-001** | Security | Access to personal student data and survey results is restricted according to user roles, responsibilities, and granted permissions. |

*Business rule validation status: RG-DEF-001, RG-CAL-001, and RG-PER-001 are under review. RG-QUA-001, RG-EXC-001, RG-TMP-001, and RG-SEC-001 are in draft status.*

---

*Project carried out as part of the student satisfaction analysis initiative for the Compétences & Développement Group.*
