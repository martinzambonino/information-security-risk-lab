# Information Security Risk Lab

![GitHub Actions Status](https://img.shields.io/github/actions/workflow/status/martinzambonino/information-security-risk-lab/ci.yml?branch=main)
![License](https://img.shields.io/github/license/martinzambonino/information-security-risk-lab)

## What It Does

A hands-on laboratory for learning and applying information security risk management frameworks and methodologies:

- **Risk Matrices:** Quantitative and qualitative risk assessment matrices with likelihood × impact scoring.
- **Threat Modeling:** STRIDE-based threat identification and diagramming for sample architectures.
- **Compliance Mapping:** Mapping organizational controls to NIST CSF, ISO 27001 Annex A, and LOPDP requirements.
- **EITDP Templates:** Data Protection Impact Assessment (Evaluación de Impacto en el Tratamiento de Datos Personales) templates aligned with Ecuadorian regulations.

## Skills Demonstrated

| Skill | Details |
|---|---|
| Risk Assessment | Qualitative/quantitative matrices, heat maps |
| Frameworks | NIST CSF, ISO 27001, ISO 27005, FAIR |
| Threat Modeling | STRIDE, attack trees, data flow diagrams |
| Compliance | LOPDP/SPDP (Ecuador), GDPR mapping |
| Python | Risk calculation automation, visualization |

## How to Run

```bash
# Clone the repository
git clone https://github.com/martinzambonino/information-security-risk-lab.git
cd information-security-risk-lab

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Linux/macOS
# venv\Scripts\activate   # Windows

# Install dependencies
pip install -r requirements.txt

# Run risk assessment example
python src/risk_matrix.py --help
```

## Methodology

- **NIST RMF (SP 800-37):** Risk Management Framework for categorization, selection, implementation, and monitoring of controls.
- **ISO 27005:2022:** Information security risk management guidelines.
- **FAIR (Factor Analysis of Information Risk):** Quantitative risk analysis model.
- **STRIDE:** Threat classification methodology by Microsoft.

## Limitations

- Risk calculations use **synthetic scenarios** — not derived from real organizational data.
- Compliance mappings are simplified for educational illustration and do not constitute legal advice.
- EITDP templates are educational examples and must be reviewed by qualified legal counsel before use in production.

## ⚖️ Ethical & Legal Disclaimer

> [!WARNING]
> **This repository is strictly for academic and educational purposes.**
> The risk assessment templates and methodologies are provided as learning tools and do **not** constitute professional risk consulting or legal compliance advice.
> The author assumes no liability for decisions made based on these materials.

### 🇪🇨 Compliance Note (Ecuador — LOPDP/SPDP)

This project adheres to Privacy by Design and Default principles.
**No real personal data is used, stored, or processed.** All scenarios, organizations, and datasets referenced are purely fictitious. EITDP (Evaluación de Impacto en el Tratamiento de Datos Personales) templates are provided as educational references compliant with the *Ley Orgánica de Protección de Datos Personales (LOPDP)* and auditable by the *Superintendencia de Protección de Datos Personales (SPDP)*.
