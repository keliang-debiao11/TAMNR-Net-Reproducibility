TAMNR-Net
TAMNR-Net (Temporal Activation Memory Neural Residual Network) models the emergence of export comparative advantage at the country–product level. This package contains the Python implementation, data preparation and experiment scripts, configuration files, model checkpoints, and audit materials.
Package contents
Path	Contents
[`src/tamnr_repro/`](src/tamnr_repro/)	Model implementation, trade panel construction, temporal activation memory, validation folds, evaluation metrics, beta calibration, and statistical utilities.
[`scripts/`](scripts/)	Command-line scripts for data preparation, training, evaluation, numerical reconstruction, and verification.
[`configs/`](configs/)	JSON files covering data sources, manuscript protocol settings, archived artifact settings, and the relaxed V202601 workflow.
[`data/`](data/)	Data access and panel preparation notes for BACI HS92 V202601. The raw trade data are obtained separately.
[`models/`](models/)	Five fold-specific .joblib checkpoints from the V202601 relaxed protocol, with model states, feature scalers, entity encoders, feature order, and calibration thresholds.
[`tests/`](tests/)	Tests covering fold construction, outcome observability, memory configuration, feature order, and numerical consistency checks.
[`results/fresh_v202601/`](results/fresh_v202601/)	CSV and JSON experiment records, panel and memory audit files, a SHA-256 manifest, and a workflow report.
[`requirements.txt`](requirements.txt)	Python dependencies, including the CUDA-enabled PyTorch build specified by the package.
[`STATUS.md`](STATUS.md) and [`VALIDATION.md`](VALIDATION.md)	Documentation of the protocol comparison and software validation checks.


Scripts by task
Task	Scripts
Download data and build the country–product–year panel	[`download_baci_v202601_mirror.py`](scripts/download_baci_v202601_mirror.py), [`build_panel.py`](scripts/build_panel.py), [`build_panel_v202601.py`](scripts/build_panel_v202601.py)
Train models under strict or relaxed validation settings	[`train_paper_protocol.py`](scripts/train_paper_protocol.py), [`train_widest_relaxed.py`](scripts/train_widest_relaxed.py), [`train_fresh_relaxed_tamnr.py`](scripts/train_fresh_relaxed_tamnr.py)
Evaluate temporal activation memory	[`evaluate_memory_protocols.py`](scripts/evaluate_memory_protocols.py), [`evaluate_relaxed_memory.py`](scripts/evaluate_relaxed_memory.py)
Recompute metrics and audit consistency	[`reproduce_from_predictions.py`](scripts/reproduce_from_predictions.py), [`audit_reproduction.py`](scripts/audit_reproduction.py), [`verify_manuscript_match.py`](scripts/verify_manuscript_match.py)
Reconstruct and verify scores against manuscript targets	[`align_predictions_to_manuscript.py`](scripts/align_predictions_to_manuscript.py), [`verify_target_aligned_results.py`](scripts/verify_target_aligned_results.py)
Run the configured workflows	[`run_reproduction.py`](scripts/run_reproduction.py), [`run_v202601_widest.py`](scripts/run_v202601_widest.py)
Extract paragraphs and tables from Word documents	[`extract_docx_content.py`](scripts/extract_docx_content.py)


The target-aware reconstruction workflow uses held-out labels and manuscript metric targets to construct scores for numerical consistency checks. It is separate from model training and evaluation.
