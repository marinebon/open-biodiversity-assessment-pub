 # Open Biodiveristy Assessment
This is a work-in-progress draft of a publication on Open Biodiversity Assessment.
This work will draw on work existing currently under the following repos:

* https://github.com/iobis/pyobis
* https://github.com/marinebon/py-dwc-viz/
* https://github.com/marinebon/obisindicators

## editing workflow
* Edit the qmd or md files in the `content` folder. qmd files can include code (R, Python, Julia) and lots of Quarto markdown bells and whistles (like call-outs, cross-references, auto-citations and much more).
* Add the files to `_quarto.yml`
* github actions will render the files and make them available on the github-pages-powered website.

## technical details
This draft is using Quarto, github actions, and github pages.
The technical framework for this draft was provided by the [NOAA quarto simple](https://github.com/nmfs-opensci/NOAA-quarto-simple) github template repository.

The repo includes a GitHub Action that will build the website automatically when you make changes to the files. The webpage will use the `gh-pages` branch. Serving the website files from this branch is a common way to keep all the website files from cluttering your main branch. 

**Note:** The GitHub Action installs R so you can render qmd files with R code. You will need to edit to install Python or Julia if your qmd uses those instead. If you have substantial computations, you don't want to be re-running all the computations for files that didn't change. Read about the [freeze option](https://quarto.org/docs/publishing/ci.html) for this situation. R users with complex reports with dependencies (so qmd B depends on qmd A or data file A) should be aware of the {targets} package which will help you keep track of files that need to be re-rendered due to changes in dependencies.
