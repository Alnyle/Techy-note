
types of users

#### Superuser account:

- Root user - unrestricted permission

#### User Account
- A regular user we create to login
- each has didact space 

#### Service Account

- Relevant for Linux Server Distors
- Each service will gets it's own user
- Example mysql will start mysql application
- Best practice for security
- Don't run service with root user!

- Always 1 Root user per computer 
- can have multiple regular users and service users


#### We manage permission in 2 different levels :
##### 1-  User level
 - Give permission to User directly

#### 2- Group level
- Group Users into Linux Groups
- Give permission to the Group
- This is the best way to go if you manager multiple Users


#### Access Control files

you have to go `/etc` where system configuration location

1 - `/etc/passwd` 
- Stores user account information
- Everyone can read it, but only root user can change the file

2- `/etc/group`


#### Create User

create user

```
sudo adduser [user-name]
```

- Automatically choose policy - conformant UID and GID values
 - Automatically creates a home directory with skeletal configuration

#### Change user password

only by root user

```
sudo adduser [user-name]
```

#### Change current user

```
su - [user-name]
```


#### Create Group

```
sudo groupadd [group-name]
```

#### Delete group

```
sudo delgroup [group-name]
```

be careful when using this command because may delete entire group of users


#### Add user to group

only the **root** user or a user with **sudo** privileges can add a user to a group in Linux. Regular users do not have the necessary permissions to modify group memberships for other users.

```
sudo usermod -g [group-name] [user-name]
```

- `-G` (group): Specifies the group to which the user is being added.


If a user is added to a new group and doesn't belong to any other groups, it's important to be aware of what happens if the group with the same name as the user should be deleted


### How Root or Sudo Users Add a User to a Group

a user can belong to multiple groups, and the user will inherit the permissions of all the groups they are a member of. This allows for flexible and fine-grained control over what files and resources a user can access.

```
sudo usermod -aG [group-name] [user-name]
```

**`-aG` Option:**

-  `-a`(append): Adds the user to the specified group without removing them from any other groups.
- `-G` (group): Specifies the group to which the user is being added

#### Display groups user belong to

```
groups [user-name]
```

#### Specify group to user at creation time

```
sudo adduser -G [group-name] [user-name]
```

example:
```
sudo adduser -G devops tom
``` 

#### Delete user from specific group

```
sudo gpasswd -d [user-name] [group-name ]
```