# Computational Cognitive Neuroscience

Assignment notebooks for the University of Edinburgh course **[Computational Cognitive Neuroscience](https://www.drps.ed.ac.uk/current/dpt/cxinfr11233.htm)**. The assignments explore neural population dynamics and computational modelling of behavioural data using Python.

## Assignments

### Assignment 1: Stimulus quenching of neural variability in an SSN

`Assignment_1_StimulusQuenchingNeuralVariabilityInSSN.ipynb` simulates a stabilised supralinear network (SSN) with excitatory and inhibitory populations. It explores the transfer function, membrane potentials and firing rates, the effects of feedforward input strength and Gaussian noise, and how input strength affects response variability.

### Assignment 2: Computational modelling of behavioural data

`Assignment_2_ComputationalModellingBehaviouralData.ipynb` analyses instrumental choices, outcomes, and STAI-Y2 scores. It includes learning-model simulations, likelihood-based parameter fitting, group comparisons, parameter recovery, alternative models, AIC/BIC model comparison, and model recovery with confusion matrices.

## Data

The following headerless CSV files are included and are read by Assignment 2:

| File | Contents |
| --- | --- |
| `inst_choices.csv` | Participant choices across trials; options are encoded as 1 and 2. |
| `inst_outcomes.csv` | Trial outcomes encoded as 0 and 1. |
| `stai_scores.csv` | Participant STAI-Y2 scores. |

Keep these files beside the notebooks. The analysis uses corresponding participant rows across the three files.

## Setup

Use Python 3.10 or 3.11 for the dependency ranges provided here. The original notebooks record Python 3.9 in their metadata; the requirements describe a compatibility-oriented environment, not an exact reconstruction of the original installation.

Open a terminal in this folder and create an isolated environment.

**Windows PowerShell:**

```powershell
py -3.11 -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe -m jupyterlab
```

**macOS / Linux:**

```bash
python3.11 -m venv .venv
.venv/bin/python -m pip install -r requirements.txt
.venv/bin/python -m jupyterlab
```

These commands use the environment directly, so activation is unnecessary. If using Python 3.10, replace `py -3.11` with `py -3.10`, or `python3.11` with `python3.10`.

The requirements include NumPy, pandas, Matplotlib, SciPy, and tqdm, plus JupyterLab and its Python kernel. NumPy and pandas are constrained below version 2 to preserve older behaviour used in the notebooks, including DataFrame reductions in Assignment 2. Python standard-library modules require no separate installation.

## Running the notebooks

1. Launch JupyterLab from this folder using the command above.
2. Open either assignment and select the Python 3 kernel.
3. Run cells in order from top to bottom; later cells depend on earlier variables and functions. Restart the kernel before a fresh complete run.

Plots and numerical results appear inside the notebooks. Assignment 1 generates many plots, and Assignment 2 includes repeated simulations and optimisation loops that may take time to finish.

The notebooks use random sampling, so reruns can produce different results. For repeatable runs within the same environment, set a NumPy random seed immediately after the imports before executing the remaining cells.

