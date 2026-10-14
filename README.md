# Moved to bio-evidence

This tool is maintained as [`bio_evidence.dataset_contract`](https://github.com/aarnavbhat23/bio-evidence/blob/main/src/bio_evidence/dataset_contract.py) in [bio-evidence](https://github.com/aarnavbhat23/bio-evidence). The package has one API, one test suite and worked public-data cases.

This repository is unarchived and retains the original standalone prototype, commits and results. The consolidated implementation and worked public-data cases are maintained in bio-evidence. The original standalone documentation is below.

---

# Bio Dataset Contracts

Validate machine-readable dataset contracts for hashes, required metadata, row IDs and split-group separation.

**Status: working research prototype.** The bundled input is a synthetic fixture for exercising code. Its report is not evidence about real biological data or real model performance.

## Try it

Python 3.13 was used for local validation. From this repository:

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
python tool.py examples/input.json --output report.json
python -m unittest discover -s tests -v
```

See [`examples/input.json`](examples/input.json) for a complete input and [`examples/report.json`](examples/report.json) for the actual output from that fixture. [`docs/SCHEMA.md`](docs/SCHEMA.md) describes the fields and interpretation. The report records the input SHA-256. No API key is needed for this demo.

## Contribution and related work

A reproducible preflight that joins data provenance checks with biological split constraints.

Data cards and schema validators already exist. This MVP is a focused offline contract checker. Related primary source: [https://github.com/ArcInstitute/arc-virtual-cell-atlas](https://github.com/ArcInstitute/arc-virtual-cell-atlas). The related-work scan is preliminary; no claim of being the first implementation is made.

## Next experiment

Write contracts for two independently licensed datasets; add contracts to their pipelines; test changes that break row IDs, provenance and group separation.

This milestone is planned, not completed. Preregister splits, metrics and exclusions before inspecting test results. Preserve source licenses and version identifiers when adding external data.

## Why this project

Open-data projects and scientific infrastructure teams. This describes technical relevance, not company affiliation, a hiring prediction or a claim that the company requested the tool.

## Validation

The initial local run passed 5 regression tests and the documented CLI example. CI repeats the core tests and example on Python 3.13. Network/model inference is not run in CI.

## Limitations and authorship

See the schema notes for method-specific limitations. This software has not been independently validated by researchers and does not establish experimental activity, clinical usefulness or model superiority.

Initial implementation and toy fixtures were generated with Codex. Maintainer: Aarnav Bhat. Real-data studies and human review remain future work unless a separately documented result explicitly says otherwise. Code and original synthetic fixtures are MIT licensed; externally sourced datasets and model weights retain their own licenses.

## Contributing

Useful contributions include a small reproducible failure case, an independently reviewed dataset adapter, or a metric correction. Include the input schema, expected behavior and source provenance. Avoid committing personal data, credentials, model caches or data without redistribution rights.
