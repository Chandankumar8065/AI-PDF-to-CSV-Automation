# AI PDF to CSV Automation

A reproducible invoice-extraction project comparing a traditional Python rules-based workflow with an AI-assisted workflow using **Qwen 2.5 1.5B Instruct**. The notebook also provides a Gradio interface for uploading text-based invoice PDFs and downloading extracted CSV data.

## Project workflow

1. Generate five synthetic invoice pages with known ground-truth values.
2. Extract invoice fields with labelled, rule-based Python parsing.
3. Extract the same fields with Qwen.
4. Compare both methods against the ground truth, counting missing values as mismatches.
5. Independently validate the synthetic invoice totals using quantity × unit price × (1 + GST rate).
6. Benchmark both methods over repeated runs.
7. Export the datasets, field-level comparisons, financial checks, and timing results.
8. Launch a Gradio PDF-upload interface.

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
│   ├── Traditional_Invoice_Extraction.csv
│   └── Ground_Truth_Invoices.csv  (generated when notebook runs)
├── results/
│   ├── Field_Level_Comparison.csv (generated when notebook runs)
│   ├── Financial_Validation.csv   (generated when notebook runs)
│   ├── Extraction_Accuracy_Summary.csv (generated when notebook runs)
│   └── Performance_Benchmark.csv  (generated when notebook runs)
└── docs/
    └── RESEARCH_FINDINGS.md
```

## Run the project

1. Open `notebooks/AI_PDF_to_CSV_Automation.ipynb` in Google Colab.
2. Select a GPU runtime if available (a T4 or better is recommended for Qwen).
3. Run the notebook from top to bottom. The notebook installs its dependencies and generates its own five-page synthetic test PDF; no separate sample PDF download is required.
4. Review the comparison, financial validation, and timing outputs.
5. Run the final Gradio launch cell to open the temporary app link.

For a local environment, install dependencies with:

```bash
pip install -r requirements.txt
```

Then open the notebook in Jupyter. Model loading requires internet access on first run and sufficient memory. CPU inference may be slow.

## Evaluation and limitations

The five invoices are synthetic and use a stated 18% GST rate. Accuracy and financial checks are calculated against their known source values. Results do not establish performance on arbitrary vendor invoices. The traditional parser is label-based and may need adaptation for other layouts. The app supports text-based PDFs only; scanned/image-only PDFs require OCR. AI-extracted data must be reviewed before financial or operational use.

Timing depends on hardware, runtime load, model version, and generation settings. Treat benchmark values as observations from the specific run, not universal performance claims.

## Technologies

Python, pandas, PyMuPDF, PyTorch, Transformers, Qwen 2.5, Matplotlib, Gradio, Jupyter / Google Colab.

## Data and responsible use

The included research data is synthetic. Do not upload confidential customer invoices or commit credentials, API keys, access tokens, or private business documents.

## Author

Chandan Kumar Chauhan
