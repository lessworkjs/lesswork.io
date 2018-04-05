# Configuration
## Environment
Your env file is `.env`.

Here you can define variables that will be used in your application and `serverless` configuration.

### Get Environment Settings
Environment settings can be accessed from the `env()` helper or the `process.env` object.

The `env()` helper will allow you to use a default.
```js
env('APP_ENV', 'local');

# is the same as

Env.get('APP_ENV', 'local');

# is the same as

process.env.APP_ENV || 'local';
```

### Get Current Environment
```js
App.environment(); // returns APP_ENV
App.environment('local'); // boolean if APP_ENV is local
App.environment(['production', 'staging']); // boolean if any match APP_ENV
App.environment('production', 'staging'); // same as above
```


## Configs
Other configuration files are stored in the `config` folder. 

These are javascript based configuration files and can be accessed from the `config` helper.

```js
config('database.connection', 'default');

# is the same as

Config.get('database.connection', 'default');
```