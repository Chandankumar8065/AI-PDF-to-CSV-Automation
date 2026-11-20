# Research Findings

## Experiment scope
The recorded experiment compared traditional Python extraction with an AI-assisted extraction workflow on five synthetic invoice documents.

## Results recorded in the notebook exports

| Metric | Traditional Python | AI extraction |
|---|---:|---:|
| Invoices processed | 5 | 5 |
| Successful financial validations | 5 | 5 |
| Failed financial validations | 0 | 0 |
| Field-level match rate | 100% | 100% |
| Total revenue | 73,573.00 | 73,573.00 |
| Average processing time (seconds) | 0.0031968713 | 17.2740782513 |

## Interpretation
Both methods produced matching invoice fields for the five test invoices and passed the financial validation checks. In this run, traditional Python completed substantially faster than AI-assisted extraction.

The benchmark is specific to this small dataset and this runtime/model configuration. It does not establish that traditional extraction is always faster or that AI extraction is always more accurate.

## Financial validation logic
The invoice total was validated by calculating the line-item subtotal as quantity multiplied by unit price, then adding 18% GST. The resulting expected total matched the extracted total for each of the five test invoices.

## Limitations
- Only five synthetic invoices were evaluated.
- The results do not establish performance on scanned, noisy, multi-page, or highly varied real-world invoices.
- Timing depends on the runtime environment and the AI model/service configuration.
- Further tests should use a larger and more diverse invoice set, repeated benchmark runs, and documented model/API settings.

## Files
- `data/AI_Invoice_Extraction.csv`: AI-extracted invoice fields.
- `data/Traditional_Invoice_Extraction.csv`: traditional extraction plus financial validation columns.
- `results/Extraction_Validation_Summary.csv`: method-level validation summary.
- `results/Performance_Benchmark.csv`: average measured extraction time.
