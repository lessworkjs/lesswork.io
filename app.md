A# App

Access with the global `app` or injected with `use('App')`.


## environment
`environment()`

```js
App.environment(); // returns APP_ENV
App.environment('local'); // boolean if APP_ENV is local
App.environment(['production', 'staging']); // boolean if any match APP_ENV
App.environment('production', 'staging'); // same as above
```


## run
`run(callbacks)`

This method allows you to run a named based class and method.

It supports `generators`.

```js
run('namespace/class@method');
```

## locales
> WIP 

* getLocale
* setLocale 
* isLocale