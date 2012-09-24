About Towsta PHP
================

This is a lib to integrate your application with the Towsta's API in a PHP project. To use this lib, all you need is to paste the folder "towsta" in your project and `include()` its files.

Towsta Secret
-------------

Before being able to synchronize, you need to define your Towsta's Secret. To do so, all you need is to define the constant "TOWSTA_SECRET";

Modules
-------

For every module on your Towsta project, this lib will generate a file containing the respective class. So if you have a module named "Books", you will have a file "book.php", containing the class "Book" extending from "Towsta" class.

You can change the location of "modules" folder by defining the constant "MODULE_FOLDER";

Synchronizer
------------

Using the method `sync_with_towsta()` you can choose which items from Towsta will be synchronized to each request. The function accepts an array of arrays as parameter, according to Towsta's API. Ex: `sync_with_towsta( array( 'Book' => array( 'all' => 'true' ) ))`.

Module's Classes
----------------

Each module has its own class, with the following methods:

* `static::all()` - Returns an array with all the synchronized instances of this module;

* `static::first()` - Returns the first instance of the synchronized objects (very useful to syncs using "id" as condition);

* `static::attributes()` - Lists all the modules attributes as an array formated like:  `'attribute_name' => 'attribute_type'`;

* `get()` - Returns the object attribute. Ex: `$book->get('title')` will return the referenced book's title;

* `set()` - Sets a new value to the chosen attribute. Ex: `$book->set('title', 'Lord of the Rings')`;
