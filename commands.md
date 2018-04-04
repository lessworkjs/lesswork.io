# Commands
Commands are provided by [adonis-ace](http://adonisjs.com/docs/4.0/ace)

## Create a command

Commands are created with the `lesswork` command.


```bash
lesswork make:command HelloWorld
```

This creates the file `app/Console/Commands/HelloWorldCommand.js`.

```js
const {
  Command,
} = require('@adonisjs/ace');

class HelloWorldCommands extends Command {

  static get signature() {
    return 'example:HelloWorld';
  }

  static get description() {
    return 'Command description';
  }

  handle() {
    console.log(`Command executed.`);
  }

}

module.exports = HelloWorldCommands;
```

## Execute a command

```bash
lesswork example:HelloWorld
```