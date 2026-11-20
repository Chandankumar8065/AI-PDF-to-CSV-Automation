# AI PDF to CSV Automation

A comparative invoice-extraction project that evaluates a traditional Python extraction workflow against an AI-assisted workflow. Both approaches were tested on the same five synthetic invoices, then compared for field-level accuracy, financial consistency, and processing time.

## Project overview

The notebook processes five invoice documents and extracts the following fields:

- Invoice ID
- Invoice date
- Customer
- Product
- Quantity
- Unit price
- Total amount

The traditional workflow and AI-assisted workflow produce structured tabular outputs. The project then compares corresponding fields, checks invoice calculations, validates the resulting datasets, and benchmarks execution time.

## Experiment results

The recorded run produced the following results:

| Measure | Traditional Python | AI extraction |
|---|---:|---:|
| Invoices processed | 5 | 5 |
| Field-level matches | 30 / 30 | 30 / 30 |
| Field-level match rate | 100% | 100% |
| Successful financial validations | 5 | 5 |
| Failed financial validations | 0 | 0 |
| Total revenue in validation summary | 73,573.00 | 73,573.00 |
| Average processing time | 0.003197 seconds | 17.274078 seconds |

For this small test, traditional Python was substantially faster. The measured AI extraction time was approximately 5,403 times the traditional processing time. These timings are specific to the recorded notebook run and should not be treated as a general benchmark of all AI or Python extraction systems.

## Key findings

1. Both methods achieved a 100% field-level match across the five tested invoices (30 field comparisons).
2. Both methods passed all five financial validation checks, with no failed validations.
3. Traditional Python was faster on these structured synthetic invoices in the recorded experiment.
4. The experiment is limited to five synthetic invoices. More testing is needed across larger datasets, varied invoice layouts, scanned documents, and real-world invoices before drawing broader conclusions.

## Repository structure

The repository is intended to contain:

```text
AI-PDF-to-CSV-Automation/
├── README.md
├── notebooks/
│   └── AI_PDF_to_CSV_Automation.ipynb
└── data/
    ├── AI_Invoice_Extraction.csv
    ├── Traditional_Invoice_Extraction.csv
    ├── Extraction_Validation_Summary.csv
    └── Performance_Benchmark.csv
```

The notebook and CSV exports will be added after the project files are uploaded.

## How to explore

1. Open the notebook in Google Colab or Jupyter.
2. Review the extraction functions and the input invoice documents used in the experiment.
3. Run the traditional and AI-assisted extraction workflows.
4. Review the field-level comparison, financial validation, and timing outputs.
5. Inspect the exported CSV files.

## Tools

- Python
- pandas
- Jupyter Notebook / Google Colab
- Matplotlib (for result visualizations)

The exact additional packages and model/API requirements should be taken from the notebook once it is included.

## Data and reproducibility

The current experiment uses five synthetic invoices. Results are dependent on the input documents, extraction implementation, runtime environment, and any external AI service used by the notebook. Do not commit API keys, access tokens, private invoices, or other credentials to this repository.

## Limitations and next steps

- Increase the number of test invoices.
- Test different invoice templates and layouts.
- Include scanned and lower-quality documents.
- Repeat benchmarks across multiple runs and report variability.
- Record the exact model, prompt, API configuration, and runtime environment for reproducibility.

## Author

Chandan Kumar Chauhan
