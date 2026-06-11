Bioinformatics Project 4 — Determining a Metagenomic Sample Composition
Repository Structure
project/
├── bioinformatics*final.ipynb # Main notebook
├── BIOINFORMATICS-Project4.docx # Full report
└── README.md
Data
The sequencing reads are available on Google Drive (too large for GitHub):
https://drive.google.com/drive/folders/1gN350988jEr-2mPaDmrmpbm1aFZaevA*
It contains:
reads/ — 5 compressed sequencing reads files (.fastq.gz)
The reference genomes are included in this repository under references/.
Option A — Run on Google Colab (Recommended)
This is the environment the project was developed and tested in.
1.Open bioinformatics_final.ipynb in Google Colab
2.Mount your Google Drive when prompted
3.Make sure the reads folder from Google Drive is accessible under:
/content/drive/Shareddrives/BIOINFORMATICS/reads/
4.Run all cells in order (Runtime → Run all)
All dependencies (BioPython, minimap2) are installed automatically in the first cell.
Option B — Run Locally
Requirements
1.Python 3.x
2.minimap2:

# Linux/Mac

apt-get install minimap2

# or

conda install -c bioconda minimap2
Python dependencies: pip install biopython pandas
Setup
1.Clone this repository
2.Download the reads from the Google Drive link above and place them in a reads/ folder
3.Your folder structure should look like:
project/
├── bioinformatics_final.ipynb
├── references/
│ ├── escherichia_coli.fasta
│ ├── salmonella_enterica.fasta
│ ├── bacillus_lentus.fasta
│ ├── streptococcus_infantis.fasta
│ └── vibrio_mimicus.fasta
└── reads/
├── escherichia_coli.fastq.gz
├── salmonella_enterica.fastq.gz
├── bacillus_lentus.fastq.gz
├── streptococcus_infantis.fastq.gz
└── vibrio_mimicus.fastq.gz
4.Update the paths in the notebook:

# Cell 2

PATH_READS = "./reads"

# Cell 3 & 5

PATH_REFS = "./references/"
5.Comment out the Google Drive mount line in Cell 1: # drive.mount('/content/drive')
6.Run the notebook: jupyter notebook bioinformatics_final.ipynb
