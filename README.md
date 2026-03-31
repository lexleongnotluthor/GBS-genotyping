# GBS-genotyping
Group B Strep (Streptococcus agalactiae) genotyping using ABRicate to understand strain prevalence. This is for the purpose of typing the GBS only, anbd you already have [ABRicate](https://github.com/tseemann/ABRICATE) installed and all you need is simply add the curated [GBS strain reference](https://github.com/swainechen/GBS-SBG). But if you are looking to do specific study on GBS, their serotypes and their resistance profiles, then you might want to check out [GBS-Typer-sanger-nf](https://github.com/sanger-bentley-group/GBS-Typer-sanger-nf). 

## Installation
1. [ABRicate](https://github.com/tseemann/ABRICATE) can be installed using Bioconda
```
conda install -c conda-forge -c bioconda abricate
abricate --check
abricate --list
```
2. GBS-SBG Database
- Download [GBS-SBG.fasta](https://github.com/swainechen/GBS-SBG/GBS-SBG.fasta) from GBS-SBG or from here.
- Make sure you have `BLAST+`, otherwise you can install BLAST+ using `conda`.
```
conda install bioconda::blast
```
- Move the fasta into a directory within your `miniconda3/envs/pkg/db`
- Run `makeblastdb` as below
```
makeblastdb -dbtype nucl -in /{miniconda3/envs/pkg/db}/GBS/GBS-SBG.fasta -out /{miniconda3/envs/pkg/db}/GBS/sequences
```

## Input
Abricate only takes your genome sequences in FASTA format. 

## Usage
1. Running serotyping per sample.
```
abricate --db GBS [genome_assembly.fna] > sample_result_1.tab
```
2. Compiling all the data into 1 `summary.csv` file
``` 
abricate --summary sample_result_*.tab > summary.tab
```

