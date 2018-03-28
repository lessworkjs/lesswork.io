# Env
> WORK IN PROGRESS

Env is provided by [adonis config](http://adonisjs.com/docs/4.0/configuration-and-env)

Access with the global variable `Env` or  with `use('Env')`.

## Env 
```js
Env.get('APP_ENV');
# Is the same as 
use('Env').get('APP_ENV');
```

## env 
`env()`

This global function allows you to access environment variables with defaults.
```js
env('APP_ENV', 'local');
```