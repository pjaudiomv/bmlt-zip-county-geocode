# bmlt-zip-county-geocode

*Backup your database, the maintainers of this script cannot be held responsible for things that could go wrong.*

This will geocode the zip and county data.  You will need to set 3 configuration values at the top of bmlt-zip-county-geocode.php.

```php
$table_prefix = "";  // database prefix for your MySQL sever
$google_maps_api_key = "";
$root_server = "";
$location_lookup_bias = ""; // Used for better geocoding results
```

more info on location_lookup_bias options can be found here. https://developers.google.com/maps/documentation/geocoding/intro#ComponentFiltering
the default is `country:us`

Once you are ready run it

`php bmlt-zip-county-geocode.php` 

or to send the output directly to a file 

`php bmlt-zip-county-geocode.php > geocode.sql`

You will get a list of `INSERT` queries to run on your root server MySQL.  Run them.

after running you may want to do a search to see if anylines contain `Could not geocode for address` and remove those lines. then you could go into your BMLT and see what went wrong with them, most likely address data is way out of wack or very generic.