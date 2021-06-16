# SmartSHARK MSR 2022 - Mining Challenge Application

This repository contains sample data and analysis scripts for our MSR mining challenge application. The sample consists of our data for one of the smaller projects in our database, i.e., [Apache Giraph](https://giraph.apache.org/).

Below, we describe how our data can be loaded and the example be executed. If you just want to look at the example, you can just [view it directly here on Github](https://github.com/sherbold/msr2022-mc-sample/blob/master/MSR-MC2022-Sample.ipynb). 

You can find our guide for using the full database [here](https://github.com/smartshark/usage-examples).

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
wget https://user.informatik.uni-goettingen.de/~sherbol/smartshark_sample.agz
mongorestore --gzip --archive=smartshark_sample.agz
```

## Running the Notebook

To run our python code, you only need our library [pycoshark](https://github.com/smartshark/pycoSHARK) and [Jupyter Lab](https://jupyter.org/install) (or any other app, that can work with Jupyter Notebooks). 

For example, you could run the following commands in your Ubuntu 18.04 machine to get everything running.

```
sudo apt-get install python3-venv build-essential python3-dev
git clone https://github.com/sherbold/msr2022-mc-sample.git
cd msr2022-mc-sample/
python3 -m venv venv
source venv/bin/activate
pip install pycoshark jupyterlab
```

You can just open the notebook in the browser and run our example.
