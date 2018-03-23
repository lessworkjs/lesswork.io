# Redis
Redis is provided by [adonis-redis](http://adonisjs.com/docs/3.2/redis).

## Installation
Install redis
```bash 
npm install redis --save
npm install adonis-redis --save
```

Edit `config/app.js` and in your `providers` object add the following:
```js 
'adonis-redis/providers/RedisFactoryProvider',
'adonis-redis/providers/RedisProvider',
```

Edit `config/app.js` and in your `alises` object add the following:
```js 
Redis: 'Adonis/Addons/Redis'
```
## Configuration
The redis configuration is located in `config/redis.js`.



## Usage 
Once installed you can use `redis` with the `use` command.

```js
'use strict';

class HelloWorldController extends require('lesswork-framework/Controller') {
  constructor() {
    this.redis = use('Redis');
  }

  get() {
    const phrase = this.redis.get('phrase');

    response.success({
      hello: phrase || 'world'
    });
  }
}

module.exports = HelloWorldController;
```

