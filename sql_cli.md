#Accessing a running SQL DB via the terminal

use mariadb-server & mariadb-client

command:

```
mariadb --host 127.0.0.1
            --port 3306
            --user admin
            --password
```

It should then ask for the password, then open the db interface.

User, password and port are current defined in Dockerfile.

Same principles should apply for accessing a remote database.

#update 20240809

```
sudo apt-get install mysql
// if that doesnt work
sudo apt-get install mariadb-server
//then 

mysql -h 127.0.0.1 -P 3306 -u root -p

// then enter password for root user

```


