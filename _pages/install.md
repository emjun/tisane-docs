---
title: "Installing Tisane"
layout: page
---

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
We recommend using a [virtualenv](https://stackoverflow.com/a/54183964) with `pip` to keep your dependencies clean.
Here's how you create and activate a virtualenv.

```bash
# create and activate your virtual environment, if you haven't already
# replace <MY-ENV-NAME> with the name of your env
python3 -m venv <MY-ENV-NAME>
# activate the virtual environment
source <MY-ENV-NAME>/bin/activate
```

Once you have activated the virtualenv, you install Tisane using `pip`.

```bash
# install tisane
pip install tisane
```

As long as your virtualenv is activated, you will be able to run Python scripts that use Tisane with no problems!

## Installing with poetry
Equivalently, you could also use [`poetry`](https://python-poetry.org), and add Tisane to your dependencies for your data analysis:

```bash
poetry add tisane
```

## Installing with conda
```bash
conda install tisane
```


## Installing R
For convenience, here are several ways you can install R:

### Conda
[Anaconda](https://www.anaconda.com/distribution/) is a popular Python data science package manager, that can also be used to install R. This will also install the required R packages.

```
conda install -c conda-forge r r-base r-lmertest r-emmeans rpy2
```

**Caution**: using `conda` together with `poetry` may cause problems with running
models. In that case, you may want to install R in one of the following alternative ways.

### Homebrew

```
brew install r
```

### Download
Visit [this page](https://cran.r-project.org) and select the version for your operating system.

### RStudio
RStudio is a popular IDE for developing R scripts. You can download it [here](https://www.rstudio.com/products/rstudio/). Once you have installed RStudio, you can run the code in [Requirements](#requirements) in the R shell in RStudio.
