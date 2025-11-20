

### Running Python scripts with UV

To run a Python script directly, you can use the `uv run` command followed by your script name instead of the usual `python script.py` syntax:

```c
uv run main.py
```

The `run` command ensures that the script is executed inside the virtual environment UV created for the project.

### Updating dependencies

In long-term projects, it is common to update the packages you are using to bring the most up-to-date features to the table. Or sometimes, a package you are using introduces breaking changes and you want to ensure that version doesn't get installed accidentally in your environment. The `add` command can be used again in these and any other scenario where you need to change the constraints or versions of existing dependencies.

#### 1. Installing the latest version of a package:

```c
uv add requests
```
``
#### 2. Installing a specific version:

```
uv add requests=2.1.2
```

#### 3. Change the bounds of a package's constraints:

```c
uv add 'requests<3.0.0'
```

#### 4. Make a dependency platform-specific:
```c
uv add 'requests; sys_platform="linux"'
```