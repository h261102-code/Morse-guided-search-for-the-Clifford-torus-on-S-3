# Morse-guided search for the Clifford torus on S³

Repository: https://github.com/h261102-code/Morse-guided-search-for-the-Clifford-torus-on-S-3

## Setup

Use Python 3.12 and keep the notebook, requirements and result directory in the same project folder.

```bash
python3.12 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
jupyter lab clifford_morse_submission.ipynb
```

Windows PowerShell activation: `.venv\Scripts\Activate.ps1`.

## Reproduce the report experiments

Run `clifford_morse_submission.ipynb` from top to bottom. The submission activation cell immediately before section 9 enables the central experiments and convergence-map families, overriding the initial demo selection. Do not skip it. Optional exploratory refinements and directed extensions are separately selectable.

The enabled protocols include baseline descent, epsilon/lambda ablations, the 165-run k sweep, paired k=5/8 comparisons, geometric/Jacobi validation, neural decomposition, budget pairs, angular tests and initialization maps. Full execution may take many hours on CPU.

To continue in an already initialized kernel, execute the submission activation cell and then sections 9 through the final audit in order. Keep the working directory and `complete_results` unchanged. Matching completed runs are reused; missing runs train. Interrupted partial trajectories restart rather than resume optimizer state.

## Outputs and evidence

`complete_results/checkpoints` stores configuration-keyed metrics and model states; `tables` and `figures` contain generated comparisons and plots. `environment.json` records the runtime. The final execution audit lists expected and available runs. Missing runs are not numerical failures. Controlled conclusions require the complete 165-run family, and budget comparisons require all ten paired runs.

The supplied executed notebook contains a completed five-run demonstration and an accepted asymmetric candidate, but the controlled sweep and maps were incomplete. These outputs are preserved as execution evidence, not proof that the whole suite has been run. Run the required cells and reconcile the report against the exported results before submission.

Gaussian-smoothed maps are descriptive and generated separately by iteration budget. The empirical band is fitted to available data; neither colors nor the band replace the stationarity, regularity, curvature and area acceptance criteria. Spectral diagnostics have discretization and near-zero classification limitations.

## Validation

Notebook code passed syntax checks. The duplicate-key issue in baseline diagnostics was corrected. Full end-to-end numerical validation of the expanded suite remains pending. The report currently includes previous experimental results and the supplied historical heatmap; exact agreement with newly generated results has not yet been established.

After successful reproduction, retain an environment lock:

```bash
python -m pip freeze > requirements-lock.txt
```

For a fresh-environment verification, install that lock and run the same notebook protocols. Publish generated tables and, where practical, trusted model checkpoints to support result inspection without retraining.

## References and assistance

Urbano (1990), *Minimal surfaces with low index in the three-dimensional sphere*; Milnor (1963), *Morse Theory*; E and Zhou (2011), *The gentlest ascent dynamics*; Kingma and Ba (2014/2015), *Adam*.

ChatGPT and DeepSeek assisted with ideas, code and analysis. The author is responsible for verifying the submitted work. Numerical acceptance is approximate Clifford compatibility, not proof of exact geometric identification or universal convergence.
