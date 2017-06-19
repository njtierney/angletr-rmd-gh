# Angletr 2017 workshop: "Reproducible documents with RStudio, Rmarkdown, and GitHub.

**We'd like to hear from you!**

To make sure that we give everyone the best experience at this tutorial, it would be great if you could fill in this survey to tell us about your experience with R and what you are expecting from the tutorial.

https://goo.gl/forms/UgSWdrFgQGTEVJNB3

# Installation of software

You must have the following software installed on your computer in order to participate fully in this workshop. Please do your best to follow the guidelines below.

Please also note that the process of installing this software can sometimes be a bit trying and frustrating. We are here to help, ideally before the conference, as this will be the best use of time (yours and ours). Below I describe the steps for getting started with GitHub, which is also where you can communicate with us if you have any issues installing and running examples. We would strongly prefer you to make use of the facilities in GitHub to contact us, rather than over email as it has two clear benefits:

1. Others who have had similar problems can see what you have done
2. Formatting of code and dialogue is clearer

# Getting started with GitHub

An important part of this workshop will be using github. So you will need to create a GitHub account. Please follow the guidelines for doing so on [chapter 5 from Jenny Bryan's awesome book](http://happygitwithr.com/github-acct.html)

Once you have created an account, feel free to introduce yourself on the [welcome issue](https://github.com/njtierney/angletr-rmd-gh/issues/5).

# Stuck?

If you encounter any problems with installation of any of the software for the workshop, please [open an issue](https://github.com/njtierney/angletr-rmd-gh/issues/new), and we'll do our best to help you.

# installing R and RStudio

You will need to install or update R to the latest version, and make sure you have RStudio.
We expect that you have a version of R 3.1 or greater.

1. Install R from here, selecting your operating system: https://cloud.r-project.org.

Alternatively, for windows and mac, download directly at:
	- Windows: https://cloud.r-project.org/bin/windows/base/R-3.4.0-win.exe
	- Mac: https://cloud.r-project.org/bin/macosx/R-3.4.0.pkg

2. Install RStudio from here: https://www.rstudio.com/products/rstudio/download/

> Note: If you have any problem installing R and/or RStudio, please see the battle tested instructions from Jenny Bryan's book: http://happygitwithr.com/install-r-rstudio.html

# installing rmarkdown

run:
```
install.packages("knitr")
install.packages("rmarkdown")
install.packages("tidyverse")
```

To convert rmarkdown to PDF you will need to install LaTeX.
Note that these installations might take 5-10 minutes, as they are
large files, so make sure you have a good internet connection.

- windows: https://miktex.org/download
- mac:  http://tug.org/cgi-bin/mactex-download/MacTeX.pkg
- linux: https://www.tug.org/texlive/acquire-netinstall.html
