---
title: "Compiling Advanced R to PDF Version"
author: "zhengwei niu"
date: "9/13/2019"
output: pdf_document
---

## Introduction
Use git to clone the source of Hadley Wickham’s Advanced R Programming from his GitHub repository to a local space on your own computer. Build the book using bookdown package.

## Installation
packages:
 'sessioninfo', 'bench', 'desc', 'DBI', 'dbplyr', 'ggbeeswarm', 'rlang', 'testthat', 'sloop', 'RSQLite', 'lobstr', 'tibble', 'profvis'.

## Error
1. I met a 'emo' package error.
- For this problem: I installed 'devtools', then I used devtools::install_github("hadley/emo") to fix this error.

2. I met a fonts problem
- When I start intalling fonts, an error occured which told me that it could not find the package to install the fonts.
Solution: I installed a package called "extrafont"to finish the job. After that, the package was able to provide a function called "font_import" to continue on the fonts job .
```{r}
library("extrafont")
extrafont::font_import(pattern = "Inconsolata")
```

3. I met some running error during the run
- error: 
Warning message:
In system(cmd) : 'make' not found
Quitting from lines 77-84 (Rcpp.Rmd) 
Error in sourceCpp(code = code, env = env, rebuild = rebuild, cacheDir = cacheDir,  : 
  Error 1 occurred building shared library.
Calls: local ... withVisible -> eval -> eval -> cppFunction -> sourceCpp

Execution halted
Error in Rscript_render(f, render_args, render_meta) : 
  Failed to compile Rcpp.Rmd

   Exited with status 1.

- Solution: I added a line of code into introduction.rmd 
```{r, echo=FALSE}
knitr::opts_chunk$set(error = TRUE)
```

Finally after 5 hours' fighting with bugs I got the pdf version of the ADV_R BOOK!
