Google Address Field
================================================================================


[![Build Status](https://travis-ci.org/sunnysideup/silverstripe-google_address_field.svg?branch=master)](https://travis-ci.org/sunnysideup/silverstripe-google_address_field)

Provides an Auto-Complete field for addresses using the Google API.

see: http://gmaps-samples-v3.googlecode.com/svn/trunk/places/autocomplete-addressform.html


Developer
-----------------------------------------------
Nicolaas Francken [at] sunnysideup.co.nz


Requirements
-----------------------------------------------
see composer.json



Installation Instructions
-----------------------------------------------
1. Find out how to add modules to SS and add module as per usual.

2. Review configs and add entries to mysite/_config/config.yml
(or similar) as necessary.
In the _config/ folder of this module
you can usually find some examples of config options (if any).

3. the way to work with this field is not to make it replace existing fields, but to add it. After that you can add use the `setFieldMap` method to map your existing fields to data returned by Google. Here is a very basic example of how to place all the data into one field:
```php
		    $fields->insertBefore(
			    $addressField = new GoogleAddressField("AddressLookup", "Physical Address"),
			    "Address"
		    );
		    $addressField->setFieldMap(array("Address" => array("formatted_address" => "long_name")));
```

