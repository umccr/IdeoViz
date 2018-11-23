---
title: "IdeoViz"
author: "Ayesha"
date: "16 November 2018"
output: 
  html_document:
    keep_md: yes
---



## R Markdown

This is an R Markdown document. Markdown is a simple formatting syntax for authoring HTML, PDF, and MS Word documents. For more details on using R Markdown see <http://rmarkdown.rstudio.com>.

When you click the **Knit** button a document will be generated that includes both content as well as the output of any embedded R code chunks within the document. You can embed an R code chunk like this:


```r
require(IdeoViz)
require(RColorBrewer)
```


```r
data(binned_multiSeries)
ideo <- getIdeo("hg18")
head(ideo)
```

```
##   chrom chromStart chromEnd   name gieStain
## 1  chr1          0  2300000 p36.33     gneg
## 2  chr1    2300000  5300000 p36.32   gpos25
## 3  chr1    5300000  7100000 p36.31     gneg
## 4  chr1    7100000  9200000 p36.23   gpos25
## 5  chr1    9200000 12600000 p36.22     gneg
## 6  chr1   12600000 16100000 p36.21   gpos50
```

```r
plotOnIdeo(chrom=seqlevels(binned_multiSeries), # which chrom to plot?
           ideoTable=ideo, # ideogram name
           values_GR=binned_multiSeries, # data goes here
           value_cols=1, # col to plot
           col=brewer.pal(n=5, 'Spectral'), # colours
           # val_range=c(0,3),
           plotType = 'rect', # set y-axis range
           ylab="array intensities",
           plot_title="Trendline example")
```

![](report_files/figure-html/plot1-1.png)<!-- -->

```r
plotOnIdeo(chrom=seqlevels(binned_multiSeries), # which chrom to plot?
           ideoTable=ideo, # ideogram name
           values_GR=binned_multiSeries, # data goes here
           value_cols=2, # col to plot
           col=brewer.pal(n=5, 'Spectral'), # colours
           # val_range=c(0,3),
           plotType = 'rect', # set y-axis range
           ylab="array intensities",
           plot_title="Trendline example")
```

![](report_files/figure-html/plot1-2.png)<!-- -->


```r
data(binned_singleSeries)
data(hg18_ideo)
plotOnIdeo(chrom = seqlevels(binned_singleSeries),
ideo = hg18_ideo,
values_GR = binned_singleSeries,
value_cols = colnames(mcols(binned_singleSeries)),
plotType = 'rect',
col = 'pink',
vertical = T,
val_range = c(-1,1), ylab = "dummy score",
plot_title ="Discretized example")
```

```
## Plot chromosome done
```

<<<<<<< HEAD
```
## Plot chromosome done
```

```
## Plot chromosome done
```

![](report_files/figure-html/plot 2-1.png)<!-- -->


```r
data("binned_fullGenome")
plotOnIdeo(chrom = seqlevels(binned_fullGenome),
           ideo = ideo,
           values_GR = binned_fullGenome,
           value_cols = colnames(mcols(binned_fullGenome)),
           plotType = 'rect',
           col = 'orange', addScale = F,
           plot_title = "Whole genome view",
           val_range = c(-1,1),
           cex.axis = 0.5,
           chromName_cex = 0.6)
```

![](report_files/figure-html/Whole genome view-1.png)<!-- -->

=======

>>>>>>> 25fb1dc0ca49f8e43c071d6904bc9488c8685764
