# AllofUs-GWAS
This repository contains a series of notebooks for the purpose of better understanding the genetic etiology of diseases and phenotypes using the AllofUs Biobank.  The code is simple and interactable for individuals with limited coding experience.  The notebooks can be used to 
•	Prepare a cohort of individuals for GWAS for any disease or binary trait available within the biobank (1)
•	Generate ancestry principal components for each of five appropriately represented ancestry groups (1.11, 1.12)
•	Perform logistic regression across each group separately (2.11)
•	Meta-analyze the groups together using METAL (2.12)
•	Display the resultant summary statistics (3)
•	Generate and test polygenic risk scores across the AllofUs population (4.1)
•	Use the LDSC function within GenomicSEM to evaluate the heritability of and genetic correlations between different diseases using summary statistics from AllofUs or external biobanks (4.2)
The notebooks also includes code to modify Finngen summary statistics using formulas derived in https://pmc.ncbi.nlm.nih.gov/articles/PMC2790578/, and include them in the meta-analysis, although this is specific to the project for which this repository was developed, and can be ignored (5), as well as code to test PRS performance from scoring files (4), and code to run GWAS using precomputed multi-ancestry principal components (2). 
Notebooks have detailed annotations.  Bolded text in the intro section of any notebook contains links to parameters which I recommend specifying.  The computations involved in running this GWAS are intense- running an ethnically stratified GWAS costs hundreds of dollars.  The primary way to cut costs is to use preemptible workers, but there is an increased chance that any task will fail due to preemptions.  As such, the code generating principal components and running GWAS is written to minimize chances of task failure, and in the event of task failure, to resume with repeating as few tasks as possible.  This is done by performing tasks in smaller chunks and saving to the workspace bucket at several steps in the process. 
This code was specifically developed for understanding meniscus injuries, but as mentioned, can be applied to any binary phenotype. Files can be downloaded from Github and uploaded into the AllofUs Researcher Workbench within a workspace.
