UniMapper Flexibee extension
============================

Flexibee API integration with [UniMapper](http://unimapper.github.io).

[![Build Status](https://secure.travis-ci.org/unimapper/flexibee.png?branch=master)](http://travis-ci.org/unimapper/flexibee)

# Usage

> Supported is only JSON API.

```php
$config = [
    // Required
    "host" => "http://localhost:5434"
    "company" => "name"

    // Optional authentization
    "user" => ,
    "password" => ,

    // Optional SSL version
    "ssl_version" => 3
];
$adapter = new UniMapper\Flexibee\Adapter($config);

// Create new contacts
$response = $adapter->put("adresar.json", ["adresar" => ["sumCelkem" => ....]);

// Load created contacts
foreach ($response->results as $result) {
    $adapter->get("adresar/" . $result->code . ".json");
}
```
For more inromation see the docs on official [Flexibee](http://www.flexibee.eu) site.
