

### Incepts installed dependencies

```c
uv pip list
```

another way but also show the sub-dependencies

```c
uv tree
```

### 📦 Exports your locked environment to a `requirements.txt` file

```
uv export -o requirements.txt
```

Reads from your `uv.lock` file (which has exact versions) then write into a `requirements.txt` file that can be used with `pip`

#### Perfect when you want to:
- Share dependencies with teams using `pip`
- Deploy to environments where `uv` isn't available
- Migrate to/from `pip`-based workflows


### Dependency Groups

Dependency groups allow you to organize your dependencies into logical groups, such as:
- development dependencies
- test dependencies 
- or documentation dependencies.

This is useful for keeping your production dependencies separate from your development dependencies.

To add a dependency to a specific group, use the `--group` flag:

```c
uv add --group group_name package_name
```

Then, users will be able to control which groups to install using the `--group`, `--only-group`, and `--no-group` tags.

for example `pytest` which is dev dependency

```c
uv add --dev pytest
```