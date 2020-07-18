# Create shared directory for all users

1. make folder
```
sudo mkdir -p /folder/folder
```
* -p option creates & ignores any error

2. make group
```
sudo groupadd SharedUsers
```

3. give permission
```
sudo chgrp -R SharedUsers /folder/folder
sudo chmod -R 2775 /folder/folder
```
* 1st line changes group ownership, 2nd line changed rw permission

4. add users
```
usermod -a -G [groupname] [username]
```
* -a adds user to group, -G is group, seperated by comma