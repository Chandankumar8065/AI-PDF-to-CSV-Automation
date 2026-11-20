# AI PDF to CSV Automation

A comparative invoice-extraction project that evaluates a traditional Python workflow against an AI-assisted workflow. Both approaches were tested on the same five synthetic invoices and compared for extracted-field agreement, financial consistency, and processing time.

## Project overview

The notebook demonstrates a PDF-to-structured-data workflow:

1. Upload and read invoice PDFs.
2. Extract invoice fields using traditional Python and an AI language model.
3. Convert the extracted results into Pandas DataFrames.
4. Compare the extracted fields between methods.
5. Validate invoice totals, including 18% GST.
6. Check the resulting datasets for missing values and duplicate invoice IDs.
7. Benchmark processing time and visualize the results.
8. Export the extracted data and evaluation summaries as CSV files.

## Experiment results

The recorded run used five synthetic invoices.

| Measure | Traditional Python | AI extraction |
|---|---:|---:|
| Invoices processed | 5 | 5 |
| Field-level matches | 30 / 30 | 30 / 30 |
| Field-level match rate | 100% | 100% |
| Successful financial validations | 5 | 5 |
| Failed financial validations | 0 | 0 |
| Total revenue in validation summary | 73,573.00 | 73,573.00 |
| Average processing time | 0.003197 seconds | 17.274078 seconds |

For this specific run, traditional Python was substantially faster. The measured AI extraction time was approximately 5,403 times the traditional processing time. These timings depend on the notebook runtime and model configuration; they are not a general benchmark of all AI and Python extraction systems.

## Key findings

- Both methods achieved a 100% field-level match across the five tested invoices (30 field comparisons).
- Both methods passed all five financial validation checks.
- The financial check calculated the line-item subtotal and added 18% GST before comparing it with the invoice total.
- Traditional Python was faster on these structured synthetic invoices in the recorded experiment.
- Only five synthetic invoices were tested, so broader conclusions require more varied data.

## Repository structure

```text
AI-PDF-to-CSV-Automation/
├── README.md
├── requirements.txt
├── .gitignore
├── notebooks/
│   └── AI_PDF_to_CSV_Automation.ipynb
├── data/
│   ├── AI_Invoice_Extraction.csv
│   └── Traditional_Invoice_Extraction.csv
├── results/
│   ├── Extraction_Validation_Summary.csv
│   └── Performance_Benchmark.csv
└── docs/
    └── RESEARCH_FINDINGS.md
```

## How to run

1. Open `notebooks/AI_PDF_to_CSV_Automation.ipynb` in Google Colab or Jupyter.
2. Install the dependencies listed in `requirements.txt` (the first notebook cell also installs the PDF and dataframe libraries used there).
3. Run the notebook cells in order.
4. When prompted, upload a PDF containing invoice pages in a supported text-based format.
5. Review the extraction comparison, financial validation, benchmark charts, and exported CSV files.

The AI workflow downloads and loads its model at runtime. Model loading may require a suitable runtime, sufficient memory, and an internet connection. The notebook was developed in Google Colab with GPU runtime metadata.

## Tools and technologies

- Python
- pandas
- PyMuPDF
- Transformers
- PyTorch
- Matplotlib
- Jupyter Notebook / Google Colab

## Limitations and next steps

- The experiment uses only five synthetic invoices.
- Test more invoice templates, suppliers, and document layouts.
- Evaluate scanned and lower-quality PDFs separately; text extraction alone may not work for image-only scans.
- Repeat timing tests and report variability across runs.
- Record the exact model version and runtime configuration for reproducibility.
- Review AI-extracted values before using them in business or financial workflows.

## Data and responsible use

The included invoice records are synthetic. Do not upload private customer invoices or commit credentials, API keys, or access tokens to this repository.

## Author

Chandan Kumar Chauhan
