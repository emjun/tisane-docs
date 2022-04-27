---
title: Using Tisane with the Command Line
permalink: /tutorial/cli/
redirect_from: /tutorial/cli.html
layout: tutorial
---
With this workflow, you

1. Write your study design specification in the Tisane DSL in any IDE or plain old text editor of your choice. The last line in the file should be the call to `tisane.infer_statistical_model_from_design`
2. Run the python file from the command line. This should look like `python3 <my-tisane-design-file>.py` or `poetry run python3 <my-tisane-design-file>.py`. This will open up the Tisane GUI.
3. After generating code in the Tisane GUI, you will get the path to the output model. You can copy it, and then go back to the command line and run `python3 <copied-path-goes-here>` or `poetry run python3 <copied-path-goes-here>`

![A pop-up after generating the code in the Tisane GUI, which gives a copy-able path to the output model script](https://github.com/emjun/tisane/raw/main/examples/tutorial_screenshots/code_generated.png?raw=true)

This way, you get to use whatever IDE you like to write the specification using the Tisane DSL.
