# MongoDB commands

### Start project
    
```
    sudo service mongod start
```

#### Main commands

```
    mongo  --> start mongo
    show dbs  --> show the dbs
    **use** database_name ex. family  -->  Select your db or create a new database
    show collections
    db.dropDatabase()  --> Deleting the database
```

#### other commands
```
    db.family.count( { "name": "John" } ).count();
```

    



#### Import or Export files in the mongoDB
```
    mongoexport --db                --> database name 
                --collection        --> collection name
                --out               --> myCollection.json
                --host 127.0.0.1    --> host 

    mongoimport --db
                --collection
                --drop--file ifExistsFile.json
                --host 127.0.0.1
```

### REGEX  ( Regular Expression )
```
    q = { name: /father/i }   --> i (insensitive)
```



Handle data in the collection

#### Insert Data
```
    father = { "name": "The Father" , age: 60 }  --> Create a **json**  file with variable
    db.family.insert(father)  -->   Insert data in the **new collection**
```


#### Select Data
```
    db.family.find()
    db.family.findOne(father)  --> find The first or the first with name father
```


###  Update data
#### db.update( q , mod , options )  

```
    q = father
    mod = { $set: { key:  "value" } }    --> update or create the key:  value
    mod = { $unset: { key: "value" } }   --> delete 

    db.family.update(q, mod)
```
#### Update ( options )
    upsert: boolean   --> If not find it will create
    multi:  boolean   --> all registers
```
    q = { name: /the father/i } 
    mod= { $set: { active: true } }
    options: { upset:  true }  

    db.family.update(q, mod, options)
```


$setOnInsert   --> insert the key: if it don't exists. It works together with $set


```
    q = { "name": /mother/i }
    mod = {
        $set: { "active": true }
    ,   $setOnInsert: {
            name: 'mother'
        ,   age:  59
        ,   skills: 'a lot'
        }
    }
    
    options = { upsert: true }  --> if don't exists (create)
    
    db.family.update(q, mod, options)   --> Create all
```




#### Operators Math
```
    maxHeight = { height:  {  $gt: 1.83 } } 
    maxHeight = { height:  {  $gte: 1.83 } } 
    maxHeight = { height:  {  $lt: 1.83 } } 
    maxHeight = { height:  {  $lte: 1.83 } } 
```


#### Operators Math II
    Make accounts to increase or decrease
```
   mod = { $inc: { key: 100 } } 
   mod = { $inc: { key: -30 } }   --> decrease
```


#### Operators Logic
```

    q = { $or: [ { name: 'The father' }, { height: 1.70 } ] }   --> 'Or'
    q = { $nor: [ { name: 'The father' }, { height: 1.70 } ] }   --> 'Not or'
    q = { $and: [ { name: 'The father' }, { height: 1.70 } ] }   --> 'All conditions' 
```


#### Operators exists --> return if exists
```
    db.collection.find( { key:  {  $exists: true }  } )
```


#### Operators Array
    $push --> Create a new value in the key:     
    ps: if not exists the key OR it's not Array trow a error
    $pushAll  --> array of values at same time
```
    mod = { $push: { skills: 'a new skill' } } 
    mod = { $pushAll: { skills: [ 'a new skill' , 'other skill', 'and a lot of'  ]   } } 

    db.family.update( q , mod )
```


    $pull --> Delete value in the key:    
    $pullAll  --> Delete array
```
    mod = { $pull: { skills: 'trow skill' } } 
    mod = { $pullAll: { skills: [ values ]   } } 

    db.family.update( q , mod )
```





    








   
