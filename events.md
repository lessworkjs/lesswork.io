# Events
This feature is provided by [adonis events](https://adonisjs.com/docs/4.1/events)

## Create a listener

Controllers are created with the `lesswork` command.


```bash
lesswork make:listener HelloWorld
```

This creates the file `app/Listeners/HelloWorldListener.js`.

```js
'use strict';

class HelloWorldListener {
  
}

module.exports = new HelloWorldListener();
```