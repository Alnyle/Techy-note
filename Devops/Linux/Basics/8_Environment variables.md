
An **environment variable** is a user-definable [value](https://en.wikipedia.org/wiki/Value_(computer_science) "Value (computer science)") that can affect the way running [processes](https://en.wikipedia.org/wiki/Process_(computing) "Process (computing)") will behave on a computer. Environment variables are part of the environment in which a process runs. For example, a running process can query the value of the TEMP environment variable to discover a suitable location to store [temporary files](https://en.wikipedia.org/wiki/Temporary_file "Temporary file"), or the HOME or USERPROFILE variable to find the [directory structure](https://en.wikipedia.org/wiki/Directory_structure "Directory structure") owned by the user running the process.

They were introduced in their modern form in 1979 with [Version 7 Unix](https://en.wikipedia.org/wiki/Version_7_Unix "Version 7 Unix"), so are included in all [Unix](https://en.wikipedia.org/wiki/Unix "Unix") [operating system](https://en.wikipedia.org/wiki/Operating_system "Operating system") flavors and variants from that point onward including [Linux](https://en.wikipedia.org/wiki/Linux "Linux") and [macOS](https://en.wikipedia.org/wiki/MacOS "MacOS"). From [PC DOS 2.0](https://en.wikipedia.org/wiki/PC_DOS_2.0 "PC DOS 2.0") in 1982, all succeeding [Microsoft](https://en.wikipedia.org/wiki/Microsoft "Microsoft") operating systems, including [Microsoft Windows](https://en.wikipedia.org/wiki/Microsoft_Windows "Microsoft Windows"), and [OS/2](https://en.wikipedia.org/wiki/OS/2 "OS/2") also have included them as a feature, although with somewhat different syntax, usage and standard variable names.


We use `printenv` command to print environment variables in the shell 

1. print all environment variables in your current system or (user)

```
printenv
```


2. If you want to print a specific environment variable, you can do so by specifying its name


```
printenv [variable-name]
```

example :

```
print USER
```

and

```
printenv SHELL
```

3. use `printenv` with `grep` you can use shell commands like `grep` to filter the output for specific patterns:

```
printenv | grep "SOME_PATTERN"
```


#### Create Environment Variable (temporary variable)

`note this not a permanent environment variable as soon you close your terminal will not exist  

example`

```
export variable_name=value
```



```
export [DB_USERNAME]=dbuser
```

### Delete environment variable 

```
unset [variable_name]
```

#### Create Environment Variable (Permanent variable)

To create permanent environment variable you have add variable to hidden file auto generated for the shell program for the current user to save it's shell configuration called `.bashrc`
if you use `bash` shell and `.zshrc` in case of `zsh` shell

Variable set in this file are loaded whenever a bash login sell is entered

 the location of the file `/home/user-name` to open the file you have to use vim editor

```
vim .bashrc
```

and add your variable
```
export [VARIABLE_NAME_IN_CAPITAL]=value
```

after you add your environment variable you have to close and open your shell again to load the new environment variables you add recently 