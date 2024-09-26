
```
#!/bin/bash

name="Ali"  # variable 

echo "Good Morning $name!!"  # $ for interpreting variable inside string

sleep 1

echo "You're looking good today $name!"

sleep 1

echo "You have the best board I've ever seen $name!!"


```

**$ sign** In Bash, when you use a dollar sign (`$`) followed by a variable name inside a string, it tells the shell to replace that variable name with its value. This process is called **variable expansion** or **substitution**.


## Read input from command line

```
#!/bin/bash

echo "what is your name: "

read name # read Input from commnad line

echo  "Good Moring $name!!"

sleep 1

echo "You're Looking good today $name!"

sleep 1

echo "You have the best board I've ever $name!!"
```

**read** In Bash, the `read` command is used to take input from the user during the execution of a script. When you use `read`, the script pauses and waits for the user to type something, then it stores the input in a variable.


### Positional Parameter


```
#!/bin/bash

name=$1
friend=$2

echo  "Good Moring $name!!"

sleep 1

echo "You're Looking good today $name!"

sleep 1

echo "You have the best $friend I've ever $name!!"
```


positional variable passed when write command in command line not during execution

In above Bash script, `name=$1` and `friend=$2` are examples of **positional parameters**. Positional parameters are used to pass arguments to a Bash script from the command line.

Here's how it works:

- `$1` refers to the first argument passed to the script.
- `$2` refers to the second argument passed to the script.
- Similarly, `$3`, `$4`, and so on refer to the third, fourth, etc., arguments

For example, if you run your script with the following command:

```
./your_script.sh Ali Bob
```

- `$1` will be `"Ali"`, which is assigned to the `name` variable.
- `$2` will be `"Bob"`, which is assigned to the `friend` variable.


So, your script will output:

```
Good Morning Ali!!
You're looking good today Ali!
You have the best Bob I've ever seen, Ali!!

```

example:

```
#!/bin/bash

name=$1
friend=$2

user=$(whoami) # store the command result in variable in user

date=$(date)

whereami=$(pwd)


echo  "Good Moring $name!!"

sleep 1

echo "You're Looking good today $name!"

sleep 1

echo "You have the best $friend I've ever $name!!"

sleep 2

echo "You are currently logged in as $user and you are in the directory $whereami. Also today is:$date"
```