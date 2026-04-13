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

# Main Commands
1) Following method retrieves all the documents in the collection
    db.moviescollection.find()
2) findOne() method, that returns only one document
    db.moviescollection.findOne()
3) The following operation counts the documents in a collection of moviesdb
    db.moviescollection.aggregate( [{ $count: "total_number_of_movies" }])
4) Converting ratingValue field to float to make certain operations applicable on it.
    db.moviescollection.find().forEach((d) => {
    d["ratingValue"] = parseFloat(d["ratingValue"]);
    db.moviescollection.save(d);
    });
