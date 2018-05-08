# BIOC3301-report
Methods for data analysis of soil metadata.
This Github repository is for the analysis of soil taken from Gordon Square Park in the Autumn of 2017. 

As most of the analysisfor this project was done on the Cirrus high performance computer cluster, batch scripts were made to submit jobs to the cluster.
The files contain several lines of codes starting with #, which are instructions for the HPC job queue. Such as how long the job will run on how many cores, how much RAM and storage is required.

Analysis was done with the quantitative insights into microbial ecology (QIIME) package. the QIIME config file contains the different parameters changed to default so they do not need to be hard coded into every script which requires them. The .qiime_config file does it automatically.

The basic pipeline folder contains the code necessary to join Reads 1 and 2, (forward and reverse reads), to demultiplex the reads, and to pick OTUs using open reference OTU picking. 

The further analyses folder contains many different scripts to perform further analysis on the data obtained from the basic pipeline code. first the cda.pbs script should be run as most other scripts in this folder use outputs from this script. Other code in this folder allows for the comparison of the beta diversity using metadata, calculating if there are any statistically significant changes in abundance of specific OTUs (after taxa has been summarized to phyla and class level using summarize_taxa.pbs). Furthermore, the ability to generate heatmaps based on the core microbiome (from core_microbiome_anal.pbs) can be perfromed.

The Excel analyses folder contains all the further analyses done in excel based on the data generated from the previous folders. For example, the alpha diversity of each sample or the most abundant phyla present. Other analysis not from the report includes a comparison of the phyla make-up between sample 515rcbc36 and the average phyla make-up from the other samples.

The maps folder contains a number of the different mapping files and their evolutions used during the analysis of the data.

The OTU Network/3 year level 2 contains an example of the output file from the otu_network.pbs code in the Further Analysis folder. This data can be used in conjunction with the progarmme Cytoscape to make figures such as real_edge_table.txt.pdf in the Figures folder.

The Sourcetracker Code and Sourcetracker Python folders are used to do further analysis between the samples collected and the earth microbiome project (EMP). The Sourcetracker Code is run on Cirrus (run batch_sourcetrack.pbs first, then run_sourcetrack.pbs), whereas the Sourcetracker python code was run in Jupyter Notebook for the creation of figures using the output from the Sourcetracker Code files. https://github.com/nameisBaron-MichaelBaron/BIOC3301 was helpful in assembling the code which was adapted for the code in these folders.
