# Introduction to MySQL and Relational Databases

Relational Databases (or RDB) refer to a form of database structure that involves tables, records, and columns, with clearly defined relationships between them. 

SQL, or Structured Query Language, is how we interface with that structure, and it is the language that we use to add, modify, delete, and perform many tasks on that data and it's relationships.

## What technology will we be using?

There are two dominant database systems you will likely see, one being MSSQL, and the other MySQL. They have quite a few differences under the hood, but just know that there are particularly syntactic differences, and we will be using MySQL throughout this.

## Installing MySQL

First, you need to install MySQL on your machine. You can do this using the *brew* package manager, by using the command:

`brew install mysql`

Now, you will need to start the service using brew:

`brew services start mysql`

If this fails, make sure that brew services are installed:

`brew tap homebrew/services`

And then set up the service to run at startup:

`ln -sfv /usr/local/opt/mysql/*.plist ~/Library/LaunchAgents`

Now, you want to configure the root user that you will be using:

`mysqladmin -u root password 'yourpassword'`

## Installing MySQL Workbench

You can find MySQL Workbench here: https://www.mysql.com/products/workbench/

MySQL Workbench will provide a number of tools and a GUI for actually viewing your data. You can (and should in most cases) just use the command-line and SQL to query your information, but the workbench is indispensible when it is inconvenient to do otherwise.

## Configuring

When you first run MySQL Workbench, you need to configure some settings to get your instance up and running. Next to "MySQL Connections", you can press a "+" button, where you will be confronted with a new panel. For the most part, these defaults will be correct. You will be running MySQL from localhost (127.0.0.1), at port 3306. You will be using the 'root' user, and then enter the password that you defined when you ran the `mysqladmin` command earlier.

Now everything should be set up and running properly.

## First Assignment!

You will be creating a small database of music, and each of these databases will have distinct *relationships* defined between them. Before you get started, get out a piece of paper, and sketch out a box for each of these, with each column that you would like to have. 

Each table will need a primary key (id), which is auto-incrementing and unique. Figure out which tables will need foreign keys, and what those foreign keys should be named.

* Genres
* Artists
* Albums
* Songs

### Relationships

When working with relational databases, it's important to think about what type of relationship tables have to each other. Here are the main types of relationships you need to think about through this:

#### One to One
  
*One* record on Table A has *one* related record on Table B.

#### One to Many

*One* record on Table A has *many* related records on Table B.

#### Many to Many

*Many* records on Table A can have *many* related records on Table B.

In the tables you are creating, define the relationship each will have to each other.

## SQL

Once you have added some records, and have defined your foreign keys between them, let's try our first queries. Here is a list of queries I'd like to see you complete:

* Get all Albums that belong to a Genre 
* Get all Songs in an Album
* Get all songs by an Artist
* Return all albums and songs for each artist
