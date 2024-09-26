
Bash provides several built-in variables that contain useful information about the current shell environment and script execution. These variables are often referred to as "special" or "built-in" variables. Here's a list of some commonly used built-in variables in Bash:

### 1. **Positional Parameters:**

- `$0`: The name of the script.
- `$1` to `$9`: The first to ninth arguments passed to the script.
- `${10}`, `${11}`, etc.: Arguments beyond the ninth.

### 2. **Special Variables:**

- `$#`: The number of arguments passed to the script.
- `$@`: All the arguments passed to the script (as a single string).
- `$*`: All the arguments passed to the script (treated as a single word).
- `$$`: The process ID (PID) of the script.
- `$?`: The exit status of the last command executed.
- `$!`: The process ID of the last background command.
- `$-`: The current options set for the shell.
- `$_`: The last argument of the previous command.

### 3. **Environment Variables:**

- `$HOME`: The current user's home directory.
- `$PATH`: The list of directories searched for executable files.
- `$USER`: The current logged-in user's name.
- `$HOSTNAME`: The hostname of the system.
- `$PWD`: The current working directory.
- `$OLDPWD`: The previous working directory.
- `$SHELL`: The path to the current shell.
- `$EDITOR`: The default text editor.

### 4. **Script-Specific Variables:**

- `$LINENO`: The current line number in the script.
- `$BASH_VERSION`: The version of Bash being used.
- `$RANDOM`: A random number between 0 and 32767.
- `$SECONDS`: The number of seconds the script has been running.
- `$UID`: The user ID of the current user.

### 5. **Array Variables:**

- `BASH_ALIASES`: An associative array of the current shell aliases.
- `BASH_SOURCE`: An array containing the source filenames where each corresponding shell function was defined.

```
#!/bin/bash

echo "Script name: $0"
echo "First argument: $1"
echo "Number of arguments: $#"
echo "All arguments: $@"
echo "Current working directory: $PWD"
echo "Home directory: $HOME"
echo "Bash version: $BASH_VERSION"
echo "Random number: $RANDOM"
echo "Current User: $USER"
echo "current Host name: $HOSTNAME"
```