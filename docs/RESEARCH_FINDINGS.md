# Research Findings

## Experiment design

This project compares traditional label-based Python extraction with Qwen 2.5 1.5B Instruct on five synthetic, text-based invoice pages generated inside the notebook. The synthetic records are the ground truth and use an explicitly stated GST rate of 18%.

## Evaluation method

- Both methods extract Invoice_ID, Invoice_Date, Customer, Product, Quantity, Unit_Price, and Total_Amount.
- Each method is compared independently with the known ground-truth fields.
- A missing value is counted as a mismatch; two missing values are never counted as a successful match.
- Numeric values are compared with a tolerance of 0.01.
- Financial validation independently calculates quantity × unit price × (1 + GST rate) from the synthetic source records and compares each extracted total with that calculated amount.
- Processing time is measured over repeated runs after an AI warm-up. Results vary by runtime and hardware.

## Results

The notebook computes the accuracy, validation pass count, and timing values when run. The generated CSVs in `results/` are the run outputs. Do not report a fixed accuracy or timing number without checking the latest notebook execution and corresponding exports.

## Limitations

- Only five synthetic invoices are included in the experiment.
- The traditional parser is label-based and may need adaptation for unfamiliar layouts.
- The AI model can produce incorrect or incomplete values; review extracted data.
- The notebook and Gradio application support text-based PDFs. Scanned/image-only PDFs need OCR, which is not included.
- One invoice per PDF page is assumed in the research sample.
- Benchmark timings depend on model, hardware, runtime load, and software versions.
- The financial formula is appropriate only for the generated sample's stated tax assumptions; real invoices may include discounts, multiple tax rates, shipping, or other adjustments.

## Reproducibility

Run `notebooks/AI_PDF_to_CSV_Automation.ipynb` from top to bottom. It generates the sample PDF and exports the ground truth, extracted datasets, field comparisons, financial validation, accuracy summary, and benchmark CSVs.
