### WARNING ###
# This is a reduced version of the CKDGen consortium round 4 phenotype script. The output is solely intended for the CKDGen consortium round 2 Meta EWAS. 
# Logging isn't fully adjusted.
# These scripts can only be applied for participants above the age of 18. If your study contains children please contact us. (schlosser@imbi.uni-freiburg.de)

Usage instructions

1. Rename the parameters file to reflect your study, e.g.
	"cp params-template params-ARIC"

2. Edit the parameters file to reflect your input file.
   The parameters file itself contains detailed instructions.

3. Generate a tab separated file with the input variables. The following columns are mandatory and all other columns will be ignored:
COLUMN_NAME	DEFINITION
iid		Use your unique participant identifier
male		Code: 1 = male, 0 = female
black		Code: 1 = African or African American ancestry, 0 = any other ancestry
screa		As measured, possible units: mg/dl or μmol/l (units will be specified in the parameter file)
ucrea		As measured, possible units: mg/dl or μmol/l (units will be specified in the parameter file)
ualb		use/convert to unit mg/l
uric_acid	As measured, possible units: mg/dl or μmol/l (units will be specified in the parameter file)

example R code for export:
> tmp <- YOUR_DATA
> colnames(tmp) <- c("iid","age_screa", "male", "black", "screa", "ucrea", "ualb")
> write.table(file="phenodata.txt",tmp, col.names=TRUE, row.names=FALSE, sep="\t")

4. Run the phenotype generation script, passing the parameters file, e.g.
	"./ckdgen-pheno-prep.sh params-ARIC"

5. Output is written both to the screen and to a log file. Please examine
   the output. If there are problems, please try to fix the
   parameters in the parameters file or the data in your input file. 
   If you need assistance, please do not hesitate to contact us (schlosser@imbi.uni-freiburg.de).

For Windows, please use Cygwin and ensure "Rscript" is in your PATH.