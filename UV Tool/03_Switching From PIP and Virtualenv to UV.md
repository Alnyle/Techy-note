
Migrating from PIP and virtualenv to UV is straightforward since UV maintains compatibility with existing Python packaging standards. Here's a step-by-step guide to make the transition smooth:

### 1. Converting an existing virtualenv project

f you have an existing project using `virtualenv` and pip, start by generating a `requirements.txt` file from your current environment if you haven't already:

```c
pip freeze > requirements.txt
```

Then, create a new UV project in the same directory:

```c
mkdir projectName && cd projectName
```

then

```c
uv init .
```

Finally, install the dependencies from your requirements file:

```c
uv pip install -r requirements.txt
```


### 🔁 2. pip / virtualenv vs. UV Commands

|📦 **pip / virtualenv command**|⚡ **UV equivalent**|
|---|---|
|`python -m venv .venv`|`uv venv`|
|`pip install package`|`uv add package`|
|`pip install -r requirements.txt`|`uv pip install -r requirements.txt`|
|`pip uninstall package`|`uv remove package`|
|`pip freeze`|`uv pip freeze`|
|`pip list`|`uv pip list`|
