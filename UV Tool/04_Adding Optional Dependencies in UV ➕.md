
Optional dependencies are used to install **extra features** that aren't required for your project's core functionality.

#### 📦 Example: Pandas

Pandas has extras like:

- `plot` → for visualization
- `excel` → for Excel parsing
    

### 🔁 Traditional pip Syntax:

```bash
pip install pandas[plot,excel]
```

### ✅ UV Syntax (Two Steps):

1. **Install the base package**:

```bash
uv add pandas
```

2. **Add optional dependencies**:
    
```bash
uv add pandas --optional plot excel
```
### 📄 Result in `pyproject.toml`:

```toml
name = "explore-uv"
version = "0.1.0"
description = "Add your description here"
readme = "README.md"
requires-python = ">=3.9"
dependencies = [
    "pandas>=2.2.3",
    "requests>=2.32.3",
]
[project.optional-dependencies]
plot = [
    "excel>=1.0.1",
    ...
]
```

>> ✅ UV separates core and optional dependencies for clarity and better environment control.

Let me know if you'd like this as a Markdown doc or want to add visuals!