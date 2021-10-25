# CNV_RNA_CCLE
initial mining using code from Liz

This file contains relevant code created by Dr. Elizabeth Brunk, PhD; UNC Chapel Hill Associate Professor of Pharmacology.
THe purpose of the code is to take three files downloaded from Depmap https://depmap.org/portal/download/ 
https://ndownloader.figshare.com/files/29162481 is the sample_info.csv file which contains relevant information on the
cancer cell lines. https://ndownloader.figshare.com/files/29124747 contains the CCLE_expression.csv file. Lastly,
https://ndownloader.figshare.com/files/29125230 contains the CCLE_gene_cn.csv files which contains the copy numbers for each
identified gene in the RNA-seq data. The type of RNA-seq performed by the Broad Institute that generated these data is 
bulk sequencing and not single cell seq. Therefore the longitudinal behavior of the cell populations is not contained in 
these data along with the various line trajectories for distribution studies. 

This file is created in Jupyter notebooks and uses Pandas packages for the data wrangling and matplotlib for the visualization
of the plots. The inital attempt at clustering the cells as having eccDNA is based mainly on the copy number and overall
expression changes (Log2(FC)) of critical oncogenes such as her2, kras, myc, egfr. Tumor suppressor genes are ignored at the
moment. A plot is then made of the gene, for example her2, gene expression on the y axis and gene copy number on the x axis. This 
allows one to visualize all of the cell lines in the two datasets that have expression/copy number differences normalized
from their tissue/cell line type (for the particular individual presumably ? - as this changes from person to person). A
cell line that is likely to contain eccDNA with her2 would have high copy numbers (> 3 arbitrary cutoff) and high expression
(> 4 cutoff). Clustering cells are having high eccDNA potential would take cells at the NE quadrant of the plot. 

Further validation of the cell lines can be made with the chromatin accessibility dataset which would indicate whether 
the gene is in an 'open state' as opposed to heterochromatin. Conversely, the methylation dataset would provide information
on the silencing of the gene to further ensure an open, accessible state for transcription. Enhancers can also be cross
referenced and are well studied for the critical oncogenes listed above - https://www.nature.com/articles/onc2017382. 
