# Elastic Mongo
**Docker setup to get Elasticsearch and MongoDB up and running**



### Install Docker and docker-compose

* https://docs.docker.com/installation
* https://docs.docker.com/compose/install/

```bash

git clone https://github.com/dolomitt/elastic-mongo.git
cd elastic-mongo
docker-compose up -d  # If you skip -d, then the entire clusted will go down when
                      # mongosetup and elasticsearch-river-setup are done.
```

Now you have Elasticsearch and MongoDB configured with mongodb-river.

```bash
$ docker ps  # =>

CONTAINER ID        IMAGE               COMMAND                CREATED             STATUS                  PORTS                                                NAMES
48f2b777abdf        mongo:3.1.5         "/usr/bin/mongod --r   2 seconds ago       Up 1 seconds            0.0.0.0:27017->27017/tcp, 0.0.0.0:28017->28017/tcp   elasticmongo_mongo1_1
7e6dd54b85e5        mongo:3.1.5         "/usr/bin/mongod --r   2 seconds ago       Up 1 seconds            0.0.0.0:27018->27017/tcp, 0.0.0.0:28018->28017/tcp   elasticmongo_mongo3_1
24e147982c2d        mongo:3.1.5         "/usr/bin/mongod --r   3 seconds ago       Up 2 seconds            0.0.0.0:27019->27017/tcp, 0.0.0.0:28019->28017/tcp   elasticmongo_mongo2_1

```

### Log into a container
```
docker exec -i -t elasticmongo_mongo3_1  bash
```
  
