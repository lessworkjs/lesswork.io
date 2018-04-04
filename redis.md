# Redis
Redis is provided by [adonis-redis](https://adonisjs.com/docs/4.1/redis).

## Installation
Install redis
```bash 
npm install redis --save
npm install @adonisjs/redis --save
```

Edit `config/app.js` and in your `providers` object add the following:
```js 
'@adonisjs/redis/providers/RedisProvider',
```


## Configuration
The redis configuration is located in `config/redis.js`.


## Usage 
Once installed you can use `redis` with the `use` command.

```js
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

