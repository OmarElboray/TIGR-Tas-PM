# TIGR-TasR

TIGR-TasR is a Flask-based computational scoring platform for generating and comparing dual-spacer RNA-guided DNA-targeting candidates for the TIGR-Tas nuclease system.

Given a DNA sequence or a gene/promoter lookup, it can generate candidate spacer pairs and display model outputs for geometry, cleavage, thermodynamics, and specificity.

> **Scientific caution:** several parameters are hypotheses transferred from related CRISPR systems and are not experimentally validated for TIGR-Tas. Review the scoring modules and test suite before interpreting results. The composite final score is intentionally not calculated while its weights remain unresolved.

## Features

- Raw DNA and FASTA input.
- NCBI Entrez and Ensembl sequence retrieval.
- Candidate pair generation with spacer-length, distance, and GC constraints.
- Separate geometry, cleavage, thermodynamic, and specificity models.
- Results table and sequence overview UI.
- Automated unit and integration tests.

## Install

```bash
git clone https://github.com/OmarElboray/TIGR-Tas-PM.git
cd TIGR-Tas-PM
python -m venv .venv
source .venv/bin/activate
pip install -r backend/requirements.txt
```

## Run

```bash
python app.py
```

Open <http://localhost:5000>.

For NCBI requests, provide a valid email address as required by Entrez usage policies.

## Test

```bash
pytest tests/ -v
```

Network-dependent NCBI and Ensembl checks should be run deliberately and may require network access.

## Repository structure

```text
TIGR-Tas-PM/
├── app.py                  # Flask entry point and routes
├── modules/                # Candidate generation and scoring models
├── templates/              # Input and results pages
├── static/                 # Browser assets
├── tests/                  # Unit and integration tests
└── backend/requirements.txt
```

## Data sources

The application uses NCBI Entrez and the Ensembl REST API for genome lookups. Review their terms, rate limits, and attribution requirements before operating the service publicly.

## License

GPLv3
