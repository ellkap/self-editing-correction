# self-editing-correction
This code applies the self-editing correction for base editors as described in the bioRxiv [preprint](https://www.biorxiv.org/content/10.1101/2024.11.12.622254v1) “Activity-based selection for enhanced base editor mutational scanning” by Kaplan et al (2024). The output from this code is a read counts file that can be used for further screen analysis. Sample inputs and outputs are provided using SpG-Cas9-ABE8e activity-based selection condition as described in the preprint.

To use this pipeline, it is first necessary to run [PoolQ](https://portals.broadinstitute.org/gpp/public/software/poolq), developed by the Genetic Perturbation Platform of the Broad Institute of MIT and Harvard, to deconvolute sequencing files. To investigate self-editing, we recommend setting the number of unexpected reads to 1e6. 

A description of the necessary files is below:
<br> condition – 2-column file linking P7 barcode to associated sample 
<br>reference – 5-column file consisting of sgRNA Target Sequence, Target Gene ID, Target Gene 
Symbol, A-G edits, and C-T edits
<br>unexpected_count = PoolQ-generated file containing the most frequent (1e6, typically) sgRNA 
sequences that are not found in the reference file.
<br>counts = PoolQ-generated file containing read counts for each condition. This only includes 
sgRNA sequences that are found in the reference file.

To cite this code, please reference the following publication: “Activity-based selection for enhanced base editor mutational scanning” by Kaplan et al (2024).
