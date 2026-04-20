## Antibiotic Resistance Database — SQL + Python Analysis

End-to-end database design and AMR surveillance analysis using 
a real-world antibiotic resistance dataset of 2,199 patient records.

**Tools:** Python, pandas, SQLAlchemy, SQLite, Matplotlib, Seaborn  
**Skills:** Database design, SQL query writing, pandas ↔ SQL integration,
CASE WHEN logic, percentage calculations, data visualisation

**Database structure:**
- `Patients` — demographics and clinical outcomes
- `lab_results` — antibiotic susceptibility results per patient
- `Resistance_summary` — aggregated resistance gene prevalence

**Key findings:**
- Meropenem had the highest resistance rate at 34.29% — alarming 
  for a 3rd line antibiotic
- VIM resistance gene was most associated with deceased patients (167 cases)
- Disc Diffusion detected the most resistant cases (1,225) across all antibiotics
- Female patients had a marginally higher mortality rate (32.07% vs 30.30%)
- Blood, Stool, and Urine specimens showed the highest Meropenem resistance (~36%)

**Recommendations:**
- Urgent review of carbapenem prescribing protocols
- Enhanced VIM surveillance in high-mortality patient cohorts
- Investigation into bloodstream infection management protocols
