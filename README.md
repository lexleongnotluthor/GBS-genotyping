# GBS-genotyping
Group B Strep (Streptococcus agalactiae) genotyping using ABRicate to understand strain prevalence. This is for the purpose of typing the GBS only, anbd you already have [ABRicate](https://github.com/tseemann/ABRICATE) installed and all you need is simply add the curated [GBS strain reference](https://github.com/swainechen/GBS-SBG). But if you are looking to do specific study on GBS, their serotypes and their resistance profiles, then you might want to check out [GBS-Typer-sanger-nf](https://github.com/sanger-bentley-group/GBS-Typer-sanger-nf). 

## Installation
1. [ABRicate](https://github.com/tseemann/ABRICATE) can be installed using Bioconda
```
conda install -c conda-forge -c bioconda abricate
abricate --check
abricate --list
```
2. Database

## Input
Abricate only takes your genome sequences in FASTA format. 

## Usage

`abricate --db GBS [genome_assembly.fna]`
