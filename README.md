# Bioinformatics Tools Installation Guide on GitHub Codespaces

This guide provides step-by-step instructions for setting up essential bioinformatics tools using Conda environments.

## Step 1: Initialize Conda & Configure Channels (Crucial!)

Before installing tools, you MUST configure the channels to ensure Conda finds the correct bioinformatics packages.

```bash
conda init bash
# Important: Run these in order to set channel priority
conda config --add channels defaults
conda config --add channels conda-forge
conda config --add channels bioconda
conda config --set channel_priority strict

# Restart your terminal after running this
```
## **Step 2: Quality Control (QC) Environment**
This environment includes tools for raw data filtering and quality assessment.
Tools: ```fastp```, ```FastQC```
```
Bash
conda create -n qc_env -c bioconda fastp fastqc -y
# To use: conda activate qc_env
```
## Step 3: Genome Assembly and Evaluation
This environment is used for de novo assembly and checking assembly completeness.
Tools: ```SPAdes```, ```BUSCO```, ```QUAST```
```
Bash
conda create -n assembly_env -c bioconda spades busco quast -y
# To use: conda activate assembly_env
```
## Step 4: Genome Annotation with Prokka
Prokka is used for rapid prokaryotic genome annotation.
```
Bash
conda create -n prokka_env -c bioconda prokka -y
# Setup database: prokka --setupdb
# To verify: prokka --version
```
## Step 5: Antimicrobial Resistance Identification (RGI)
RGI (Resistance Gene Identifier) predicts resistomes based on the CARD database.
# To verify: virulencefinder.py -h
```
Bash
conda create -n rgi_env -c bioconda rgi -y
```
## Step 6: Virulence Factor Identification
VirulenceFinder is used to identify virulence genes in bacterial genomes.
```
Bash
conda create -n vf_env -c bioconda virulencefinder -y
```
## Final Check: Verify All Environments

After completing all steps, run the following command to see your list of environments:

```bash
conda env list
```
_Note: Using separate environments prevents dependency conflicts between tools._
