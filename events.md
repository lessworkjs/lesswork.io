# Events
This feature is provided by [adonis events](https://adonisjs.com/docs/3.2/events)

## Create a listerner

Controllers are created with the `work` command.


```bash
node work make:listener HelloWorld
```

This creates the file `app/Listeners/HelloWorldListener.js`.

```js
'use strict';

class HelloWorldListener {
  
}

module.exports = new HelloWorldListener();
```