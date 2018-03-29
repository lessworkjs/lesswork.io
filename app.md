# App

Access with the global `App` or injected with `use('App')`.


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
App locale settings adjust your applications localization. 
 

### getLocale()
Get the apps locale.

```js
console.log(App.getLocale());
// en-US
```

### setLocale(locale)
Change the apps locale.

```js
App.setLocal('en-ES');
```

### isLocale(locale)
Check to see the apps locale matches the paramater.

```js
App.isLocale('en-ES');
// true
```