=====================
# MySQL Cheat Sheet
=====================


To begin, you'll want to set up an SSH Tunnel through to the Vagrant Box (Scotch Box). This will allow you to connect any MySQL DB Tools to the localhost instead of the 192.168.33.10 IP address for the Scotch Box. 
If your tool of choice has connect to DB via SSH, bonus points. 
Some of the VSCode Extensions I've seen do not. [sad face]
So yay! You get to learn how to ssh tunnel!

	$ ssh -v -L 3306:127.0.0.1:3306 vagrant@192.168.33.10



Once you've started your Scotch Box with the following command:

	$ vagrant up

You're ready to ssh into the Box Of Scotch with this command: 

	$ vagrant ssh

Notice the prompt change to something like:

	vagrant@scotchbox:~$

Now you're in the Scotch Box. Log in to MySQL using the following command: 

	$ mysql -u root -proot

You'll notice the prompt change to:

	mysql>


All the commands to issue from the 

	mysql> 

prompt, remember, you're entering actual MySQL statements. 
And as with any statement, you'll need to make sure you end it with a ';'


## Show all the available databases on the server

	show databases;


## Create a Database

	create database [database-name];


## Create a Table in the Database

This will add a table to the specified database with columns for common user data. 
Note that one column is the primary key for the table. 

	create table [database-name].[table-name] {
		userID int unsigned not null auto_increment primary key,
		lastName varchar(64),
		firstName varchar(64),
		email varchar(320),
		userProfileImage varchar(320),
		address varchar(320),
	};


## Alter a Table in a Database

The following will alter a pre-existing column userID and add a number of properties to it, it's an integer, not null, unsigned, etc. etc. 

	alter table [database-name].[table-name] modify column [column-name] int unsigned not null auto_increment


## Alter a Table in a Database and add a column. 

This statement will add a column [column-name] thats 320 variable characters to the database table

	alter table [database-name].[table-name] ADD [column-name] varchar(320)


## Describe what's in a table. 

To find out all the columns in a table, use the 'describe' command. 

	describe [database-name].[table-name]


## Insert values into a row in the table

This statement will add a new row to the database with the values indicated.
You must make sure that the values are in the same order as the specified columns. 

	insert into [database-name].[table-name] (
		lastName, 
		firstName,
		email,
		userProfileImage,
		address
		) values (
		'Smith',
		'Sammy',
		'email@email.com',
		'/assets/images/default.jpg',
		'123 Main St. Muricah, TN 373737'
	);


## Select all things from a table. 

This returns ALL (*) the rows from the db. 

	select * from [database-name].[table-name]



## See what's in a table

Will return a list of what's in the Row. 

	describe [database-name].[table-name]


## Help how do I get out of here? 

	exit

