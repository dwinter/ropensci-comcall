---
title       : Rentrez 
subtitle    : getting NCBI data in an R session
author      : David Winter 
job         : Arizona State University
framework   : revealjs       # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

# Rentrez
### Getting NCBI data into your R sessions

David Winter (@theatavism), Arizona State University


--- 

## The NCBI

The NCBI has a lot of data... like a _lot_


<img src='http://upload.wikimedia.org/wikipedia/commons/b/bb/NucleotideSequences_86_87.jpeg' width=300px>

---

## The NCBI

The NCBI has a lot of data... like a _lot_

![genbank_35](http://upload.wikimedia.org/wikipedia/commons/8/86/Genbank63FloppyDisk.jpg)

---


## The NCBI

The NCBI has a lot of data... like a _lot_

![genbank_CDROM](http://upload.wikimedia.org/wikipedia/commons/2/24/Genbank100CD.jpg)

(thanks @yokofakun/wikipedia!)

---


## The NCBI

The NCBI has a lot of data... like a _lot_


```r
load_all("~/src/rentrez")
all_dbs <- entrez_dbs()[-47] #there's always one...
how_many_recs <- function(db)  as.integer(entrez_db_summary(db)["Count"]) 
nrecs <- sapply(all_dbs, how_many_recs)
```

---

## The NCBI 


```r
dotchart(nrecs)
```

![plot of chunk dotchart](assets/fig/dotchart-1.png) 

---

## The NCBI and entrez

[Via the web...](http://www.ncbi.nlm.nih.gov/)

---

## The NCBI and entrez

[..or an API](http://www.ncbi.nlm.nih.gov/books/NBK25501/)

---

## The NCBI and entrez in R

 * Lots of use the API for a few cases
 * `genomes` package in BioC is pretty complete...
 * ...as is `rentrez` which I'm going to talk about

---

## Demo

---

## What's next

[A stable and feature-complete
release](https://github.com/ropensci/rentrez/milestones)

---

## A little help

[ensembl REST in R](https://github.com/dwinter/rensembl)
 


