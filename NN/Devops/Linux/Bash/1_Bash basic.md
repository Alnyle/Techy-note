
#### To know what shell you are using

```
which $SHELL
```

print text in command line 

```
echo "text here"
```
## 1.Nano text editor

#### 1. run
run nano editor 

```
nano filename
```

example:

```
nano himgs
```


#### 2.code

```
#!/bin/bash

// rest of code

//example
echo "Hi man"

```

**#!**  marks: these two characters call Shebang 
**/bin/bash** :  tell bash shell what script language you want to use because sometimes we my use python to run python script or GO or any other programming language

##### 3.quit from nano editor:

```
press CTRL + X
```


##### 4.run bash file or script

```
bash fileName
```

example:

```
bash himsg.sh
```

##### 5.Edit bash file using same command 

edit is easy in bash you can use nano command with name of the file

```
nano samefileName
```

### ----------------------

#### sleep word

Sleep is a way to pause the execution of a script


```
#!/bin/bash

echo "Hi Mom"

sleep 3

echo "Uh uh"

sleep 3

echo "Oh wow"


sleep 3

echo "I can't believe that"

echo "Bye Love you too"
```



### 3.File Permission

##### list all files with their permissions

```
ls -l
```


change file permission 

```
chmod +typeofpermission fileName
```

type permission have type and simple
w: writable file
r: readable file
x: executable file