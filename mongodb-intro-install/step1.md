In this step you will download the binaries of MongoDB latest version on an ubuntu server

## Download the MongoDB binaries

Before we get started first we need to download MongoDB binaries. Current tutorial is running on _Ubuntu_. So download the binaries for _Ubuntu_ and uncompress it using below commands.

`wget http://downloads.mongodb.org/linux/mongodb-linux-x86_64-ubuntu1604-3.6.3.tgz
tar xzvf mongodb-linux-x86_64-ubuntu1604-3.6.3.tgz
`{{execute}}

## Setup the environment

Before you start the MongoDB server, first you need to create setup the environment. Below commands will
* Configure the environmenth _PATH_
* Create directory for storing the data files

`cd mongodb-linux-x86_64-ubuntu1604-3.6.3/bin
export PATH=$(pwd):$PATH
mkdir -p ~/data/db
`{{execute}}

## Start the MongoDB server

Specify an alternate path for data files using the --dbpath option. 
`./mongod --dbpath ~/data/db`{{execute}}