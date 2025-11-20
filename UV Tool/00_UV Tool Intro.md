
UV is a modern, high-performance Python package manager and installer written in Rust. It serves as a drop-in replacement for traditional Python package management tools like `pip`, offering significant improvements in speed, reliability, and dependency resolution.

This tool represents a new generation of Python package managers, designed to address common pain points in the Python ecosystem such as slow installation times, dependency conflicts, and environment management complexity. UV achieves this through its innovative architecture and efficient implementation, making it 10-100 times faster than traditional package managers.

Key features that make UV stand out:

- Lightning-fast package installation and dependency resolution
- Compatible with existing Python tools and workflows
- Built-in virtual environment management
- Support for modern packaging standards
- Reliable dependency locking and reproducible environments
- Memory-efficient operation, especially for large projects
## Getting Started With UV For Python Projects

 We will discuss how to migrate from existing projects to UV in a later section.


### 1. Installing UV

UV can be installed system-wide using cURL on macOS and Linux:

```c
curl -LsSf https://astral.sh/uv/install.sh | sudo sh
```

And with Powershell on Windows (make sure you run Powershell with administrator privileges):

```c
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

UV is available via Homebrew as well:

```c
brew install uv
```

A PIP install is supported but it is not recommended:

```c
pip install uv  # Make sure you have a virtual environment activated
```

Afterward, you can verify the installation by running `uv version`:

```c
uv version
```

 output:

```c
uv 0.4.25 (97eb6ab4a 2024-10-21)
```

### Initializing a new project

#### 📁 2. Create an empty project folder 

You start by initializing an empty project using the `uv init` command:

```c
uv init explore-uv
```

The command will immediately create a new `explore-uv` directory with the following contents:

```c
.
├── .gitignore
├── .python-version
├── README.md
├── hello.py
└── pyproject.toml

```

Output:

```c
Initialized project explore-uv at /Users/bexgboost/projects/explore-uv
```

The command will immediately create a new `explore-uv` directory with the following contents:

```c
cd explore-uv
```


##### Create the project in current folder 

Initializes the project in the current directory — **no new folder is created**.

```c
uv init projectName
```

or 

```c
uv init .
```

**Tip:** Use `uv init` after `mkdir myproject && cd myproject` to keep things organized.

```c
mkdir myproject && cd myproject && uv init
```

### 3. Adding initial dependencies to the project

UV combines the environment creation and dependency installation into a single command - `uv add`:

```c
uv add scikit-learn
```

#### What happening when run `uv add scikit`

 - The first time you run the `add` command, UV creates a new virtual environment in the current working directory and installs the specified dependencies.
 - On subsequent runs, UV will reuse the existing virtual environment and only install or update the newly requested packages, ensuring efficient dependency management.

Another important process that happens for every `add` command is:
resolving dependencies. UV uses a modern dependency resolver that analyzes the entire `dependency graph` to find a compatible set of package versions that satisfy all requirements. This helps prevent version conflicts and ensures reproducible environments. The resolver considers factors like version constraints, Python version compatibility, and platform-specific requirements to determine the optimal set of packages to install.


- 🛠️ **Automatically updates**:
    
    - `pyproject.toml` with the added dependencies
        
    - `uv.lock` to lock exact versions
        

---

### 📄 Example `pyproject.toml` after `uv add requests`:

```toml
name = "explore-uv"
version = "0.1.0"
description = "Add your description here"
readme = "README.md"
requires-python = ">=3.9"
dependencies = [
    "scikit-learn>=1.5.2",
    "xgboost>=2.0.3",
]
```

Let me know if you'd also like to show a sample `uv.lock` entry!

### 4. Remove dependency
To remove a dependency from the environment and the `pyproject.toml` file, you can use the `uv remove` command. It will uninstall the package and all its child-dependencies:

```c
uv remove scikit-learn
```
