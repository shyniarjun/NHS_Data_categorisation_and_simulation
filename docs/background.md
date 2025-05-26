## NHS Exemplar Accreditation Use Case

This project originated within the NHS Exemplar Accreditation programme, where performance across 35 wards is assessed using KPIs grouped under four pillars: Quality, Efficiency, Patient Experience, and Staff Experience.

### Problem Identified

- Each ward uses a standalone Excel template with inconsistent layouts and KPI naming
- Colour-based performance bands (Gold/Silver/Bronze/White) were manually or partially formula-driven, making them non-transparent and hard to audit
- KPI thresholds varied widely in structure (percentages, raw counts, text entries) and direction (higher is better vs lower is better)
- Some thresholds required manual interpretation (e.g. \"5–10 more than comparator\") which couldn’t be handled using standard logic
- Performance reports were only compiled biannually due to the manual data cleaning burden

### Project Aim

- Introduce a logic-based categorisation system that standardises KPI performance across wards
- Automate categorisation using Python to remove Excel dependency
- Simulate the effect of performance drops or policy changes on KPI categorisation
- Support ward-level improvement and accreditation readiness using scalable, auditable data pipelines

These aims were driven by real workflow constraints, with no existing automation infrastructure in place.
