
## APT (Advance Package Tool)

used to install and uninstall and update software package  in Linux system

Search for package

```
sudo apt search [package]
```

example

```
sudo apt search java
```


remove package

```
sudo apt remove [software-package-name]
```

example 

```
sudo apt remove java
```


#### Update package index

- Get list version from the applications and update them
- pulls the latest changes from the APT repositories
- The APT package index is basically a database 
- Hold records of a available packages from the repositories 



## APT - GET

apt-get can achieve the same if you use additional command options but it's more user friendly, like progress bar and fewer but sufficient command in a more organized way 

`Update only updates the list of what packages are available. Upgrade only installs packages based on that list on your system.`

`You should always update before you upgrade. And you should probably upgrade after updating`


****`apt-get update`**** This command is used to update packages rather than installing them, basically it is used to update local package index with the latest information from the configured source. Remember it does not install packages.

Syntax for `apt-get update`:

```
sudo apt-get update
```

#### Syntax for `apt-get upgrade`:

In this we going to upgrade firefox,  if it is already upgrade it will show firefox is already upgraded.

```
sudo apt-get upgrade
```