---
layout: default
title: "Python tips and tricks"
---

# Python tips and tricks

### [1] Modules v/s Packages v/s Distributions

 - Python Module: A [module](https://docs.python.org/3/tutorial/modules.html#) is a single Python file containing Python code (functions, classes, variables, etc.). It is the most basic unit of code organization in Python. When you import a module, you are importing all the code from that single .py file into your program.
 - Python Package: A [package](https://docs.python.org/3/tutorial/modules.html#packages) is a directory containing Python module files and a special __init__.py file. The __init__.py file is what distinguishes a package from a regular directory - it allows the directory to be treated as a Python package. Packages provide a hierarchical way to organize related modules together under a common namespace. For example, you could have a package named mypackage with submodules mypackage/module1.py and mypackage/module2.py.
 - Python Distribution: A distribution is a compressed archive file (like a .zip or .tar.gz) that contains one or more Python packages, along with metadata and other files required for installation. Distributions are what you download from sites like PyPI when you run pip install package_name. They provide a standard way to package up and distribute Python code to be installed on different systems.

In summary, a module is a single .py file containing Python code. A package is a directory containing init.py and other Python module files, providing a namespace hierarchy. A distribution is an installable archive file containing packages and metadata for distribution. Packages help organize code within a project, while distributions allow that code to be packaged up and shared as a single installable unit across different systems.

 
### [2] TQDM
[tqdm](https://tqdm.github.io/) is a package that lets you see the progress of your code as it's running through loops. We import "from tqdm import tqdm" and wrap tqdm around any iterator that we looping through e.g. "for item in tqdm(items): ". When the loop runs, a progress bar will appear! Another thing we can do is "from tqdm import trange" and using "trange" instead of "range" anytime we are creating an iterator over integers. We can also create a new iterator as "pbar = tqdm(items)" and then have a loop as "for item in pbar: pbar.set_description(f"processing {item}")". Finally, we can disable tqdm via "tqdm(items, disable = not config.debug" where "config.debug" can be set in the file configuration.
Reference: [This](https://www.youtube.com/watch?v=n4E7of9BINo&feature=youtu.be) video.
 

### References
 - Classes [link](https://realpython.com/learning-paths/object-oriented-programming-oop-python/)
 - Context managers [link](https://realpython.com/lessons/context-managers-intro/)
 - Dunder methods [link](https://www.youtube.com/watch?v=KSiRzuSx120&t=9s)
 - args and kwargs [link](https://www.youtube.com/watch?v=4jBJhCaNrWU)