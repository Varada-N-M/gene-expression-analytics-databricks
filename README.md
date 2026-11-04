# Gene Expression Analytics Platform using Databricks

## Overview

This project demonstrates an end-to-end gene expression analytics pipeline built using **Databricks, PySpark, Spark SQL, and Delta Lake**.

The project uses publicly available RNA-seq data from NCBI Gene Expression Omnibus (GEO) to explore how hypoxia affects gene expression over time in human kidney organoids.

The data engineering workflow follows the **Medallion Architecture (Bronze, Silver, and Gold)** to transform raw gene expression data into structured analytical datasets.

## Problem Statement

Gene expression datasets contain large numbers of genes and samples. Processing and analyzing these datasets requires reliable data ingestion, transformation, data quality validation, and analytical workflows.

This project explores how Databricks can support scalable processing and analysis of RNA-seq data.

## Dataset

- **Source:** NCBI Gene Expression Omnibus (GEO)
- **GEO Accession:** [GSE236379](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE236379)
- **Study:** Hypoxia Triggers Signatures of Maladaptive Repair in Human Kidney Organoids
- **Genes:** 39,754
- **Samples:** 12
- **Experimental conditions:** Hypoxia and Normal
- **Time points:** Day 20 and Day 25

## Technology Stack

- Databricks
- Apache Spark
- PySpark
- Spark SQL
- Delta Lake
- Python
- SQL

## Architecture

The project follows the Medallion Architecture.

### Bronze Layer
- Ingest raw RNA-seq gene expression data.
- Store the original dataset in Databricks Volumes.

### Silver Layer
- Parse and clean gene expression data.
- Transform the expression matrix from wide format to long format.
- Integrate sample metadata.
- Perform data quality checks.
- Store the processed data as a Delta table.

### Gold Layer
- Aggregate gene expression values.
- Calculate Hypoxia vs Normal expression differences.
- Calculate fold changes and log2 fold changes.
- Classify genes based on their time-dependent response patterns.
- Prepare analytical datasets for visualization.

## Key Results

- Processed 477,048 gene-expression records.
- Analyzed 39,754 genes across 12 samples.
- Identified exploratory hypoxia response patterns:
  - 110 late-induced genes
  - 81 early-induced genes
  - 9 consistently induced genes
- Explored gene-level expression patterns, including MMP7, SPINK1, S100A8, and S100A9.

## Scientific Considerations

The current analysis uses raw gene expression counts and exploratory fold-change calculations.

These results are not statistically validated differential-expression findings. Further work is required, including library-size normalization, statistical testing, multiple-testing correction, and biological pathway analysis.

## Project Objectives

- Explore Databricks for bioinformatics data engineering.
- Implement a Medallion Architecture using Delta Lake.
- Develop data transformation workflows using PySpark and Spark SQL.
- Perform gene-level exploratory analytics.
- Visualize time-dependent gene expression patterns.

## Future Enhancements

- RNA-seq sample quality control.
- Library-size normalization.
- Differential expression analysis using DESeq2.
- Statistical significance testing and FDR correction.
- Gene ontology and pathway enrichment analysis.
- Interactive Databricks SQL dashboards.

## Author

Developed as a hands-on project combining biotechnology, bioinformatics, and data engineering.
