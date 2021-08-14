# PostgreSQL-setup
Set up PostgreSQL on a RaspberryPi-4


### install dependencies and postgresql
sudo apt install postgresql

# Configure User
### change to postgres user
<code>sudo su postgres</code>

### create a new role
<code>createuser <username> -P --interactive</code>

### Enter a password for this new role
<code>Enter password for new role:</code>
<code>Enter it again:</code>

### You will now need to decide if you want this new user to be a superuser
### if you want to use the new user to create databases and other stuff, answer Y to this question
<q>Shall the new role be a superuser? (y/n)</q> <code>y</code>

### Create a database that has the same name as our user.
<blockquote>When you use the CLI, it will try to auto connect to a database with the same name as your username. Load up
    the CLI by running the following command</blockquote>
<code>psql</code>

### Create a database with the username you chose
<code>CREATE DATABASE < username >;</code>

### Quit the CLI tool by typing
<code>exit</code>

## CREATE POSTGRESQL DATABASE
### Load into Postgres CLI
<code>psql</code>

### Create and manipulate databases
<code>CREATE DATABASE <database_name>;</code>

### Connect to newly created database
<code>\connect "database_name";</code>

### If you connected successfully, you should be prompted with a message
<blockquote>You are now connected to database "database_name" as user "pi"</blockquote>

### Create a sample database table
<code>CREATE TABLE programming_books (name text, author text);</code>

### Add data to database
<code>INSERT INTO programming_books VALUES ('Practical SQL', 'Anthony Debarros');</code>

### Query data from database
<code>SELECT * FROM programming_books</code>



# PostgreSQL Commands

### DROP/DELETE DATABASE
<code>DROP DATABASE "database_name"; </code>

### RENAME DATABASE
<code>ALTER DATABASE programming_books RENAME TO something_else</code>
