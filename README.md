# BIOC3301-report
Methods for data analysis of soil metadata.
This Github repository is for the analysis of soil taken from Gordon Square Park in the Autumn of 2017. 

As most of the analysisfor this project was done on the Cirrus high performance computer cluster, batch scripts were made to submit jobs to the cluster.
The files contain several lines of codes starting with #, which are instructions for the HPC job queue. Such as how long the job will run on how many cores, how much RAM and storage is required.

Analysis was done with the quantitative insights into microbial ecology (QIIME) package

The basic pipeline folder contains the code necessary to join Reads 1 and 2, (forward and reverse reads), to demultiplex the reads, and to pick OTUs using open reference OTU picking. 

The further analyses folder contains many different scripts to perform further analysis on the data obtained from the basic pipeline code. first the cda.pbs script should be run as most other scripts in this folder use outputs from this script. Other code in this folder allows for the comparison of the beta diversity using metadata, calculating if there are any statistically significant changes in abundance of specific OTUs (after taxa has been summarized to phyla and class level using summarize_taxa.pbs). Furthermore, the ability to generate heatmaps based on the core microbiome (from core_microbiome_anal.pbs) can be perfromed.

The Excel analyses folder contains all the further analyses done in excel based on the data generated from the previous folders. 
