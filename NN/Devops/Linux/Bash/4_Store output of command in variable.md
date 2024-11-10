
To store command result in a variable use their two ways

To store the result of a command in a variable in Bash, you use **command substitution**. There are two ways to do this:

1. Using backticks `` `command` `` (older syntax).
2. Using `$(command)` (modern and preferred syntax).

### Example:

If you want to store the result of the `date` command in a variable called `current_date`, you can do it like this:


```
current_date=$(date)
```

store date command result in variable called `current_date`
