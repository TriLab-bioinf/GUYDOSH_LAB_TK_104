#### Ticket TK_104

Goal: Add new code to calculate mean normalized read counts per condition

New code added to R script:

```
# Subset DESeq object for 25A treatment and control for WT
dds.one.cds.wt.25A <- dds.one.cds.wt[,dds.one.cds.wt$Inducer %in% c("None", "25A")]
mean_norm_counts.wt.25A <- apply(counts(dds.one.cds.wt.25A, normalized=TRUE), 1, function(x) mean(x))

# Subset DESeq object for polyIC treatment and control for WT
dds.one.cds.wt.pIC <- dds.one.cds.wt[,dds.one.cds.wt$Inducer %in% c("None", "polyIC")]
mean_norm_counts.wt.pIC <- apply(counts(dds.one.cds.wt.pIC, normalized=TRUE), 1, function(x) mean(x))

# Subset DESeq object for polyIC treatment and control for RNAseL KO samples
dds.one.cds.ko.pIC <- dds.one.cds.ko[,dds.one.cds.ko$Inducer %in% c("None", "polyIC")]
mean_norm_counts.ko.pIC <- apply(counts(dds.one.cds.ko.pIC, normalized=TRUE), 1, function(x) mean(x))

``` 
