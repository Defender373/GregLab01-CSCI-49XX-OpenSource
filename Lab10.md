# Gregory Saini - Lab10

## Checkpoint 1
![4-5-2019osLabcheckpoint1](https://user-images.githubusercontent.com/17090994/55664100-efe75f80-57f6-11e9-9dd0-84363fb2b791.PNG)


## Checkpoint 2
![4-5-2019osLabcheckpoint2](https://user-images.githubusercontent.com/17090994/55664109-f07ff600-57f6-11e9-86af-3f61d560d3a9.PNG)


## Checkpoint 3
![4-5-2019osLabcheckpoint3part1](https://user-images.githubusercontent.com/17090994/55664108-efe75f80-57f6-11e9-8774-ba3dda7add82.PNG)

![4-5-2019osLabcheckpoint3part2](https://user-images.githubusercontent.com/17090994/55664107-efe75f80-57f6-11e9-883e-648e42c07439.PNG)

![4-5-2019osLabcheckpoint3part3](https://user-images.githubusercontent.com/17090994/55664106-efe75f80-57f6-11e9-890f-c0a6df133607.PNG)

![4-5-2019osLabcheckpoint3part4](https://user-images.githubusercontent.com/17090994/55664105-efe75f80-57f6-11e9-827f-6fa4f7caf704.PNG)

![4-5-2019osLabcheckpoint3part5](https://user-images.githubusercontent.com/17090994/55664104-efe75f80-57f6-11e9-8881-bd7af35b4af0.PNG)

![4-5-2019osLabcheckpoint3part6](https://user-images.githubusercontent.com/17090994/55664103-efe75f80-57f6-11e9-9e0f-f69a8ece00b9.PNG)

## Checkpoint 4
![4-5-2019osLabcheckpoint4part1](https://user-images.githubusercontent.com/17090994/55664102-efe75f80-57f6-11e9-9b40-d29a491d6633.PNG)

![4-5-2019osLabcheckpoint4part2](https://user-images.githubusercontent.com/17090994/55664101-efe75f80-57f6-11e9-9982-e965e6b40039.PNG)

``` python
from pymongo import MongoClient
from bson.objectid import ObjectId
import pprint
client = MongoClient('localhost', 27017)

if __name__ == '__main__':
    #Setup to allow us to access the database
    db = client.mongo_db_lab
    collection = db.definitions
        
    #Fetch all records
    for each in collection.find():
        pprint.pprint(each)
        
    #Fetch one record
    pprint.pprint(collection.find_one())
    
    #Fetch a specific record
    pprint.pprint( collection.find({"word": "Toad"}) )
    
    #Fetch a record by object id
    pprint.pprint(collection.find_one({"_id": ObjectId("56fe9e22bad6b23cde07b8b8")}))
    
    #Insert a new record
    new_profile = {'definition': ' n. Make Angular Great Again.', 'word': 'MAGA'}
    result = db.posts.insert_one(new_profile)
```    


## Checkpoint 5

