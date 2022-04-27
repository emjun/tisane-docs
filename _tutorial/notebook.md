---
title: Using Tisane in a Jupyter Notebook
permalink: /tutorial/notebook/
redirect_from: /tutorial/notebook.html
---

You can create your study design specification, launch the Tisane GUI, and run the model script all inside a Jupyter notebook!

This requires a couple of extra steps, but if you're used to running data analyses in Jupyter notebooks, Tisane will integrate all the more smoothly into
your data analysis workflow.

### Setting up a Jupyter kernel

You will need to make sure that the jupyter notebook can find the dependencies you need, including Tisane and others.

#### With poetry
Make sure you have `ipykernel` added to your `poetry` dependencies, and then
create a kernel for ipython.

```
poetry add ipykernel
poetry run python -m ipykernel install --user --name <MY-KERNEL-NAME>
```

#### With pip and a virtual environment
Make sure you have your virtual environment, or venv, activated. Then run:

```
# install ipykernel
pip install ipykernel
# create the kernel, which is specific to the particualr venv
python -m ipykernel install --name <MY-KERNEL-NAME>
```

### Opening the notebook
Once you've created your kernel, you can run `jupyter notebook`. Open up any notebook, and go to the menu: `Kernel > Change kernel`, and choose `<MY-KERNEL-NAME>` (whatever you called it) from the list.

![You can change the kernel of a Jupyter notebook by going to the menu and choosing Kernel > Change kernel, and then selecting a kernel from the list.](https://github.com/emjun/tisane/raw/main/examples/tutorial_screenshots/change_kernel.png?raw=true)

Then you should be good to go! After importing Tisane in your notebook, all five steps of using Tisane can be completed within the notebook itself.

An example showing the GUI running in a jupyter notebook from `examples/Animal_Science/pigs.ipynb`:

![The Tisane GUI running in the output of the Jupyter notebook examples/Animal_Science/pigs.ipynb](https://github.com/emjun/tisane/raw/main/examples/tutorial_screenshots/query_tisane_in_jupyter.png?raw=true)
