# jamoviTemplate

# ‘A beginners guide to [jamovi](https://www.jamovi.org) modules’

Official documentation is here: https://dev.jamovi.org/

## TL;DR

- Use this repo as template: https://github.com/sbalci/jamoviTemplate to generate a new repo

- Use `R >= 4.0.2`

- Current package repository is: https://cran.microsoft.com/snapshot/2020-08-24

- Install jamovi

Get the latest (1.6.3) https://www.jamovi.org/download.html  

If using mac use this: https://www.jamovi.org/downloads/jamovi-unsigned.zip

- Install `jmvtools` package with:

```r
install.packages('jmvtools', repos=c('https://repo.jamovi.org', 'https://cran.r-project.org'))
```

<details>
 <summary>- Install jamovi package family:</summary>

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

</details>

- Locate jamovi bin folder:

windows: `jmvtools::check("C://Program Files//jamovi//bin")` I recommend changing folder name from default `jamovi x.x` to `jamovi`  

mac: `jmvtools::check("~/Applications/jamovi.app")`  


- Inside this repo folder in R run `jmvtools::install()`

- A file named jamoviTemplate.jmo and install this module to jamovi

- The repo is like an R package except `jamovi` folder. 

- You need to edit `R/...b.R` files.

https://dev.jamovi.org/tuts0104-implementing-an-analysis.html  

https://dev.jamovi.org/tuts0105-debugging-an-analysis.html  

- run `jmvtools::install()` again.

Let [me](https://github.com/sbalci) know how it goes :)


## Add Analysis

```r
jmvtools::addAnalysis(name = 'neofun', title = 'New Function')
```

## using devtools

If you want to use devtools, remove `NAMESPACE` file. 


## how jamovi module functions

See: [jamovi working structure](https://docs.google.com/presentation/d/e/2PACX-1vTfA7dL5y_PzY5L-f8FRxaqvKMME5pcDCbXtWk5-FUNCGJyFKpGJEp8ES9rAge0CbI3Gcbi7Emv4e-S/pub?start=true&loop=true&delayms=3000)


## need inspiration?

- all code is available:

https://github.com/jonathon-love/jamovi-library/blob/master/modules.yaml

- check out my codes:

https://github.com/sbalci/ClinicoPathJamoviModule


## how to remove functions?


- delete these files:

.  
└── jamoviTemplate/  
    ├── R/  
        ├── neofun.b.R  
        └── neofun.h.R  
    └── jamovi/  
        ├── neofun.a.yaml  
        ├── neofun.r.yaml  
        └── neofun.u.yaml  




- also delete this portion from `analysis` portion of `jamovi/0000.yaml`

```yaml
  - title: New Function
    name: neofun
    ns: jamoviTemplate
    menuGroup: jamoviTemplate
    menuTitle: New Function
```
