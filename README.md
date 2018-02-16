README-BCGcalc
================

<!-- README.md is generated from README.Rmd. Please edit that file -->

    #> Last Update: 2018-02-16 12:30:01

# BCGcalc

Biological Condition Gradient (BCG) calculator. Peform basic functions
needed for metric calculation and model (tier) assignments.

## Installation

``` r
# Installing just this library (should get all dependancies)
library(devtools) 
install_github("leppott/BCGcalc")
```

The vignette (big help file) isn’t created when installing from GitHub
with the above command. If you want the vignette download the compressed
file from GitHub and install from that file or install with the command
below.

``` r
# Installing just this library (should get all dependancies)
library(devtools) 
install_github("leppott/BCGcalc", force=TRUE, build_vignettes=TRUE)
```

If dependant libraries do not load you can install them separately.

``` r
# Choose a CRAN mirror (dowload site) first (can change number)
chooseCRANmirror(ind=21) 
# libraries to be installed
data.packages = c(                  
                  "devtools"        # install helper for non CRAN libraries
                  ,"installr"       # install helper
                  ,"digest"         # caused error in R v3.2.3 without it
                  ,"dataRetrieval"  # loads USGS data into R
                  ,"knitr"          # create documents in other formats (e.g., PDF or Word)
                  ,"doBy"           # summary stats
                  ,"zoo"            # z's ordered observations, use for rolling sd calc
                  ,"htmltools"      # needed for knitr and doesn't always install properly with Pandoc
                  ,"rmarkdown"      # needed for knitr and doesn't always install properly with Pandoc
                  ,"htmltools"      # a dependency that is sometimes missed.
                  ,"evaluate"       # a dependency that is sometimes missed.
                  ,"highr"          # a dependency that is sometimes missed.
                  ,"rmarkdown"      # a dependency that is sometimes missed.
                  )
                  
lapply(data.packages,function(x) install.packages(x))
```

Additionally Pandoc is required for creating the reports and needs to be
installed separately. Pandoc is installed with RStudio so if you have
RStudio you already have Pandoc on your computer.

``` r
## pandoc
require(installr)
install.pandoc()
```

## Purpose

## Usage

Everytime R is launched the `BCGcalc` package needs to be loaded.

``` r
# load library and dependant libraries
require("BCGcalc")
```

The default working directory is based on how R was installed but is
typically the user’s ‘MyDocuments’ folder. You can change it through the
menu bar in R (File - Change dir) or RStudio (Session - Set Working
Directory). You can also change it from the command
line.

``` r
# if specify directory use "/" not "\" (as used in Windows) and leave off final "/" (example below).
#myDir.BASE  <- "C:/Users/Erik.Leppo/Documents/ProjectName"
myDir.BASE <- getwd()
setwd(myDir.BASE)
```

## Help

Every function has a help file with a working example. There is also a
vignette with descriptions and examples of all functions in the
`BCGcalc` library.

``` r
# To get help on a function
# library(ContDataQC) # the library must be loaded before accessing help
?BCGcalc
```

To see all available functions in the package use the command below.

``` r
# To get index of help on all functions
# library(ContDataQC) # the library must be loaded before accessing help
help(package="BCGcalc")
```

The vignette file is located in the “doc” directory of the library in
the R install folder. Below is the path to the file on my PC. But it is
much easier to use the code below to call the vignette by name. There is
also be a link to the vignette at the top of the help index for the
package.

“C:\\Programs\\R\\R-3.4.3\\library\\ContDataQC\\doc\\ContDataQC\_Vignette.html”

``` r
vignette("BCGcalc_Vignette", package="BCGcalc")
```

If the vignette fails to show on your computer. Run the code below to
reinstall the package and specify the creation of the vignette.

``` r
library(devtools)
install_github("leppott/BCGcalc", force=TRUE, build_vignettes=TRUE)
```
