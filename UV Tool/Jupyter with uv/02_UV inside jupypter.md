
If you need to manipulate the project's environment from within the notebook, you may need to add `uv` as an explicit development dependency:

```
uv add --dev uv
```

From there, you can use `!uv add pydantic` to add `pydantic` to the project's dependencies, or `!uv pip install pydantic` to install `pydantic` into the project's virtual environment without updating the project's `pyproject.toml` or `uv.lock` files.