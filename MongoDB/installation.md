# How to install MongoDB on Windows Subsystem for Linux(WSL) 2

MongoDB is one of the most popular databases for modern Web Development, especially for those using JavaScript and JSON in their applications. It fits well into the MERN Stack structure, and provides dynamic and scalable performance across the board.

## Install MongoDB on the command line
sudo apt-get install mongodb

## Get familiar with MongoDB services
1. mongod - Starts the local database server and runs it on the default port 27017
2. mongo - Runs the MongoDB shell

## Set up the local database
Normally, MongoDB's default directory for the database is /data/db.
```linux
cd /
sudo mkdir -p data/db
sudo chown -R `id -un` data/db
```
The final line in the terminal should be something like "Waiting for connections on port 27017".