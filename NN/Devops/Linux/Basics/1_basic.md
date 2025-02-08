Everything in Linux is a file
- Linux commands like (pwd, ls, etc..) is represent as binary files locate in of bin folder
- Devices like printer, USB, Keyboard you can access them 


`pwd`: display current working directory

```
pwd
```


## ls


`ls`: list files and folder

```
ls
```


`ls -r`: show folder inside folder 

```
ls -R path
```

exmaple:

```
ls -R documents
```


cd: Change directory to [path]

```
cd `path`
```


mkdir: create folder (directory) 

```
mkdir directoryName
```


`touch`: create file

```
tocuh fileName.extension
```

example:

```
touch main.py
```


`rm`: delete file

```
rm fileName.extension
```

example

```
rm main.py
```




`rm -r`: Delete a none-empty directory and all the files within it

```
rm -r folderNmae
```

`rm -d`: Delete an empty directory

```
rm -d folderNmae
```


navigate to the root folder

```
cd /
```


`mv`: Rename the file to a filename

```
mv [oldName] [newName]
```


## Copy

##### copy folder

`cp`: copy folder 
```
copy [copy-From-folder] [folder-to-copy-to]
```

example:

```
cp java-project py-project
```

##### copy files

`cp`: copy files 
```
copy [file-to-make-copy-from] [copy-name]
```

example:

```
cp read.md test.md
```


