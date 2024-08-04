#Accessing a running SQL DB via the terminal

use mariadb-server & mariadb-client

command:

mariadb --host 127.0.0.1
            --port 3306
            --user admin
            --password

It should then ask for the password, then open the db interface.

User, password and port are current defined in Dockerfile.

Same principles should apply for accessing a remote database.
