
`Ownership` who owns the file/directory

`Ownership` Ownership levels of file/directory :
 -  Which user owns by the file/directory
-  Which group owns by the file/directory

`Owner`: is the user, who created the file
`Owning group` is the primary group of that user


##### Change file/directory ownership

```
sudo chown [user-name]:[group-name] [file-name]
```

example:

```
sudo chown tom:devops index.html
```


##### change file/directory user owner

```
sudo chown [user-name] [file.name]
```

example :

```
suod chown tom index.html
```

change the ownership of this file to `tom` user


##### change file/directory group owner

```
sudo chgrp [group-name] [file-name]
```

example: 

```
sudo chgrp devops index.html
```

change the ownership of this file to `tom` group


### File permission

File permissions in Linux are a crucial part of the security model, defining who can read, write, or execute a file. Each file and directory in Linux has an associated set of permissions that determine how users and groups can interact with them.

### Understanding File Permissions

Permissions in Linux are managed at three levels:

1. **User (Owner)**
2. **Group**
3. **Others**

Each of these can have three types of permissions:

- **Read (r)**: Allows viewing the contents of the file.
- **Write (w)**: Allows modifying or deleting the file.
- **Execute (x)**: Allows running the file as a program.

### Viewing File Permissions

To view the permissions of a file or directory, you can use the `ls -l` command

```
ls -l filename
```

The output will look like this:

```
-rwxr-xr--
```

This breakdown shows:

- **`-`**: File type (e.g., `-` for a regular file, `d` for a directory)
- **`rwx`**: Permissions for the user (owner)
- **`r-x`**: Permissions for the group
- **`r--`**: Permissions for others

### hanging File Permissions with `chmod`

The `chmod` command is used to change file and directory permissions.

#### Symbolic Mode

In symbolic mode, you specify which permissions to add (`+`), remove (`-`), or set (`=`) for each category (user, group, others)

**Examples:**

Add execute permission for the owner:
```
chmod u+x filename
```

Remove write permission for the group:
```
chmod g-w filename
```

Set read-only permission for others:
```
chmod o=rwx filename
```

another example:

```
chmod o=r-- filename
```


#### Numeric (Octal) Mode

In numeric mode, you represent permissions using a three-digit octal number. Each digit corresponds to the permissions for the user, group, and others


- **Permission values:**
    
    - **Read (r):** 4
    - **Write (w):** 2
    - **Execute (x):** 1
    - **No permission:** 0
- **Examples:**
    
    - **`chmod 755 filename`**:
        - Owner: `rwx` (7 = 4+2+1)
        - Group: `r-x` (5 = 4+0+1)
        - Others: `r-x` (5 = 4+0+1)
    - **`chmod 644 filename`**:
        - Owner: `rw-` (6 = 4+2+0)
        - Group: `r--` (4 = 4+0+0)
        - Others: `r--` (4 = 4+0+0)
