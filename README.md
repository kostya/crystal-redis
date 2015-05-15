Redis Client for Crystal-Lang
================================

A Redis client for the Crystal programming language.


## Features

* Performance (> 260.000 commands per second using pipeline on a MacBook Air with a single client thread)
* Pipelining
* Transactions
* LUA Scripting
* All string commands
* All hash commands
* All list commands
* All set commands
* All hyperloglog commands
* All commands for bit operations
* All sorted set commands
* Publish/subscribe


## Installation

Add it to `Projectfile`

```crystal
deps do
  github "stefanwille/crystal-redis"
end
```

and then download the library into your project:

```crystal
$ crystal deps
```


## Required Crystal Version

This library needs Crystal version >= 0.7.1.


## Usage

Require the package:

```crystal
  require "redis"
```

then

```crystal
  redis = Redis.new
```

Then you can call Redis commands on the `redis` object:

```crystal
  redis.set("foo", "bar")
  redis.get("foo")
```

## Documentation

To get started,

* see this basic example: https://github.com/stefanwille/crystal-redis/blob/master/examples/basic.cr
* look at more examples: in https://github.com/stefanwille/crystal-redis/blob/master/examples/

API documentation is at http://stefanwille.github.io/crystal-redis/doc/

More details are available at:

* http://redis.io/commands - necessary, the API documentation is just a quick reference
* spec/redis.cr - offers more usage examples
* http://redis.io/documentation - general information about Redis and its concepts


## Performance

With this library I get > 260.000 commands per second using pipeline on a MacBook Air with a single client thread.

The equivalent program written in C with Hiredis gets me 340.000 commands per second.

Ruby 2.2.1 with redis-rb (https://github.com/redis/redis-rb) handles 50.000 commands per second.