# Configuration
## Environment
Create your applications environment file. 
```bash
cp .env.example.yml .env.yml
```

Here you can define YAML based variables that will be used in your application and `serverless` configuration.

### Get Environment Settings
Environment settings can be accessed from the `env()` helper or the `process.env` object.

The `env()` helper will allow you to use a default.
```js
env('APP_ENV', 'local');
// or 
process.env.APP_ENV || 'local';
```

### Get Current Environment
```js
app.environment(); // returns APP_ENV
app.environment('local'); // boolean if APP_ENV is local
app.environment(['production', 'staging']); // boolean if any match APP_ENV
app.environment('production', 'staging'); // same as above
```


## Configs
Other configuration files are stored in the `config` folder. 

These are javascript based configuration files and can be accessed from the `config` helper.

```js
config.get('database.connection', 'default');
```