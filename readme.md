1. insert 500 data:
    BulkWriteResult({
        "writeErrors" : [ ],
        "writeConcernErrors" : [ ],
        "nInserted" : 1000,
        "nUpserted" : 0,
        "nMatched" : 0,
        "nModified" : 0,
        "nRemoved" : 0,
        "upserted" : [ ]
})

2. find all movies equal to movie_name:
    command and output:
    db.movie.find({movie_name:"Blink"}).pretty()
{
        "_id" : ObjectId("62663d9d563d8325dcf31d1e"),
        "id" : 5,
        "movie_name" : "Blink",
        "movie_genre" : "Thriller",
        "production_year" : 1974,
        "budget" : 18980
}
3. find all movies which are not equal to movie_name
        command and output:
         db.movie.find(!{movie_name:"Blink"}).pretty()
{
        "_id" : ObjectId("62663d9d563d8325dcf31d1a"),
        "id" : 1,
        "movie_name" : "Arthur and the Revenge of Maltazard (Arthur et la vengeance de Maltazard)",
        "movie_genre" : "Animation|Children|Fantasy",
        "production_year" : 1998,
        "budget" : 14768
}
{
        "_id" : ObjectId("62663d9d563d8325dcf31d1b"),
        "id" : 2,
        "movie_name" : "Light It Up",
        "movie_genre" : "Drama",
        "production_year" : 2008,
        "budget" : 18507
}

4. find all movies greater than and greater than equal to a budget

    command and output:
    db.movie.find({budget:{$gt:15000}}).pretty()
    db.movie.find({budget:{$gte:15000}}).pretty()
{
        "_id" : ObjectId("62663d9d563d8325dcf31d1b"),
        "id" : 2,
        "movie_name" : "Light It Up",
        "movie_genre" : "Drama",
        "production_year" : 2008,
        "budget" : 18507
}
{
        "_id" : ObjectId("62663d9d563d8325dcf31d1c"),
        "id" : 3,
        "movie_name" : "Cria! (Cría cuervos)",
        "movie_genre" : "Drama|Mystery",
        "production_year" : 2012,
        "budget" : 20404
}

5. find all movies less than and less than equal to a budget
    command and output:
    db.movie.find({budget:{$lt:10000}}).limit(2).pretty()
{
        "_id" : ObjectId("62663d9d563d8325dcf31d37"),
        "id" : 30,
        "movie_name" : "Let Him Have It",
        "movie_genre" : "Crime|Drama",
        "production_year" : 1986,
        "budget" : 8182
}
{
        "_id" : ObjectId("62663d9d563d8325dcf31d3f"),
        "id" : 38,
        "movie_name" : "Rainmaker, The",
        "movie_genre" : "Comedy|Romance|Thriller|Western",
        "production_year" : 2012,
        "budget" : 8370
}

6. find all movies that are produced after 2000 with budget greater than 10000

command and output: