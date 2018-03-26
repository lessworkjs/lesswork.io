# App

Access with the global `app` or injected with `use('App')`.


## environment
`environment()`

```js
app.environment(); // returns APP_ENV
app.environment('local'); // boolean if APP_ENV is local
app.environment(['production', 'staging']); // boolean if any match APP_ENV
app.environment('production', 'staging'); // same as above
```


## run
`run(callbacks)`

This method allows you to run a named based class and method.

It supports `generators`.

```js
run('namespace/class@method');
```