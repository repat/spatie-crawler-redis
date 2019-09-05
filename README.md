# spatie-crawler-redis
[![Latest Version on Packagist](https://img.shields.io/packagist/v/repat/spatie-crawler-redis.svg?style=flat-square)](https://packagist.org/packages/repat/spatie-crawler-redis)
[![Total Downloads](https://img.shields.io/packagist/dt/repat/spatie-crawler-redis.svg?style=flat-square)](https://packagist.org/packages/repat/spatie-crawler-redis)

**spatie-crawler-redis** is an alternative CrawlerQueue implementing the `Spatie\Crawler\CrawlQueue\CrawlQueue` interface using Redis Hashes.

## Installation
`$ composer require repat/spatie-crawler-redis`

## Example
Create a `Predis\Client` beforehand if you need options, such as selecting a database. If you don't pass a client, a new one without options will be used. Predis assumes `127.0.0.1`, `6379` and `0` as default host, port and database. You can also pass a custom prefix, otherwise `uniqid()` will be used.

```php
// see https://github.com/nrk/predis for options
$options = [
    'database' => 7,
];

$prefix = uniqid() . ':'; // same as passing no prefix

$redisClient = new \Predis\Client($options);

// ...
->setCrawlQueue(new RedisCrawlQueue($redisClient, $prefix))

// uses new \Predis\Client without options
->setCrawlQueue(new RedisCrawlQueue())
```

## TODO
* `phpredis` support

## Testing
> Thanks spatie for the tests. These are the instructions:

To run the tests you'll have to start the included node based server first in a separate terminal window.

```bash
cd tests/server
npm install
./start_server.sh
```

With the server running, you can start testing.
```bash
vendor/bin/phpunit
```

## License
* MIT, see [LICENSE](https://github.com/repat/spatie-crawler-redis/blob/master/LICENSE)

## Version
* Version 0.1

## Contact
#### repat
* Homepage: https://repat.de
* e-mail: repat@repat.de
* Twitter: [@repat123](https://twitter.com/repat123 "repat123 on twitter")

[![Flattr this git repo](http://api.flattr.com/button/flattr-badge-large.png)](https://flattr.com/submit/auto?user_id=repat&url=https://github.com/repat/spatie-crawler-redis&title=spatie-crawler-redis&language=&tags=github&category=software)
