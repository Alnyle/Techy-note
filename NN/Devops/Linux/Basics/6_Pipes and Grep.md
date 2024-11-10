
### Pipe `|`
The output from one command can become the input of another command

In Linux, a **pipe** is a powerful feature that allows the output of one command to be used as the input for another command. This is done using the pipe symbol `|`. Pipes are an essential part of Linux command-line usage, enabling the combination of simple commands to perform more complex tasks efficiently.

### How Pipes Work

- **Basic Syntax:**
```
command1 | command2
```

- Here, the output of `command1` is sent directly to `command2` as its input.

- **Flow of Data:**
    
    - `command1` generates output (standard output, `stdout`).
    - The pipe (`|`) takes this output and feeds it as the input (standard input, `stdin`) to `command2`.

### Examples of Using Pipes

1. **Listing Files and Searching for a Pattern:**

command

```
ls -l | grep "pattern"
```

**Explanation:**

- `ls -l` lists files in long format.
- `grep "pattern"` filters the list to show only lines containing "pattern."

2. Search in command history

```
history | grep sudo | less
```

- **Step 1**: `history` retrieves your command history.
- **Step 2**: `grep sudo` filters that history to show only the commands where you used `sudo`.
- **Step 3**: `less` allows you to view those filtered commands in a scrollable format.
### Combining Multiple Pipes

You can chain multiple commands together using pipes:

**Example:**

```
cat /var/log/syslog | grep "error" | sort | uniq -c | sort -nr | head -n 10
```

**Explanation:**

- `cat /var/log/syslog`: Displays the contents of the system log.
- `grep "error"`: Filters lines containing the word "error".
- `sort`: Sorts the filtered lines.
- `uniq -c`: Counts the number of occurrences of each unique line.
- `sort -nr`: Sorts the results numerically in reverse order.
- `head -n 10`: Displays the top 10 most frequent error messages.