# Bioinformatics Tools Installation Guide on GitHub Codespaces

This guide provides step-by-step instructions for setting up essential bioinformatics tools using Conda environments.

## Step 1: Initialize Conda Environment
Before installing tools, ensure your Conda environment is ready:
```
bash
conda init bash
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
```
## Step 5: Antimicrobial Resistance Identification (RGI)
RGI (Resistance Gene Identifier) predicts resistomes based on the CARD database.
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
_Note: Using separate environments prevents dependency conflicts between tools._
