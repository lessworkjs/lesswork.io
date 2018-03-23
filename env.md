# Env
> WORK IN PROGRESS

Env is provided by [adonis config](http://adonisjs.com/docs/4.0/configuration-and-env)

Access by injection with `use('Env')`.


## env 
`env()`

This global function allows you to access environment variables with defaults.
```js
env('APP_ENV', 'local');
```