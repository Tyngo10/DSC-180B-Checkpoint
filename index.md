<div class="gradient-bg">
    <h1>Exploring Genetic Relationships Among Age-Related Diseases</h1>
    <!-- Add other content of your website below this -->
</div>

<style>
.gradient-bg {
    background: linear-gradient(to right, #ff7e5f, #feb47b); /* Adjust the colors as needed */
    padding: 50px; /* Adjust the padding as needed */
    text-align: center;
    color: white; /* Change text color if needed */
}
</style>

# Exploring Genetic Relationships Among Age-Related Diseases

**Authors:**
- Tyler Ngo [tdngo@ucsd.edu](mailto:tdngo@ucsd.edu)
- Ethan Lee [e3lee@ucsd.edu](mailto:e3lee@ucsd.edu)
- John Driscoll [jjdrisco.edu](mailto:jjdrisco.edu)

**Mentor:** Tiffany Amariuta [tamariutabartell@ucsd.edu](mailto:tamariutabartell@ucsd.edu)

## Abstract

In our study, we will be exploring the connections between common genetic diseases, specifically with Alzheimer’s and age-related conditions. We aim to find out which genetic processes are most important for these diseases. To accomplish this, we will use colocalization and gene set enrichment analysis to pinpoint key genes. We’re also digging into large genetic datasets to see how different diseases are linked and which genes are most prevalent. Our main goal is to narrow down the underlying genetics behind Alzheimer’s and related diseases, then comparing them to others that aren’t related to aging. By doing this, we can shed light on what makes these diseases unique. Ultimately, our research allows us to understand aging-related diseases better, helping us prevent and treat them. We hope that we can reinforce current understandings or reveal new relations.

## Introduction

Understanding more about aging-related diseases, such as Alzheimer’s or dementia, is a crucial stepping stone for medical advances and increased prevention. In this study, we take a deeper look into the aforementioned diseases, uncover the underlying genetic factors that define them.

We will use a variety of methods to understand how diseases are connected at the genetic level. The central method in this process, colocalization analysis, is a powerful tool that will allow us to see if numerous different traits share any causal genes. By examining overlapping gene representation between diseases, we can identify these causal genes. Additionally, we employ principal component analysis (PCA) in order to visualize patterns in our genetic datasets. PCA allows us to reduce the dimensionality of complex data matrices and identify clusters, providing valuable insight into the genetic relationships among the targeted diseases.

We will also use gene set enrichment analysis (GSEA) to identify genes within gene sets that have a stronger effect on our phenotype data, in this case our gender data correlating to the 1000G dataset. We can then cross-reference our significant gene results from our colocalization and the GSEA to make notable conclusions.

By implementing these analytical approaches, our study aims to establish a connection between the genetic basis of Alzheimer’s and age-related conditions. By figuring out how diseases are related genetically and finding shared pathways, researchers can determine better treatments for them. Our discoveries can significantly change how age-related diseases are diagnosed, prevented, and treated.

## Methods

### Data Collection and Preprocessing

For the purposes of our study, we were interested in aging-related disease GWAS data, genotype data, gene expression data, and gene set databases. We were able to find relevant GWAS summary statistics for our diseases of interest from the GWAS catalog, genotype and gene expression data from the 1000 Genomes dataset, and gene sets from the Molecular Signatures Database (MSigDB). To use these data sources in our analysis, we had to format, label, normalize, and clean up the datasets using various techniques in Python.

### Gene Set Enrichment Analysis

A crucial aspect of our project is gene set enrichment analysis (GSEA), which we performed on the 1000 Genomes dataset and the Molecular Signatures Database (MSigDB) Hallmark gene set collection. The goal of GSEA is to identify biological pathways or gene sets that are significantly enriched in a gene expression dataset. These pathways are then further explored to uncover their roles in aging-related diseases. To perform GSEA, we configured the software locally and prepared the required inputs. Using a combination of the 1000 Genomes genotype data, phenotype labels, and Hallmark gene sets, we generated enrichment scores among other values for each gene set and individual gene. The results of GSEA are later combined with the biological functions implicated by the colocalization analysis, giving us a comprehensive understanding of the underlying biological pathways and biological mechanisms behind aging-related diseases.

### Colocalization Analysis

We conduct colocalization analysis (COLOC) by utilizing GWAS summary statistics for several aging-related diseases and integrating them with gene expression and genotype data from the 1000 Genomes dataset. By using colocalization, we assess the statistical likelihood of there being a shared causal variant between two independent associations: disease status and the expression of a particular gene. We implemented the analysis using the "coloc" package in R, and ran the analysis in batches due to the large size of the GWAS data. The resulting matrix contains the results of statistical tests, which identify the strength of evidence for colocalization at points of interest in the genotype data.

### Principal Component Analysis

We applied Principal Component Analysis (PCA) to the results matrix from the COLOC analysis which comprises of genes and COLOC summary statistics. PCA serves as a dimensionality reduction technique, which allows for the analysis of potential patterns or relationships within the genotype architecture behind the aging-related diseases of interest. We applied PCA through code configured in Python, allowing us to employ various analysis and visualization techniques. Additionally, we employed clustering to further analyze patterns within the results data, which allowed for the identification of clusters of genetic variants with similar characteristics or affects on aging-related diseases. Combined, the PCA and clustering analysis allowed us to identify patterns in the COLOC data, uncover influential variants, and potentially gain a deeper understanding of the genetic underpinnings of aging-related diseases.
