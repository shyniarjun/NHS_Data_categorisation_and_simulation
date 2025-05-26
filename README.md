# NHS KPI Categorisation and Simulation

This project automates the classification of ward-level NHS KPIs using standardised threshold logic. It also includes simulation models to assess the impact of performance drops and policy changes on categorised outcomes.

The solution was developed in response to inconsistent and manual KPI reporting practices across 35 NHS wards. Excel templates were colour-coded without a standard logic, limiting automation and performance comparability.

###  What This Project Includes:
- Threshold-based categorisation logic (Gold/Silver/Bronze/Manual/White)
- Python automation of messy ward-level data
- Two simulations:
  - Tightened thresholds for 'Gold'
  - Simulated 3-point KPI performance drop
- Category count summaries and impact visualisations

### Key Files
- `Datascience_project.ipynb`: Main logic, simulation, and outputs
- `KPI_Data_2024.csv`: Sample KPI data file
- `KPI_Threshold_Lookup_Table.csv`: Customised thresholds by KPI and direction

### Documentation
- [Background (Real NHS Problem)](docs/background.md)
- [Methodology (Step-by-step logic)](docs/methodology.md)
- [Simulation Insights](docs/Insights.md)
- [Lessons Learned & Next Steps](docs/Lessons learned & Next steps.md)

###  NHS Relevance
This work supports ward performance evaluation, enables earlier detection of quality risks, and offers a scalable method to simulate policy shifts on service outcomes.
