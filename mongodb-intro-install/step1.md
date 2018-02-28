In this step you will download the binaries of MongoDB latest version on an _Ubuntu_ server

## Download the MongoDB binaries

Since the current tutorial is running on _Ubuntu_ server let's download the binaries for _Ubuntu_ and uncompress it using below commands.

`wget http://downloads.mongodb.org/linux/mongodb-linux-x86_64-ubuntu1604-3.6.3.tgz
tar xzvf mongodb-linux-x86_64-ubuntu1604-3.6.3.tgz
`{{execute}}

## Setup the environment

Setup the environment using below commands before you start the MongoDB. They will

* Configure the environment variable _PATH_
* Create directory for storing the _datafiles_

`cd mongodb-linux-x86_64-ubuntu1604-3.6.3/bin
export PATH=$(pwd):$PATH
mkdir -p ~/data/db
`{{execute}}

## Start the MongoDB server

The default settings for _datafiles_ is _/data/db_. You can specify an alternate path for _datafiles_ using the _--dbpath_ option as show below. Run the below command to start the server with the _--dbpath_ and _--logpath_ overrides 

`./mongod --dbpath ~/data/db --logpath ~/data/mongod.log --fork`{{execute}}

## Launch a Mongo Shell

Then type the following to start the Mongo shell.

`./mongo`{{execute}}

Display available commands.

`help`{{execute}}

Display available databases.

`show dbs`{{execute}}

To use a particular database (lets say myappdb) we can type the following.

`use myappdb
db`{{execute}}

To create a collection and insert a document into it, run the below command

`db.users.insert({fname: 'Shyam', lname: 'Arjarapu'})`{{execute}}

To see all the collections with in the database, run the following command

`show collections`{{execute}}

To see the document we just created, run the following command

`db.users.find()`{{execute}}