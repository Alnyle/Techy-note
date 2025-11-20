### 1. Initializes the project

- This creates a new project folder named `myproject` with a `pyproject.toml` and virtual environment setup.

```c
uv init .
```


### 2. Install ipykernel package

 you need to install packages from within the notebook, we recommend creating a dedicated kernel for your project. Kernels enable the Jupyter server to run in one environment, with individual notebooks running in their own, separate environments.
 
In the context of uv, we can `create a kernel for a project while installing Jupyter itself in an isolated environment`, as in `uv run --with jupyter jupyter lab`. Creating a kernel for the project ensures that the notebook is hooked up to the correct environment, and that any packages installed from within the notebook are installed into the project's virtual environment.

- Installs the `ipykernel` package into this new environment.
- `ipykernel` is what allows Jupyter to run code inside this environment.

```bash
uv add --dev ipykernel
```

### 3. Create the kernel for `project` with


```bash
uv run python -m ipykernel install --user --name projectName --display-name "ProjectName"
```

or you to write inside a script

```bash
uv run python -m ipykernel install --user --name %1 --display-name "%1"
```

- `uv run` → runs a command **inside the environment** created by `uv`.
- `python -m ipykernel install` → registers a new Jupyter kernel.
- `--user` → installs the kernel spec for your user only (no admin rights needed).
- `--name %1` → the **internal kernel name** (machine-readable). Example: `myproject`.
- `--display-name "%1"` → the **human-readable name** shown in Jupyter Notebook/Lab dropdowns. Example: `myproject`.

This script automates creating a new Python project with `uv`, installs `ipykernel`, and registers it so you can select it in Jupyter as a kernel.

#### Step 1-2-3 in one script

That's useful but a bit tedious. Much better to have a script that will create a new project and do the work for you.

```bash
uv init %1 
cd %1
uv add ipykernel uv run python -m ipykernel install --user --name %1 --display-name "%1"

```

to run the script:

```bash
./juv.bat mynewproject
```


### 4. Run Jupyter notebook


for first time

```bash
uv run --with jupyter jupyter lab
```

if is not first after creating your project 

```bash
uv run jupyter lab
```


This will run a Jupyter server in an isolated environment.

By default, `jupyter lab` will start the server at [http://localhost:8888/lab](http://localhost:8888/lab).



## [Using Jupyter from VS Code](https://docs.astral.sh/uv/guides/integration/jupyter/#using-jupyter-from-vs-code)


You can also engage with Jupyter notebooks from within an editor like VS Code. To connect a uv-managed project to a Jupyter notebook within VS Code, we recommend creating a kernel for the project, as in the following:

```bash
# Create a project.
uv init project

# Move into the project directory.
cd project

# Add ipykernel as a dev dependency.
uv add --dev ipykernel

# Open the project in VS Code.
code .
```

Once the project directory is open in VS Code, you can create a new Jupyter notebook by selecting "Create: New Jupyter Notebook" from the command palette. When prompted to select a kernel, choose "Python Environments" and select the virtual environment you created earlier (e.g., `.venv/bin/python` on macOS and Linux, or `.venv\Scripts\python` on Windows).


### Reference 

- [Using UV with Jupyter Notebooks](https://medium.com/@alan-jones/using-uv-with-jupyter-notebooks-56d964244d6e)
- [How to Run a Jupyter Notebook with uv](https://pydevtools.com/handbook/how-to/jupyter-notebook-with-uv/)
