# ADT Acceptability Reproduction

This repository contains additional materials for reproduction and artifact evaluation of the paper *A Limited Technical Background Is Sufficient for Attack-Defense Tree Acceptability*.

This repository is not intended for redistribution of the complete original artifact package. Instead it provides a more transparent reproduction guide, package dependency details, and a machine-readable discrepancy comparison file derived from the reproduced results.

## Repository Purpose

This repository was prepared as part of an evaluation of research project artifacts. It helps to reproduce the statistical analysis from the original artifact by noting the Python/Jupyter environment needed, the package versions used during reproduction, how to download and arrange the original artifact files, how to run `Statistics.ipynb`, the expected final output location in the notebook, known run-time warnings observed during reproduction, and numerical discrepancies between the paper’s reported values and the reproduced results.

## Original Artifact Source

The original artifact files are available to download from authors’ Zenodo repository:

https://zenodo.org/records/14717343

Original artifact includes files such as:

- `Statistics.ipynb`
- `Survey Data.csv`
- `ADT1.zip`
- `ADT2.zip`
- `ADT3.zip`
- `Small Study (SS).pdf`
- `Large Study (LS).pdf`
- `ADT3 Qualitative Evaluation Rubric.pdf`
- `Lecture Plan.pdf`
- `Lecture Slides.pptx`

This repository does not redistribute original files. Direct download from Zenodo.

## Files in This Repository

This repository contains the following supplementary files:

```text
README.md
requirements.txt
reported_vs_reproduced_discrepancies.csv
SOURCE_NOTE.md
````

### `README.md`

This file explains the purpose of the repository and how to get the original artifact, reproduce the analysis, and interpret the supporting files.

### `requirements.txt`

This file is used to record versions of packages used for reproduction:

```text
notebook==7.2.2
numpy==1.26.4
pandas==2.2.2
pingouin==0.6.1
scipy==1.13.1
```

### `reported_vs_reproduced_discrepancies.csv`

This file contains the numerical difference between the values reported in the paper and the ones reproduced from `Statistics.ipynb` after applying the precision shown in the tables of the paper.

The csv contains three columns:

```text
Discrepancy
Reported Result in Paper
Reproduced Result
```

### `SOURCE_NOTE.md`

This file says that the original artifact files are from the Zenodo repository of the authors and are not relicensed by this repository.

## Reproduction Environment

The reproduction was made with:

```text
Operating system: Windows 11
Environment manager: Anaconda
Notebook interface: Jupyter Notebook 7.2.2
Python version: 3.12.7
```

We used the following non-standard Python packages:

```text
notebook==7.2.2
numpy==1.26.4
pandas==2.2.2
pingouin==0.6.1
scipy==1.13.1
```

## How to Reproduce the Results

### Step 1: Download the Original Artifact

Download original artifact package from Zenodo:

[https://zenodo.org/records/14717343](https://zenodo.org/records/14717343)

### Step 2: Place the Main Files in the Same Directory

Save `Statistics.ipynb` and `Survey Data.csv` to the same local folder.

The notebook assumes the CSV file is in the same folder as the notebook.

### Step 3: Install the Required Packages

Install the packages listed in `requirements.txt`.

Using pip:

```bash
pip install -r requirements.txt
```

Or if you are using Anaconda and these packages have already been installed in the base environment, you can just check the package versions and run the notebook directly.

### Step 4: Open Jupyter Notebook

Open Jupyter Notebook via Anaconda or command line:

```bash
jupyter notebook
```

Then open `Statistics.ipynb`.

### Step 5: Keep the Original Path Setting

If `Statistics.ipynb` and `Survey Data.csv` are located in the same folder, keep the original notebook setting:

```python
PATH = ""
```

In this case, no path modification is needed.

### Step 6: Run the Notebook Sequentially

Run the cells of the notebook from top to bottom.

The last visible statistical output is produced in the `Show Results` section.

The final output is shown in `Show Results`, but earlier cells are required to import packages, define global variables, load `Survey Data.csv`, process derived variables, define statistical test functions, define hypotheses, run statistical tests, and generate the final results.

### Step 7: Compare the Results

Check the values that were still different after applying the displayed precision used in the paper's tables with `reported_vs_reproduced_discrepancies.csv`.

## Known Warning

During reproduction you may see a SciPy runtime warning:

```text
RuntimeWarning: Precision loss occurred in moment calculation due to catastrophic cancellation.
This occurs when the data are nearly identical. Results may be unreliable.
```

The precision loss in the moment calculation is because of catastrophic cancellation. This happens when the data are very similar. The results might not be dependable.

This warning can occur when some of the values being compared are very similar.

This warning during the reproduction process did not stop the notebook execution and did not prevent the final `Show Results` output from being generated.

## Notes on Numerical Comparison

The values printed in the notebook are printed in full precision. The values in the tables of the paper are rounded.

Hence, when comparing to reproduced values, the reproduced values should be rounded to the same displayed precision as the respective paper table.

Some BM statistics and Cohen’s d values may be reverse in sign to the paper.

This appears to be due to the direction of group comparison, e.g. LT--HT vs. HT--LT.

If the p-values and conclusions are the same, then the sign differences do not change the statistical interpretation.

## Source and License Note

The original artifact files were taken from the authors’ Zenodo repository:

[https://zenodo.org/records/14717343](https://zenodo.org/records/14717343)

The original data, notebooks, study material, ADT files, PDFs and slides are owned by the original authors.

This repository does not re-license those original materials, nor distribute the full original artifact package.

This repository contains only extra reproduction instructions and comparison files generated for the artifact evaluation.