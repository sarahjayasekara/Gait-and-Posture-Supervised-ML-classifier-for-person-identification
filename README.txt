Flat terrain 0,0 walking trial collection.
Numbering follows source folder name order within each person.
Each numbered folder represents one source recording; processing phases remain together.
Empty source trials and repeated angle datasets were excluded; see trial_manifest.json.
Angle deduplication does not establish that every other signal file is identical or prove statistical independence.
Thenuri has a retained source trial marked device 9 missing.
Madhumini has no eligible flat-terrain source recordings. So she was excluded.
Copied file sizes were verified; all copied CSVs were additionally verified using SHA256.
Original source files were not modified.

Project layout
==============
data/       Participant folders, retaining person/trial/phase organization.
analysis/   Jupyter notebooks, including the historical results notebook.
results/    Generated feature dataset and evaluation/result CSV tables.
trial_manifest.json records original source provenance; its Source paths refer
 to the original collection and are intentionally preserved.

Running notebooks
=================
Start Jupyter from this project root or the analysis folder. Each notebook's
first cell locates the project using trial_manifest.json and defines
PROJECT_ROOT, DATA_ROOT, and RESULTS_DIR. Always run that setup cell first.
After the folder reorganization, restart existing kernels and run from the top
so in-memory paths from the old layout are discarded.

Workflow: 01_data_audit -> 02_eda_patterns -> 03_feature_engineering ->
04_svm_evaluation and 05_pca_svm_model -> 00_results.
The modelling notebooks read results/cycle_features_with_quality.csv.
All generated CSV tables are written to results/ using explicit paths.
Keep measurement CSVs inside their participant trial folders in data/.
Existing notebook outputs are historical outputs retained from before the move;
rerunning the notebooks refreshes any displayed old file paths.
