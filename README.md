# MongoDB-Dockerized-Container

Project Description
This project is done on docker container creating a containerized Mongodb environment. 
Showing all the commands that are required for any naïve user to understand the basics of Mongodb.
command 1 - 10 shows how to initialize the mongodb environment in docker container 
along with uploading the user data in the database.
While the main commands section shows the basics of mongodb. A total of 59 commands has been
used in this assignment containing the topics such as (Aggregation, Replication, Counting,
Condition based search, regex search etc.)
Dataset Description
IMDB movies dataset is collected from Kaggle website. Following is the information about
the dataset.
Element Description
Dataset Filesize 405 Megabytes
Dataset Shape 600,000+ movies
Dataset (Movies Description) International Movies (USA, India, Russia, China etc.)
Dataset File Format Json
Dataset Source Kaggle
Dataset Drive Download Link drive.google...../view
Dataset Kaggle Download Link Kaggle.com/...-movies
Each doc contains the following information.
Element Type Description
Id String (unique) Unique id for each movie
ImdbId String (unique) Unique ImdbId for each movie
Name String Name of the movie
Poster_url String Url of the poster of movie
Year String Released year of the movie
Certificate String Certificate giving to movieEg. MA- 17 etc
Runtime String Runtime of the movie^
Genre Array Comedy, Horror etc^
RatingValue String Rating of the movie^
Summary_text String Plot of the movie^
ratingCount Numeric Total number of people giving rating^
Director Object Name of the director along with director id^
Cast Array of Object Cast of the movie^
1) docker-compose up -d
Creating network "mongodb_default" with the default driver
Pulling mongodb (mongo:)...
latest: Pulling from library/mongo
7c3b88808835: Pull complete
48a403577c28: Pull complete
76bbb7dc9013: Pull complete
e81b1e5a386b: Pull complete
7bdc1db49ec9: Pull complete
7b2f602f894c: Pull complete
627a84bea5f4: Pull complete
fc06fa2a9f52: Pull complete
0133c89ee92b: Pull complete
4e990167b745: Pull complete
Digest: sha256:03ef0031c1642df26d9d3efa9d57e24929672e1ae7aba5818227752089adde
Status: Downloaded newer image for mongo:latest
Creating mongodb ... done
_____________________________________________________________________________________________________________________________
2) docker ps
CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES
a0f80020ef88 mongo "docker-entrypoint.s..." 27 minutes ago Up 27 minutes 0.0:27017->27017/tcp Mongodb
_____________________________________________________________________________________________________________________________
3 ) docker exec -it mongodb bash
root@a0f80020ef88:/#
4) root@a0f80020ef88:/# cd data/db
6) mongoimport movies.json -d moviesdb -c moviescollection --jsonArray
2022 - 03 - 16T05:31:55.147+0000 connected to: mongodb://localhost/
2022 - 03 - 16T05:31:58.147+0000 [##......................] moviesdb.moviescollection 36.4MB/396MB (9.2%)
2022 - 03 - 16T05:32:01.147+0000 [####....................] moviesdb.moviescollection 73.3MB/396MB (18.5%)
2022 - 03 - 16T05:32:04.147+0000 [######..................] moviesdb.moviescollection 110MB/396MB (27.7%)
2022 - 03 - 16T05:32:07.147+0000 [########................] moviesdb.moviescollection 146MB/396MB (36.7%)
2022 - 03 - 16T05:32:10.147+0000 [##########..............] moviesdb.moviescollection 181MB/396MB (45.6%)
2022 - 03 - 16T05:32:16.147+0000 [###############.........] moviesdb.moviescollection 253MB/396MB (63.8%)
2022 - 03 - 16T05:32:19.147+0000 [#################.......] moviesdb.moviescollection 289MB/396MB (72.8%)
2022 - 03 - 16T05:32:22.147+0000 [###################.....] moviesdb.moviescollection 325MB/396MB (81.9%)
2022 - 03 - 16T05:32:25.147+0000 [#####################...] moviesdb.moviescollection 361MB/396MB (91.0%)
2022 - 03 - 16T05:32:28.049+0000 [########################] moviesdb.moviescollection 396MB/396MB (100.0%)
2022 - 03 - 16T05:32:28.049+0000 633719 document(s) imported successfully. 0 document(s) failed to import.
7) mongo
Starting the mongodb inside docker container using “mongo” command.
8 ) show databases
admin 0.000GB
config 0.000GB
local 0.000GB
moviesdb 0.199GB
Explanation: As you can see now our moviedb database has been imported
9 ) use moviesdb
switched to db moviesdb
10) show collections
moviescollection
