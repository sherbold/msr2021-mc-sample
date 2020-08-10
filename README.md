# SmartSHARK MSR 2021 - Mining Challenge Application

This repository contains sample data and analysis scripts for our MSR mining challenge application. The sample consists of our data for one of the smaller projects in our database, i.e., [Apache Giraph](https://giraph.apache.org/).

(Rough draft)

## Preparation of the Database

- [Install MongoDB](https://docs.mongodb.com/manual/installation/#install-mongodb)
- Download sample database of giraph:
  - [Full Version (203 MB)](https://user.informatik.uni-goettingen.de/~sherbol/smartshark_sample.agz)
  - [Without software metrics and static analysis (43 MB)](https://user.informatik.uni-goettingen.de/~sherbol/smartshark_sample_small.agz)
- Run [mongorestore](https://docs.mongodb.com/database-tools/mongorestore/) to load the data into your local database.

For example, on Ubuntu 18.04, this could be achieved with the following instructions. 

```
wget -qO - https://www.mongodb.org/static/pgp/server-4.0.asc | sudo apt-key add -
echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.0.list
sudo apt-get update
sudo apt-get install -y mongodb-org
sudo systemctl daemon-reload
sudo systemctl start mongod
cd ~
wget https://user.informatik.uni-goettingen.de/~sherbol/smartshark_sample.agz
mongorestore smartshark_sample.agz
```

## Running the Notebook

- Create venv
- Install requirements (missing)
- Run `jupyter notebook` and open in browser
