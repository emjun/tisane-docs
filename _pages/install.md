---
title: "Installing Tisane"
layout: page
---

Welcome to Tisane, a data analysis tool that focuses on supporting conceptual
statistical relationships in study designs. After providing a study design
specification in the Tisane domain-specific language (DSL), the Tisane GUI
guides you through the process of generating an appropriate model.

<!-- ![The Tisane GUI](https://github.com/emjun/tisane/raw/main/examples/tutorial_screenshots/tisane_gui.png?raw=true) -->

The resulting
model is written in Python, and you can run it to get results that answer your
research questions.

 * toc
{:toc}


## Requirements
Tisane requires Python 3.8+ and also an installation of R.

You will need to install the R packages `lme4`, `lmerTest`, and `emmeans`, and also `lazyeval`. (You can do this either by copying the below code into a file and running it using R, run it in RStudio, or you open an R shell and copy and paste the code.)

```R
install.packages(c('lme4','lmerTest','emmeans','lazyeval'));
```

If you have issues with installing all 4 at once, for convenience, here they are individually:

```R
install.packages('lme4');
install.packages('lmerTest');
install.packages('emmeans');
install.packages('lazyeval');
```




## Installing with pip
We recommend using a virtualenv with `pip` to keep your dependencies clean. First, install Tisane using `pip`, in a virtual environment:

```
# create and activate your virtual environment, if you haven't already
# replace <MY-ENV-NAME> with the name of your env
python3 -m venv <MY-ENV-NAME>
source <MY-ENV-NAME>/bin/activate

# install tisane
pip install tisane
```

## Installing with poetry
Equivalently, you could also use [`poetry`](https://python-poetry.org), and add Tisane to your dependencies for your data analysis:

```
poetry add tisane
```

## Installing with conda
```
conda install tisane
```


## Installing R
For convenience, here are several ways you can install R:

### Anaconda
[Anaconda](https://www.anaconda.com/distribution/) is a popular Python data science package manager, that can also be used to install R. This will also install the required R packages.

```
conda install -c conda-forge r r-base r-lmertest r-emmeans rpy2
```

Caution: using conda together with poetry may cause problems with running
models. In that case, you may want to install R in one of the alternative ways.

### Homebrew

```
brew install r
```

### Download it
Visit [this page](https://cran.r-project.org) and select the version for your operating system.

### Download RStudio
RStudio is a popular IDE for developing R scripts. You can download it [here](https://www.rstudio.com/products/rstudio/).
