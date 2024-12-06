# self-editing-correction

This code applies the self-editing correction for base editors as described in the bioRxiv [preprint](https://www.biorxiv.org/content/10.1101/2024.11.12.622254v1) “Activity-based selection for enhanced base editor mutational scanning” by Kaplan et al (2024). The output from this code is a read counts file that can be used for further screen analysis. Sample inputs and outputs are provided using SpG-Cas9-ABE8e activity-based selection condition as described in the preprint.

To use this pipeline, it is first necessary to run [PoolQ](https://portals.broadinstitute.org/gpp/public/software/poolq), developed by the Genetic Perturbation Platform of the Broad Institute of MIT and Harvard, to deconvolute sequencing files. To investigate self-editing, we recommend setting the number of unexpected reads to 1e6. 

### Required Inputs
- condition – 2-column file linking P7 barcode to associated sample 
- reference – 5-column file consisting of sgRNA Target Sequence, Target Gene ID, Target Gene 
Symbol, A-G edits, and C-T edits
- unexpected_count = PoolQ-generated file containing the most frequent (1e6, typically) sgRNA 
sequences that are not found in the reference file.
- counts = PoolQ-generated file containing read counts for each condition. This only includes 
sgRNA sequences that are found in the reference file.

To cite this code, please reference the following publication: “Activity-based selection for enhanced base editor mutational scanning” by Kaplan et al (2024).

## Guide: Replicating this analysis

In terminal, navigate to the folders where your working environment is, and clone this repository

```
git clone https://github.com/ellkap/self-editing-correction.git 
```

Then navigate into that folder

```
cd self-editing-correction
```

Start a virtual environment to install all necessary packages

```
python3 -m venv run-self-editing-correction
source run-self-editing-correction/bin/activate
pip install -r requirements.txt
```

Then begin a jupyter notebook session

```
jupyter notebook
```

Running the command opens a tab in your internet browser. In this tab, select the file “Self_editing_correction-pipeline-Github.ipynb” to open it. 

#### Ensure that the notebook runs correctly in your environment
Navigate to the “Run” dropdown menu, and select “Run all cells”. 
The output generated by this notebook should match what you observe on the [github repository itself](https://github.com/ellkap/self-editing-correction/blob/main/Self_editing_correction-pipeline-Github.ipynb) 

#### Apply the pipeline to your own data 
Upload your input data into this same folder. Change the paths to the sample files in the jupyter notebook to match your input files, and change the column names in the code to match the column names in your data. 
For the code to generate an output csv, uncomment the final line of the juypter notebook (delete the # preceding the line)

Finally, rerun the notebook to complete the analysis on your data. 

