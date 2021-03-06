
<!-- README.md is generated from README.Rmd. Please edit that file -->

# CDSeq

<!-- badges: start -->

[![Travis build
status](https://travis-ci.com/kkang7/CDSeq_R_Package.svg?branch=master)](https://travis-ci.com/kkang7/CDSeq_R_Package)
<!-- badges: end -->

CDSeq is a complete deconvolution method for dissecting bulk RNA-Seq
data. The input of CDSeq is, ideally, bulk RNA-Seq read counts (similar
to the input format required by DESeq2), and CDSeq will estimate,
simultaneously, the cell-type-specific gene expression profiles and the
sample-specific cell-type proportions, no reference of pure cell line
GEPs or scRNAseq reference is needed for running CDSeq.

For example, if you have a bulk RNA-Seq data, a G by M matrix **A**,
which is a G by M matrix. G denotes the number of genes and M is the
sample size, then CDSeq will output **B** (a G by T matrix) and **C** (a
T by M matrix), where T is the number of cell types, **B** is the
estimate of cell-type-specific GEPs and **C** is the estimate of
sample-specific cell-type proportions.

Importantly, you can ask CDSeq to estimate the number of cell types,
i.e. T, by providing a vector of possible integer values for T. For
example, if the user input for T is a vector, i.e. \(T=\{2,3,4,5,6\}\),
then CDSeq will estimate the most likely number for T.

## Installation

You can install the released version of CDSeq from
[CRAN](https://CRAN.R-project.org) with:

``` r
install.packages("CDSeq")
```

And the development version from [GitHub](https://github.com/) with:

``` r
# install.packages("devtools")
devtools::install_github("kkang7/CDSeq_R_Package")
```

build the vignette with

``` r
# install.packages("devtools")
devtools::install_github("kkang7/CDSeq_R_Package", build_vignettes = TRUE)
```

## Known issue about MacOS installation

It is possible for Mac users to run into some errors when install from
source due to problems of Rcpp compiler tools. Follow the instruction
here may help:
<https://thecoatlessprofessor.com/programming/cpp/r-compiler-tools-for-rcpp-on-macos/>

## Example

This is a basic example:

``` r
library(CDSeq)
## basic example code
result<-CDSeq(bulk_data =  mixtureGEP, 
              cell_type_number = 6, 
              mcmc_iterations = 700, 
              cpu_number=1)
```

## Contact

email: <kangkai0714@gmail.com>
