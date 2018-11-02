[![License: AGPL v3](https://img.shields.io/badge/License-AGPL%20v3-blue.svg)](https://www.gnu.org/licenses/agpl-3.0) 
[![lifecycle](https://img.shields.io/badge/lifecycle-maturing-blue.svg)](https://www.tidyverse.org/lifecycle/#maturing) 
[![Travis CI](https://travis-ci.org/bnasr/xROI.svg?branch=master)](https://travis-ci.org/bnasr/xROI) 
[![Coverage status](https://codecov.io/gh/bnasr/xROI/branch/master/graph/badge.svg)](https://codecov.io/github/bnasr/xROI?branch=master) 
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1204366.svg)](https://doi.org/10.5281/zenodo.1204366) 
[![CRAN status](http://www.r-pkg.org/badges/version-last-release/xROI)](https://cran.r-project.org/package=xROI) 
[![Downloads](http://cranlogs.r-pkg.org/badges/xROI?color=brightgreen)](http://www.r-pkg.org/pkg/xROI) 
[![Downloads](http://cranlogs.r-pkg.org/badges/grand-total/xROI?color=brightgreen)](http://www.r-pkg.org/pkg/xROI) 


# xROI:  
## Delineate Region of Interests (ROI's) and Extract Time-Series Data from Digital Repeat Photography Images


Here, we present an interactive open-source toolkit, called xROI[^*], that facilitates the process of time-series extraction and improves the quality of the final data. xROI provides a responsive environment for scientists to interactively:

a) delineate regions of interest (ROI), 
b) handle field of view (FOV) shifts, 
c) extract and export time series data characterizing color-based metrics.

Using `xROI`, the user can detect FOV shifts with minimal difficulty. The software gives user the opportunity to re-adjust mask files or redraw new ones every time an FOV shift occurs.

### Design
R language and Shiny package were used as the main development tool for xROI, while Markdown, HTML, CSS and JavaScript languages were used to smoothen the interactivity. While Shiny apps are primarily used for web-based applications to be used online, we used Shiny for its graphical user interface capabilities. In other words, both UI and server modules are run locally from the same machine and hence no internet connection is required. The xROI’s UI element presents a side-panel for data entry and three main tab-pages, each responsible for a specific task. The server-side element consists of R and shell scripts. Image processing and geospatial features were performed using the `Geospatial Data Abstraction Library (GDAL)` and the `rgdal` and `raster` R packages. 


### Installation
The xROI R package has been published on The Comprehensive R Archive Network (CRAN). The latest tested xROI package can be installed from the <a href="https://cran.r-project.org/package=xROI">CRAN packages repository</a> by running the following command in an R environment:

```{r, echo=TRUE, eval=FALSE}

utils::install.packages('xROI', repos = "http://cran.us.r-project.org" )

```

Alternatively, the latest beta release of xROI can be directly downloaded and installed from the GitHub repository:
```{r, echo=TRUE, eval=FALSE}

# install devtools first
utils::install.packages('devtools', repos = "http://cran.us.r-project.org" )

devtools::install_github("bnasr/xROI")

```

xROI depends on many R packages including: `raster`, `rgdal`, `sp`, `jpeg`, `tiff`, `shiny`, `shinyjs`, `shinyBS`, `shinyAce`, `shinyTime`, `shinyFiles`, `shinydashboard`, `shinythemes`, `colourpicker`, `rjson`, `stringr`, `data.table`, `lubridate`, `plotly`, `moments`, and `RCurl`. All the required libraries and packages will be automatically installed with installation of xROI. The package offers a fully interactive high-level interface as well as a set of low-level functions for ROI processing. 


### How to Launch `xROI`

A comprehensive user manual for low-level image processing using xROI is available from <a href="https://cran.r-project.org/package=xROI/xROI.pdf">xROI.pdf</a>. While the user manual includes a set of examples for each function; here we explain the graphical interactive mode. The interactive mode can be launched from an interactive R environment by the following command.

```{r, echo=TRUE, eval=FALSE}

library(xROI)
Launch()

```

or form the command line (e.g. shell in Linux, Terminal in macOS and Command Prompt in Windows machines) where an R engine is already installed by:

```{r, echo=TRUE, eval=FALSE}

Rscript -e “xROI::Launch(Interactive = TRUE)”

```

Calling the Launch function opens up the app in the system’s default web browser, offering an example dataset to explore different modules or upload a new dataset of images. 



[^*]: The R package is developed and maintained by <a href="https://bnasr.github.io/">Bijan Seyednarollah</a>. Most recent release is available from: https://github.com/bnasr/xROI
