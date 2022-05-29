# wordpress-hardenning

```
find . -type d  -print0 | xargs -0 chmod 755
```
This means a permissions to read, write and execute for the user; only read & execute access to the group and none all to others.

```
find ./ -type f -iregex '.*\.\(php\)$' -print0 | xargs -0 chmod 644
```
This means that users have read and write permissions and groups and others can only read the files.
This will ensure that no one accessing the files can alter them, apart from the owner.

```
find ./ -type f -not -iregex '.*\.\(php\)$' -print0 | xargs -0 chmod 644
```
Other files

```
find . -type f -name 'wp-config.php' -print0 | xargs -0 chmod 440
```
The wp-config is the configuration file of your WordPress and is one of the most sensitive files. Protect this with a permission of 400|440.
This means even the user and the server has no right to edit, whereas other can not even read.

```
find . -type f -name '.httpaccess' -print0 | xargs -0 chmod 440
```

```
find . -type f -name 'index.php' -print0 | xargs -0 chmod 444
```
The permission for index.php is 644|444. 
The 444 permission can be set for higher security which ensures only admin can perform any write o execute actions.
