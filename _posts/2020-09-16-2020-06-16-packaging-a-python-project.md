---
layout: post
published: false
title: 2020-06-16-packaging-a-python-project
---
# A Packaging a Python project as a source distribution

This setup will be minimalist, for consumption as a Source distribution

## Create your project

hello.py
```python
def greet():
	print("Hello Python package")
```

README.md
```
Something useful
```

setup.py
```
import setuptools

with open("README.md", "r") as fh:
    long_description = fh.read()

setuptools.setup(
    name="hello-joao-vicente",
    version="0.0.1",
    author="Joao Vicente",
    author_email="joao.vicente@gmail.com",
    description="Says hello",
    packages=setuptools.find_packages(),
    classifiers=[
        "Programming Language :: Python :: 3",
        "License :: OSI Approved :: MIT License",
        "Operating System :: OS Independent",
    ],
    python_requires='>=3.6',
)
```

## Install setuptools and wheel 

```
python3 -m pip install --user --upgrade setuptools testresources wheel
```

Create a virtual enviroment

```bash
$ python3 -m venv myenv
$ source myenv/bin/activate
```

When finished with the environment deactivate it

```bash
$ deactivate
```

## References
https://docs.python.org/3/tutorial/modules.html#packages
https://packaging.python.org/tutorials/packaging-projects/
https://packaging.python.org/tutorials/installing-packages/#installing-from-local-archives