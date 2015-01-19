Mongoose valid id is a mongoose plugin that adds a `isValidId` static method to the model that can be used to check 
if a passed id is a valid mongoose/mongodb id.

## Installation

    $ npm install mongoose-valid-id

## Usage

    var mongoose = require('mongoose');
    var Schema = mongoose.Schema;
    var validId = require('mongoose-valid-id');

    var Page = new Schema({
        title : { type : String, required : true},
        content : { type : String, required : true },
        path : { type : String, required : true},
        tags : [String],

        lastModified : Date,
        created : Date
    });

    Page.plugin(mongoose-valid-id);
	
Use the `isValidId` static method

    var Page = require('page');
	
	Page.isValidId('someid'); // Returns false
	Page.isValidId('543be48d3b1b8a601ca20990'); // Returns true
