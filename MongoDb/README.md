<p align="center">
    <img src="./src/mongodb.png" width="650"/>
</p>


# MongoDB

#### Ref: https://docs.mongodb.org/manual/

 

Is a database NoSQL ( not only sequel ) it means that is relevant is the "Question" and the data is not structured in tables.

- Main groups of NoSQL database
    + key/value  --> cache (fast), just access the key to bring the information
    + document   --> search using internal value.  Ex. search by email or telephone.
    + graph      --> Like a "metro map" point to point.  Ex. Neo4J
    + column     --> Ex. apache Cassandra
    + mixed      --> orientDB ( document + graph )


MongoDB is a database style schemaLess ( not have schema ) --> to use install mongoose.

- Formats
    + Json
    + Bson ( Binary Json) --> Ex. files.png  
        When dB collection greathen than RAM memory use "SHARDING" (break file in small parts)
    + Geolocation --> Save the ( lat x long ) in the mongoDB

- Relational Db x MongoDB
    + Database X Database
    + Table    X Collection
    + Rows     X document Json
    + partion  X Shard


# Install

- Update your system
    + Create a new directory 
    ```
        c:/data/db
        chmod 777 -Rf/data
    ```
    + visit <https://www.npmjs.com/package/mongodb>
    ```
        npm install -g mongodb --save
    ```
- Possible errors
    + sudo service mongodb restart
    
    error message: /var/lib/mongodb/mongod.lock
    + mongo -repair
    + service mongodb start
    + mongo

- Editor default
    .mongorc.js  --> EDITOR="vim"


#### Install other tools
    
mongoHacker --> better visual to use mongo in terminal <br>
    ```
        npm install -g mongo-hacker
    ```

    
mongoose   --> Make mongoDB use **Schema**  <br>
    ```
        npm install -g mongoose
    ```



