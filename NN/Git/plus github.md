
Create SSH KEY
go to your bash terminal
```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

- create new branch if not exist and switch to it
```
git checkout -b [branch-name]
```

- Delete branch

```
git checkout -d [branc-name]
```

merge branch locally before push change to remote repository
`note`: switch to the main branch first then write the command
```
git merge [branch-name]
```