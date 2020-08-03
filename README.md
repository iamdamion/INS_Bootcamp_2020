
# UT INS Bootcamp 2020
### Visualizing Citation Bias with "Open-Science" Tools

## Overview
In modern research workflows, it is useful to make use of shared and openly available tools. Having an "open science" mindset is helpful in two main ways: (1) It saves time and helps you adhere to best practices in your field without having to "reinvent the wheel" and (2) Developing an open science framework for your research and sharing your tools/code allows for better reproducibility checks in the research community. 

Two very useful tools that we will briefly cover in this demo are [Docker](https://docs.docker.com/get-docker/) and [Jupyter Notebook](https://jupyter.org/). During this bootcamp session, we will demo the use of these tools (with a very brief overview of [Binder](https://mybinder.org/)) while addressing an important topic in the scientific community - the impact of gender bias in scientific citations [Dworkin et al., 2020](https://doi.org/10.1038/s41593-020-0658-y) [1]. 

## Goals for this demo session
1. We will use the [Gender Diversity Statement and Code Notebook (cleanBib)](https://github.com/dalejn/cleanBib) [2], to create a cleaned citation list from your .bib file (or the provided example file). 
2. We will then input that cleaned author list into a tool I developed during the OHBM 2020 Brainhack: [Gender Representation in Citations - circle Visualization](https://github.com/iamdamion/grepCIRCLE) [3] in order to visualize author gender representation of the example publication. 
3. Demonstrate the value of open science tools and encourage you to integrate existing tools/develop your own for all of your future projects and publications. 

## Tasks to complete before demo
Please complete the following tasks before the demo so you can follow along. 
- [ ] Install [Docker](https://docs.docker.com/get-docker/)
- [ ] Sign up at [Gender API](https://gender-api.com/)
  - Once signed in, click "My Account" in the upper right
  - Toward the top on the right, click "View API Key" (or scroll down). 
  - Copy your API key (or remember where it is on this site) as we will need to enter it during the demo.
- [ ] Download this repository as a .zip file (or clone it if you are familiar with github)
  - Unzip all contents into a folder somewhere on your computer called "INSdemo". (We will be working in this folder during the demo)
  
**Optional Pre-Demo Steps**
- [ ] Create a .bib file from your paper or reference manager
  - Word document with reference manager-inserted references [Reference Extractor](https://rintze.zelle.me/ref-extractor/)
  - [Export from Mendeley](https://blog.mendeley.com/2011/10/25/howto-use-mendeley-to-create-citations-using-latex-and-bibtex/)
  - [Export from Zotero](https://libguides.mit.edu/ld.php?content_id=34248570)
  - Use Demo_Reference_List.bib file in this repository
- [ ] Pull Docker image ahead of time.
```
# Run this command after installing Docker. 
# This step will also be covered during demo, but can be used for testing ahead of time if you'd like. 
docker pull iamdamion/demopy:1.0
```

## Demo tasks we will walk through
- [ ] Verify Docker is installed
```
# Verify Docker installation command
docker -h
```
- [ ] Download docker image for demo
```
# Pull demo docker image
docker pull iamdamion/demopy:1.0

# Check if docker image is downloaded/list all local images
docker images
```
- [ ] Verify/Locate Gender API key
- [ ] Verify/Locate .bib file
- [ ] Demo of cleanBIB binder/jupyter notebook to create clean authors list 
  - This takes a few steps and you may need to run it a few times to clean your author list
  - Save time by checking all names in your .bib file only have one first name, one last name, and one initial.
  - Edit author entires that may confuse script/API
  - Edit final output .csv if you are aware of any incorrect or unknown gender guesses from API
- [ ] Demo of grepCIRCLE to create author citation circle visualization
```
# First cd into the demo folder you made (INSdemo)
# For reference: Docker command to run grepCIRCLE.py
docker run --rm -v /$PWD:/app iamdamion/demopy:1.0 python /app/grepCIRCLE.py
```

## References:
> [1] [J. D. Dworkin, K. A. Linn, E. G. Teich, P. Zurn, R. T. Shinohara, and D. S. Bassett, “The extent and drivers of gender imbalance in neuroscience reference lists,” Nat Neurosci (2020). https://doi.org/10.1038/s41593-020-0658-y](https://doi.org/10.1038/s41593-020-0658-y) 

> [2] [D. Zhou, E. J. Cornblath, J. Stiso, E. G. Teich, J. D. Dworkin, A. S. Blevins, and D. S. Bassett (2020, February 17) “Gender diversity statement and code notebook", v1.0, Zenodo, doi:10.5281/zenodo.3672109](https://github.com/dalejn/cleanBib) 

> [3] [D. V. Demeter (2020, June 26) "Gender Representation in Citations - Circle Visualization", v1.0.1, Zenodo, doi:10.5281/zenodo.3909807](https://github.com/iamdamion/grepCIRCLE)
