
 `>` character is the redirect operator. takes the output from previous command and sends it  to a file that give 

`>>` append to file while `>` override the entire file content
### Examples

1. **store history of commands in a file**

```
history | grep sudo > res.txt
```

To add the command result to file use `>>` because does not override file content but append command result to file content

```
history | grep sudo >> res.txt
```

2. file 

```
history | grep rm >> deletRes.txt
```