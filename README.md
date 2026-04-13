# MongoDB-Dockerized-Container

# Docker Commands
1) docker-compose up -d
2) docker ps
3) docker exec -it mongodb bash
4) root@a0f80020ef88:/# cd data/db
5) mongoimport movies.json -d moviesdb -c moviescollection --jsonArray
6) mongo - Starting the mongodb inside docker container using “mongo” command.
7) show databases - As you can see now our moviedb database has been imported
8) use moviesdb - switched to db moviesdb
9) show collections - moviescollection
