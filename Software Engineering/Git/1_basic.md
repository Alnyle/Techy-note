
#### Git Log
The git log command shows a history of the commit in a repository.
```
git --no-pager log -n 10
```

`--no-pager`: don't print the output in another windows print it in same window
`n`: the number of commands you want to see

### Git Switch
a be
```
git switch [branch-name]
```

In Git, both `switch` and `checkout` can be used to change branches, but they have different purposes and are used in different contexts.

### `git checkout`

- Older command that serves multiple purposes:
    - Switching branches: `git checkout branch-name`
    - Creating and switching to a new branch: `git checkout -b new-branch`
    - Checking out a specific commit or file: `git checkout commit-hash`
- Can be used to restore individual files from a commit: `git checkout HEAD -- file.txt`
- More general but can be confusing due to its multiple roles.

### `git switch`

- Introduced in Git 2.23 to simplify branch switching.
- Specifically designed for branch operations:
    - Switching branches: `git switch branch-name`
    - Creating and switching to a new branch: `git switch -c new-branch`
- Cannot be used to checkout files or commits.
- More intuitive and recommended over `checkout` for branch operations.

### When to Use What?

- **Use `git switch`** when you only want to work with branches (switching or creating).
- **Use `git checkout`** when you need to restore files or work with specific commits.

Would you like an example of using either command?