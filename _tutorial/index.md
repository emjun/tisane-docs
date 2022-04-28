---
title: Using Tisane
permalink: /tutorial/home/
redirect_from: /tutorial/index.html, /tutorial/
layout: tutorial
---
Welcome to Tisane, a data analysis tool that focuses on supporting conceptual
statistical relationships in study designs. After providing a study design
specification in the Tisane domain-specific language (DSL)

```python
import tisane as ts
import pandas as pd

df = pd.read_csv("pigs.csv")

week = ts.SetUp("Time", order=[1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12], cardinality=12)
pig = ts.Unit("Pig", cardinality=72)  # 72 pigs
litter = ts.Unit("Litter", cardinality=21)  # 21 litters
vitamin_e = pig.ordinal(
    "Evit", order=["Evit000", "Evit100", "Evit200"], number_of_instances=1
)
copper = pig.ordinal("Cu", order=["Cu000", "Cu035", "Cu175"], number_of_instances=1)
weight = pig.numeric("Weight", number_of_instances=week)
feed = pig.numeric("Feed consumption", number_of_instances=week)

week.causes(weight)
pig.nests_within(litter)

design = ts.Design(dv=weight, ivs=[week]).assign_data(df)

ts.infer_statistical_model_from_design(design=design)
```

the Tisane GUI
guides you through the process of generating an appropriate model.

![The Tisane GUI](https://github.com/emjun/tisane/raw/main/examples/tutorial_screenshots/tisane_gui.png?raw=true)

The resulting
model is written in Python, and you can run it to get results that answer your
research questions.

## Authoring a Model

There are five steps to authoring your model:

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
