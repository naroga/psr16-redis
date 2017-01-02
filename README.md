# Redis Cache

This is a simple Redis driver that implements PSR-16.

## Installation

Install using composer:

    $ composer require naroga/redis-cache
   
That's it.

`naroga/redis-cache` adheres to [SemVer](http://semver.org/).

## Usage

`naroga/redis-cache` extends `predis/predis`, so the client
object should be constructed with the same parameters as `predis/predis`.

You can check [Predis' documentation here](https://github.com/nrk/predis#connecting-to-redis).

```php
<?php

require_once "vendor/autoload.php";

use Naroga\RedisCache\Redis;

$config = [
    'scheme' => 'tcp',
    'host' => 'localhost',
    'port' => 6379
]

$redis = new Redis($config);

if (!$redis->has('myKey')) {
    $redis->set('myKey', 'myValue', 1800); //Just call any PSR-16 methods here.
}
```

## License

This library is released under the MIT license. Check [LICENSE.md](LICENSE.md) for more information .