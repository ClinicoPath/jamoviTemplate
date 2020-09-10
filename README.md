# jamoviTemplate

# ‘A beginners guide to jamovi modules’ or ‘jamovi modules for dummies’

Official documentation is here: https://dev.jamovi.org/

## TL;DR

Briefly:

- Use this repo as template: `https://github.com/sbalci/jamoviTemplate` to generate a new repo

- Use `R >= 4.0.2`

- Current package repository is: https://cran.microsoft.com/snapshot/2020-08-24

- Install jamovi from this link: https://www.jamovi.org/download.html Get the latest one 1.6.3

- If using mac use this jamovi for development: `https://www.jamovi.org/downloads/jamovi-unsigned.zip`

- Install `jmvtools` package with:

```r
install.packages('jmvtools', repos=c('https://repo.jamovi.org', 'https://cran.r-project.org'))
```


```r
options(repos = c('https://cran.microsoft.com/snapshot/2020-08-24'))

suppressPackageStartupMessages({
  if (!requireNamespace('jmvtools'))
  {
    install.packages('jmvtools',
                     repos = c('https://repo.jamovi.org', 'https://cran.r-project.org'))
  }
})
suppressPackageStartupMessages(library('jmvtools'))

suppressPackageStartupMessages({
  if (!requireNamespace('jmv')) {
    install.packages('jmv', dependencies = TRUE)
  }
})
suppressPackageStartupMessages(library('jmv'))

suppressPackageStartupMessages({
  if (!requireNamespace('jmvconnect')) {
    install.packages('jmvconnect', dependencies = TRUE)
  }
})
suppressPackageStartupMessages(library('jmvconnect'))

suppressPackageStartupMessages({
  if (!requireNamespace('jmvcore')) {
    install.packages('jmvcore', dependencies = TRUE)
  }
})
suppressPackageStartupMessages(library('jmvcore'))

suppressPackageStartupMessages({
  if (!require('devtools')) {
    install.packages('devtools')
  }
})
suppressPackageStartupMessages(library('devtools'))
```






- locate jamovi bin folder via this: `jmvtools::check("C://Program Files//jamovi//bin")` I recommend changing folder name from default `jamovi 1.2` to `jamovi`

- inside this repo folder in R `jmvtools::install()`

- it will produce a file named jamoviTemplate.jmo and install this module to jamovi

- The repo is like an R package except `jamovi` folder. 

- You need to edit `R/...b.R` files.

https://dev.jamovi.org/tuts0104-implementing-an-analysis.html
https://dev.jamovi.org/tuts0105-debugging-an-analysis.html

- run `jmvtools::install()` again.

Let me know how it goes :)

## Add Analysis

```r
jmvtools::addAnalysis(name = 'neofun', title = 'New Function')
```

## using devtools

If you want to use devtools, remove `NAMESPACE` file. 
