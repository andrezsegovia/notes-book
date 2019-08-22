# Mongoose Module

Mongoose is a module that connects Node.js to MongoDB in an **object document mapper (ODM)** style. It offers the Create, Read, Update, and Delete (also known as CRUD) functionalities for documents stored in the database. Mongoose defines the structure of the used documents using schemas.

Mongoose introduces the term **model**. A model is a constructor-like function compiled out of a schema definition. An instance of a model represents a document that can be saved to or read from the database.

A model also exposes function for querying and data manipulation. 

To install Mongoose we need to run the following command:

```bash
npm intall mongoose
```

In the next code we create a Schema and a Model for the Catalog Item, establish a connection, then we create a new item and retrieve it from database.

```javascript
const mongoose = require('mongoose');

var Schema = mongoose.Schema;
var itemSchema = new Schema({
    "itemId": { type: String, index: { unique: true } },
    "itemName": String,
    "brand": String,
    "price": Number,
    "currency": String,
    "catagories": [String]
});

var CatalogItem = mongoose.model('Item', itemSchema);


mongoose.connect('mongodb://172.19.0.2:27017/catalog');
var db = mongoose.connection;

db.on('error', console.error.bind(console, 'connection error:'));
db.once('open', function(){
    var watch = new CatalogItem({
        itemId: 9,
        itemName: 'Sports Watch1',
        brand: 'A1',
        price: 100,
        currency: 'EUR',
        catagories: ["Watches", "Sports Watches"]
    });

    watch.save((error, item, affecteNo) => {
        if(!error) {
            console.log('Item added successfully to the catalog');
        } else {
            console.log('Cannot add item to the catalog', error);
        }
    });
});
db.once('open', function(){
    var filter = {
        'itemName': 'Sports Watch1',
        'price': 100
    }
    CatalogItem.find(filter, (err, result) => {
        if(err) {
            console.log('Error occureed');
        } else {
            console.log('Results found:'+ result.length);
            console.log(result);
        }
    } )
});
```

