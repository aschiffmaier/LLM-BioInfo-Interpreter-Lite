# LLM Bioinformatics Interpreter (Lite)

A working, offline Streamlit prototype that transforms uploaded gene-expression data into a structured prompt for language-model-assisted interpretation.

The application accepts a CSV file, displays the uploaded expression values, and automatically formats the data into a molecular-biology prompt. It also presents a clearly labeled simulated response to demonstrate how a future LLM integration could communicate potential biological insights.

> **Important:** The upload, data-preview, and prompt-generation features are fully functional. The interpretation is a fixed demonstration response; the application does not currently call an LLM or perform statistical differential-expression analysis.

## Live Application

[Launch the Streamlit application](https://cfzuh7csnopnmzie5nkzig.streamlit.app/)

## Project Overview

This proof of concept was developed in April 2025 in response to a Parker Dewey micro-internship project from the Rosetta Institute of Biomedical Research.

The original brief explored how existing large language models could support the interpretation of biochemical datasets such as:

* Microarray data
* RNA-seq data
* Mass-spectrometry data
* Gene-expression tables

The Lite prototype focuses on one stage of that larger workflow: converting a compact gene-expression dataset into a structured, reviewable prompt without transmitting the uploaded data to an external AI service.

## Features

* Working Streamlit web interface
* Gene-expression CSV upload
* Uploaded-data preview
* Structured molecular-biology prompt generation
* Support for a compact two-condition expression format
* Clearly labeled simulated interpretation
* Offline operation with no AI API calls
* Transparent, lightweight Python implementation
* Synthetic sample dataset for demonstration

## How It Works

1. The user uploads a compatible gene-expression CSV.
2. The application reads the file and extracts its headers and rows.
3. The uploaded values are displayed in the Streamlit interface.
4. The application inserts the data into a structured molecular-biology prompt.
5. The completed prompt is displayed for review.
6. A fixed simulated response demonstrates the intended form of a future interpretation.

The application therefore provides a functional bridge between tabular expression data and an LLM-ready prompt. The final model-inference stage remains intentionally simulated.

## Expected CSV Format

The current prototype expects three columns: a gene identifier followed by expression values for two conditions.

```csv
Gene,Condition_A,Condition_B
TP53,8.4,3.1
BRCA1,4.2,7.8
VEGFA,2.0,9.3
EGFR,3.5,6.9
MYC,4.1,8.0
```

The included sample values are synthetic and are intended solely to demonstrate the application’s interface and workflow. They are not experimental findings.

## Prompt Example

After a compatible CSV is uploaded, the application constructs a prompt in this form:

```text
You are a molecular biology LLM assistant. Analyze the following gene expression data:

Gene, Condition_A, Condition_B
TP53, 8.4, 3.1
BRCA1, 4.2, 7.8
VEGFA, 2.0, 9.3
EGFR, 3.5, 6.9
MYC, 4.1, 8.0

Instructions:
- Identify significantly up- or downregulated genes.
- Suggest molecular roles.
- Propose a hypothesis for further investigation.
```

In a future version, this prompt could be sent to an approved language model and supplemented with statistical results, dataset provenance, literature citations, and expert review.

## Repository Contents

| File                         | Purpose                                                      |
| ---------------------------- | ------------------------------------------------------------ |
| `streamlit_app.py`           | Functional Streamlit application and prompt-generation logic |
| `sample_gene_expression.csv` | Synthetic five-gene demonstration dataset                    |
| `requirements.txt`           | Python dependency specification                              |
| `README.md`                  | Project documentation                                        |
| `LICENSE`                    | Proprietary all-rights-reserved license                      |

## Running the Application Locally

Clone the repository:

```bash
git clone https://github.com/aschiffmaier/LLM-BioInfo-Interpreter-Lite-.git
cd LLM-BioInfo-Interpreter-Lite-
```

Create a virtual environment:

```bash
python -m venv .venv
```

Activate it on Windows:

```bash
.venv\Scripts\activate
```

Or activate it on macOS/Linux:

```bash
source .venv/bin/activate
```

Install the required dependency:

```bash
pip install -r requirements.txt
```

Start the application:

```bash
streamlit run streamlit_app.py
```

Open the local Streamlit address shown in the terminal and upload `sample_gene_expression.csv`.

## Potential Data Sources

A future version could be adapted to work with appropriately processed data from established public repositories:

* [NCBI Gene Expression Omnibus](https://www.ncbi.nlm.nih.gov/geo/) — microarray and sequence-based functional-genomics studies
* [EMBL-EBI Expression Atlas](https://www.ebi.ac.uk/gxa/home) — curated microarray and RNA-seq expression datasets
* [NCI Genomic Data Commons](https://portal.gdc.cancer.gov/) — harmonized cancer-genomics and RNA-seq data

Files from these repositories cannot necessarily be uploaded directly. Their schemas, metadata, normalization methods, access conditions, and experimental context must be reviewed before the data are converted into the prototype’s three-column format.

Controlled-access or identifiable human data is outside the scope of this application.

## Future Development

A more complete research workflow could:

1. Validate the uploaded file and identify its expression scale.
2. Normalize and filter the data using established bioinformatics methods.
3. Calculate fold changes, uncertainty, and statistical significance.
4. Preserve study metadata and dataset provenance.
5. Generate prompts from reviewed statistical results.
6. Integrate an approved domain domain-relevant language model.
7. Retrieve and verify supporting scientific literature.
8. Return cited hypotheses with confidence and limitation statements.
9. Preserve model settings and outputs in an auditable report.
10. Require review by a qualified researcher.

An LLM should assist with explanation and hypothesis generation—not replace statistical analysis, biological validation, or expert judgment.

## Current Limitations

* No live LLM or BioGPT integration
* No normalization or differential-expression statistics
* Fixed three-column input format
* Fixed simulated response independent of the uploaded values
* No scientific-literature retrieval or citation verification
* No dataset-provenance or audit-log system
* Not evaluated for research, diagnostic, or clinical use

## Project Outcome

The prototype demonstrates how a lightweight Python application can make gene-expression data visible, convert it into a structured natural-language request, and illustrate a possible human-reviewable LLM workflow.

It also provided practical experience in:

* Python application development
* Streamlit deployment
* CSV processing
* Prompt design
* Scientific-interface prototyping
* Bioinformatics workflow planning
* GitHub project documentation

## Disclaimer

LLM Bioinformatics Interpreter (Lite) is a non-clinical educational and portfolio prototype. It does not provide medical advice, diagnoses, treatment recommendations, validated research conclusions, or scientifically verified interpretations.

## License

Copyright © 2025–2026 Allison “Ally” Schiffmaier. All rights reserved.

This repository is publicly accessible for portfolio review, educational evaluation, and demonstration purposes only. No permission is granted to copy, modify, redistribute, republish, sublicense, sell, or create derivative works from its original source code, design, documentation, or sample materials.

See [LICENSE](LICENSE) for the complete terms.
