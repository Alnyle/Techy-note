
In Bash, you can create your own system (or environment) variables by defining them in your script or shell session. These variables can store values, like strings, numbers, or the output of commands, and can be used throughout your script or session.

#### note
system variable like global variable can access from any place in your system

### Creating a Variable

You can create a variable simply by assigning a value to a name:

```
my_var="Hello, World!"
```

### accessing a Variable

To access the value stored in a variable, you use the `$` symbol followed by the variable name:

```
echo $my_var  # Outputs: Hello, World!`
```


### Exporting Variables

If you want your variable to be accessible in child processes or subshells (e.g., scripts or commands that you run from your current script), you can export it as an environment variable using the `export` command:

```
export my_var="Hello, World!"
```

Now, `my_var` will be available to any script or command executed from the current shell session.

```
#!/bin/bash

# Export a variable
export my_var="Hello from parent script!"

# Run another script that uses the variable
./child_script.sh

```

In `child_script.sh`, you can access `my_var`:


```
#!/bin/bash

echo "The variable from the parent script is: $my_var"

```

### Unsetting Variables

To remove or unset a variable, you can use the `unset` command:

```
unset my_var
```

After running `unset`, the variable `my_var` will no longer be available.

### Scope of Variables

- **Local Variables:** Variables defined without `export` are local to the current script or shell session.
- **Environment Variables:** Variables defined with `export` are available to child processes or subshells.

### Example: Combining Local and Exported Variables


```
#!/bin/bash

# Local variable (only available in this script)
local_var="This is local."

# Exported variable (available to child processes)
export exported_var="This is exported."

echo "Local variable: $local_var"
echo "Exported variable: $exported_var"

# Running a command or script that accesses exported_var
bash -c 'echo "Accessed in subshell: $exported_var"'

```

In this example, `local_var` is only available within the current script, while `exported_var` is available to any child processes


By creating and managing your own system variables, you can control how data flows through your scripts and shell environment, making your scripts more flexible and powerful.