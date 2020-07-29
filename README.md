
# ISV
Method for predicting probability of pathogenicity of copy number variations (deletions and duplications)
## Description of files

File ```hg38_annotated.tsv``` contains data from ClinVar database (with genome assembly GRCh38) which were annotated by AnnotSV tool. Annotations from AnnotSV tool are divided to 'full' and 'split' records (can be find under attribute 'AnnotSV_type'): 'full' represents annotated CNV and 'split' represents annotated genes overlapped by CNVs. 72 attributes added by AnnotSV are gathered from various databases (e.g. IMH, 1000 Genomes project, OMIM, ExAC and Database of Genomic Variants) and each of these attributes is described in documentation to AnnotSV tool: https://lbgi.fr/AnnotSV/Documentation/README.AnnotSV_latest.pdf 
Aggregating some of attributes from gene's records overlapped by CNVs, we created new attributes (descriptions of creating new attributes are shown in publication Automated prediction of the clinical impact of structural copy number variations [?]).
After testing various algorithms for prediction models and with help of recursive elimination and coefficient of the feature importances in the decision function we found appropriate attributes, which we use to predict pathogenicity and benignity of CNVs.

Folder ```deletions_data``` contains dataset used for training and testing classification (predicting) model on deletions.
Training and testing data are divided to ```X_train_del.tsv``` and ```X_test_del.tsv``` which is feature vectors and ```y_train_del.tsv``` and ```y_test_del.tsv``` which contains clinical significance of deletions \*.

Folder ```duplications_data``` contains dataset used for training and testing classification (predicting) model on duplications.
Training and testing data are divided to ```X_train_dup.tsv``` and ```X_test_dup.tsv``` which is feature vectors and ```y_train_dup.tsv``` and ```y_test_dup.tsv``` which contains clinical significance of duplications \*. 
\* clinical significance of CNVs is collected from ClinVar database (https://www.ncbi.nlm.nih.gov/clinvar/)

Folder ```results``` contains:
Graphs:
- ```summary_accuracy_dup_del_bar.html``` - comprise differences between accuracy of various prediction models  
- ```summary_precision_dup_del_bar.html``` - comprise differences between precision of various prediction models

Tables:
- ```summary_metrics_del.csv``` - contains summary of metrics from different prediction model ran on deletions
- ```summary_metrics_dup.csv``` - contains summary of metrics from different prediction model ran on duplications
Summary of metrics - there can be seen differences in metrics between prediction models (metrics  contains counts of True Positives predictions (TP), True Negatives predictions (TN), False Positives predictions (FP), False Negative predictions (FN), counts of Condotion Positives and Condition Negatives, Accuracy, Precision, Specificity, Sensitivity and others.

## Licence 
[Creative Commons Attribution Share Alike 4.0 International](https://choosealicense.com/licenses/cc-by-sa-4.0/)

