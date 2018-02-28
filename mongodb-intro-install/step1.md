In this step you will download the binaries of MongoDB latest version on an ubuntu server

## Download the MongoDB binaries

Before we get started first we need to download MongoDB binaries. Current tutorial is running on _Ubuntu_. So download the binaries for _Ubuntu_ and uncompress it using below commands.

`wget http://downloads.mongodb.org/linux/mongodb-linux-x86_64-ubuntu1604-3.6.3.tgz
tar xzvf mongodb-linux-x86_64-ubuntu1604-3.6.3.tgz
`{{execute}}

## Setup the environment

Before you start the MongoDB server, first you need to setup the environment. Below commands will
* Configure the environmenth _PATH_
* Create directory for storing the data files

`cd mongodb-linux-x86_64-ubuntu1604-3.6.3/bin
export PATH=$(pwd):$PATH
mkdir -p ~/data/db
`{{execute}}

## Start the MongoDB server

Now we are ready to start the server. The default settings for _data files_ is configured to be _/data/db_. You can specify an alternate path for data files using the _--dbpath_ option. Run the below command to start the server in a background process with the dbpath override 

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

To create a collection run the below commands

`db.users.insert({fname: 'Shyam', lname: 'Arjarapu'})
db.users.find()`{{execute}}

To see all the collections with in the database, run the following command

`show collections`{{execute}}