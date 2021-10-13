---
title: Introduction
sidebar: mydoc_sidebar
permalink: mydoc_introduction.html
folder: mydoc
---

## Introduction To Python Programming

Python is the most popular language used for programming in the data science domain and a major reason for this is because of it's simplicity. While Python focuses on simplicity and ease of use, at the same time it sacrifices on speed, safety etc. However as a data scientist issues like safety and speed are not of much importance to us right now and when they do, we will use other frameworks designed specifically for production level systems.

In this tutorial we will go through basic Python programming techniques that will be essential in getting started with machine learning, deep learning, data visualization and other data science related programming tasks. This guide is however not comprehensive. It is just a means to get ourselves comfortable with Python. For an in depth Python tutorial you can always refer the officical Python documentation.

_For this tutorial, we will be using Python 3 (Python 3.6 or higher) so please ensure you have Python 3 installed on your computer. A good way to go through these tutorials is to type the commands and execute them along the way._

### The Programming Environment

Python files are saved as `file_name.py` files and running them is quite easy. Here, we will go through 3 of the most popular approaches to Python programming and help you get started:

- **Using Jupyter Notebook**
  This is the easiest approach to getting up and started with Python. This however requires extra software installation (Anaconda). You can download Anaconda distribution from [here.](https://www.anaconda.com/distribution/)
  Once istalled, run Jupyter Notebook, create a new notebook and you can get started immediately. A quick guide to Jypyter Notebook can be found [here.](https://medium.com/codingthesmartway-com-blog/getting-started-with-jupyter-notebook-for-python-4e7082bd5d46)

- **Using A Text Editor**
  A text editor is a program that lets you write code in a language of your choice and provides additional features like _syntax hilighting_, _code completion_ etc. Popular text editors include [Atom,](https://atom.io/) [Sublime Text,](https://www.sublimetext.com/) [Visual Studio Code](https://code.visualstudio.com/) etc. The steps involved are:

* Create a new Python 3 file and write code and save it.
* Open terminal and navigate to the location where the file was saved.
* Type `python3 file_name.py` to execute. If there are no errors, the file will run and the output will be visible on the terminal itself.

- **Using IDE**
  An Integrated Development Environment (IDE) is a software that provides a complete package which includes a text editor, a compiler, a debugger, a project tracker etc. These are however best suited for commercial or production level software development and beginners best stay away from there. That being said, [PyCharm](https://www.jetbrains.com/pycharm/) is a popular Python IDE.

_Alternatively, if you dont want to go through any of the above steps, you can visit [Google Colab](https://colab.research.google.com/notebooks/welcome.ipynb) and execute your Python commands online using Google's servers._

### Checking The Python Version

Once Python installation is complete, verify the installation and the version using the following command (if everything appears like below, you are good to go)

```python
# This is the command to check the version of Python
# More in import statements later
import sys
print(sys.version)
```

    3.6.7 |Anaconda, Inc.| (default, Oct 23 2018, 14:01:38)
    [GCC 4.2.1 Compatible Clang 4.0.1 (tags/RELEASE_401/final)]

## Getting started

To get started, see [Getting Started][index].

{% include links.html %}
