# BIOC3301 Report
# "Microbiome analysis of an urban park: assessing composition, diversity, and relevance to future research"
Methods for data analysis of soil metadata.
This Github repository is for the analysis of soil taken from Gordon Square Park in the Autumn of 2017. 

As most of the analysisfor this project was done on the Cirrus high performance computer cluster, batch scripts were made to submit jobs to the cluster.
The files contain several lines of codes starting with #, which are instructions for the HPC job queue. Such as how long the job will run and on how many cores, as well as how much RAM and storage is required.

Analysis was done with the quantitative insights into microbial ecology (QIIME) package. the QIIME config file contains the different override default parameters so they do not need to be hard coded into every script which requires them. The .qiime_config file does it automatically.

The basic pipeline folder contains the code necessary to join Read1 and Read2, (forward and reverse reads), to demultiplex the reads, and to pick OTUs using open reference OTU picking. 

The further analyses folder contains many different scripts to perform further analysis on the data obtained from the basic pipeline code. The cda.pbs script should be run first, as most other scripts in this folder use outputs from this script. Other code in this folder allows for the comparison of the beta diversity using metadata, calculating if there are any statistically significant changes in abundance of specific OTUs (after taxa has been summarized to phyla and class level using summarize_taxa.pbs). Furthermore, the ability to generate heatmaps based on the core microbiome (from core_microbiome_anal.pbs) can be perfromed.

The Excel analyses folder contains all the further analyses done in excel based on the data generated from the previous folders. For example, the alpha diversity of each sample or the most abundant phyla present. Other analysis not from the report includes a comparison of the phyla make-up between sample 515rcbc36 and the average phyla make-up from the other samples.

The maps folder contains a number of the different mapping files and their evolutions, used during the analysis of the data.

The OTU Network/3 year level 2 contains an example of the output file from the otu_network.pbs code in the Further Analysis folder. This data can be used in conjunction with the progarmme Cytoscape to make figures, such as real_edge_table.txt.pdf in the Figures folder.

The Sourcetracker Code and Sourcetracker Python folders are used to do further analysis between the samples collected and the earth microbiome project (EMP). The Sourcetracker Code is run on Cirrus (run batch_sourcetrack.pbs first, then run_sourcetrack.pbs), whereas the Sourcetracker python code was run in Jupyter Notebook for the creation of figures using the output from the Sourcetracker Code files. https://github.com/nameisBaron-MichaelBaron/BIOC3301 was helpful as a starting point for the code which was adapted for this analysis. As well as the heatmaps, pie charts showing the make-up of the different environments for each of our samples is also shown.

Other folders, including "3year compare cagetories results", "3year group significance results", "Cohort 3 compare categories results" and "Cohort 3 group significance results" contain the results from the statistical tests performed using a variety of metrics; adonis, ANOSIM, Spearman's rho, and Kruskall-Wallis. These output files were generated with the code used from the Further Analyses folders (with minor changes to the 3 year code).

The Distance boxplots folder contains the resutls for cohort 3 metadata comparisons, and the three cohort year comparisons. These data were not used in the report but provided here as a reference.

As the analysis code for the three Cohort year data is very similar to the Cohort 3 data analysis, only the basic pipeline is shown for the three cohort data as it is different. Reads were not joined for the three cohort year data and all the forward reads with the different maps for all three years had to be joined. This folder is in the 3 year branch of this repository.

______________________________________________________________________________________________________________________________

# Report Abstract

Only two years ago it was estimated that over 99.9% of microbial species remained unclassified. Yet recent developments have revolutionized microbiology. Advances in culture-independent genomic analyses and next-generation sequencing provide new avenues for identification and analysis. To effectively harness these advancements and enable future research, cataloguing findings is critical.  Leading this is the Earth Microbiome Project (EMP), an endeavour to characterise and catalogue environments by microbial composition. Following their aims, using their database, and these new techniques, we take localised samples from a London park for sequencing, classification and comparison of the soil microbiome. Whilst our results are limited in one year, across a three-year period we find correlations in both diversity and operational taxonomic unit makeup. Moreover, based on comparison with the wider database of EMP soil samples, we find correlations with similar environments, suggesting that this analysis may be additive to large-scale studies, enabling future developments. 
