---
title: Using Tisane
permalink: /tutorial/home/
redirect_from: /tutorial/index.html
layout: tutorial
---
Tisane is a tool for authoring generalized linear models. There are five steps to
authoring your model:

1. Specify your **variables** of interest and their **relationships.**
2. Create a study design `tisane.Design` with your variables.
3. Ask Tisane to help you author a statistical model by calling `tisane.infer_statistical_model_from_design` on your study design. Tisane will then examine your variables and variable relationships, look for additional variables that may be conceptually relevant to add, and ask you specific questions about them and the data through a GUI.
<!-- You can decide whether or not to use those variables, and also choose family and link functions, in a GUI that is launched.  -->
4. After you these additional choices, the GUI will generate a model script written in Python.
5. After running the script, the results of the model will be output so that you can examine them.

There are two different workflows for using Tisane: using Tisane in a Jupyter notebook, and using Tisane with the editor of your choice and the command line.

## Additional Resources

You might want to check out the [documentation](https://docs.tisane-stats.org) for more information, in addition to the examples below.

## Examples

Examples can be found in the `examples` directory. There are three main examples, each of which has both a Python script version and a Jupyter notebook version.

 - `examples/Animal_Science`:
   - [`pigs.py`](https://github.com/emjun/tisane/raw/main/examples/Animal_Science/pigs.py) or [`pigs.ipynb`](https://github.com/emjun/tisane/raw/main/examples/Animal_Science/pigs.ipynb)
 - `examples/Exercise`:
   - [`exercise_simple.py`](https://github.com/emjun/tisane/raw/main/examples/Exercise/exercise_simple.py) or [`exercise_simple.ipynb`](examples/Exercise/exercise_simple.ipynb)
 - `examples/Group_Exercise`:
   - [`exercise_group.py`](https://github.com/emjun/tisane/raw/main/examples/Group_Exercise/exercise_group.py) or [`exercise_group.ipynb`](https://github.com/emjun/tisane/raw/main/examples/Group_Exercise/exercise_group.ipynb)
   - [`exercise_group_age_added.py`](https://github.com/emjun/tisane/raw/main/examples/Group_Exercise/exercise_group_age_added.py) or [`exercise_group_age_added.ipynb`](https://github.com/emjun/tisane/raw/main/examples/Group_Exercise/exercise_group_age_added.ipynb)

Now that you've installed Tisane, you should be able to run the examples!

The notebook versions include extra explanations and information that you may find useful as an introduction to Tisane.
