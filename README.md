# PostgreSQL-setup
Set up PostgreSQL on a RaspberryPi-4



######################################
SETUP POSTGRESQL RASPBERRYPI 4
######################################


### install dependencies and postgresql
sudo apt install postgresql


#######################################
configure PostgreSQL's CLI to use the pi User
#######################################

# change to postgres user
sudo su postgres

# create a new role
# <username> = pi
createuser <username> -P --interactive

# Enter a password for this new role
Enter password for new role:
Enter it again:

### You will now need to decide if you want this new user to be a superuser
# if you want to use the new user to create databases and other stuff, answer Y to this question
Shall the new role be a superuser? (y/n) y

### Create a database that has the same name as our user
# When you use the CLI, it will try to auto connect to a database with the same name as your username

# Load up the CLI by running the following command
psql

### Create a database with the username you chose
CREATE DATABASE <username>;

### Quit the CLI tool by typing:
exit

######################################
END SETUP and CONFIGURE of POSTGRESQL RASPBERRYPI 4
######################################




######################################
CREATE POSTGRESQL DATABASE
######################################

### Load into Postgres CLI
psql

### Create and manipulate databases
CREATE DATABASE <database-name>;

### Connect to newly created database
\connect <database-name>;

### If you connected successfully, you should be prompted with a message
You are now connected to database "<database-name>" as user "pi".

### Create a sample database table
CREATE TABLE programmingbooks (name text, author text);

### Add data to database
INSERT INTO programmingbooks VALUES ('Practical SQL', 'Anthony Debarros');

### Query data from database
SELECT * FROM programmingbooks


######################################
END CREATE POSTGRESQL DATABASE
######################################
