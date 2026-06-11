Bioinformatics Project 4 — Determining a Metagenomic Sample Composition

Repository Structure

project/
├── bioinformatics_final.ipynb    # Main notebook
├── BIOINFORMATICS-Project4.docx  # Full report
└── README.md

Data

The sequencing reads are available on Google Drive (too large for GitHub):
https://drive.google.com/drive/folders/1gN350988jEr-2mPaDmrmpbm1aFZaevA_

It contains:


reads/ — 5 compressed sequencing reads files (.fastq.gz)


The reference genomes are included in this repository under references/.


Option A — Run on Google Colab (Recommended)

This is the environment the project was developed and tested in.


Open bioinformatics_final.ipynb in Google Colab
Mount your Google Drive when prompted
Make sure the reads folder from Google Drive is accessible under:


/content/drive/Shareddrives/BIOINFORMATICS/reads/


Run all cells in order (Runtime → Run all)


All dependencies (BioPython, minimap2) are installed automatically in the first cell.


Option B — Run Locally

Requirements


Python 3.x
minimap2:


bash# Linux/Mac
apt-get install minimap2
# or
conda install -c bioconda minimap2


Python dependencies:


bashpip install biopython pandas

Setup


Clone this repository
Download the reads from the Google Drive link above and place them in a reads/ folder
Your folder structure should look like:


project/
├── bioinformatics_final.ipynb
├── references/
│   ├── escherichia_coli.fasta
│   ├── salmonella_enterica.fasta
│   ├── bacillus_lentus.fasta
│   ├── streptococcus_infantis.fasta
│   └── vibrio_mimicus.fasta
└── reads/
    ├── escherichia_coli.fastq.gz
    ├── salmonella_enterica.fastq.gz
    ├── bacillus_lentus.fastq.gz
    ├── streptococcus_infantis.fastq.gz
    └── vibrio_mimicus.fastq.gz


Update the paths in the notebook:


python# Cell 2
PATH_READS = "./reads"

# Cell 3 & 5
PATH_REFS = "./references/"


Comment out the Google Drive mount line in Cell 1:


python# drive.mount('/content/drive')


Run the notebook:


bashjupyter notebook bioinformatics_final.ipynb
