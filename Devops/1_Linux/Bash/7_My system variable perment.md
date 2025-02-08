To create a permanent system variable in Bash that persists across sessions and reboots, you need to define it in a configuration file that is sourced automatically when the shell starts. Here’s how you can do this:

### For Individual User

1. **Edit `.bashrc` or `.bash_profile`:**
    
    - **`.bashrc`**: Typically used for non-login shells (e.g., new terminal windows).
    - **`.bash_profile`** or **`.profile`**: Used for login shells (e.g., when you log in to your user account).
    
    The choice between `.bashrc` and `.bash_profile` depends on whether you want the variable to be set for login shells or for all interactive non-login shells. Usually, `.bash_profile` sources `.bashrc`, so setting it in `.bashrc` is common.
    
    Open the file in a text editor, for example:
    
```
nano ~/.bashrc
```

or

```
nano ~/.bash_profile
```

2. **Add Your Variable:**

Add the following line to define and export your variable:

```
export MY_VARIABLE="my_value"
```


- Replace `MY_VARIABLE` with the name of your variable and `my_value` with its value.

```
source ~/.bashrc
```

or

```
source ~/.bash_profile
```

### For All Users

To set a system-wide environment variable that applies to all users, you can add it to one of the global profile files.

1. **Edit `/etc/profile` or `/etc/bash.bashrc`:**
    
    - **`/etc/profile`**: Used for login shells. Changes here apply to all users.
    - **`/etc/bash.bashrc`**: Used for non-login interactive shells.
    
    Open the file in a text editor with root privileges, for example:

```
sudo nano /etc/profile
```


3. **Apply the Changes:**

You can either log out and log back in, or source the file to apply the changes immediately:

```
source /etc/profile
```

or 

```
source /etc/bash.bashrc

```

### Checking the Variable

To verify that the variable is set correctly, open a new terminal session and run:


```
echo $MY_VARIABLE
```

This should display the value of `MY_VARIABLE` you set.
### Notes

- **Security:** Be cautious when editing global files, especially `/etc/profile`, as incorrect changes can affect all users and system behavior.
- **Variable Names:** Use uppercase names for environment variables to distinguish them from other variables and avoid conflicts.