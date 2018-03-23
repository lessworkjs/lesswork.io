# Commands
Commands are provided by [adonis-ace](http://adonisjs.com/docs/4.0/ace)

## Create a command

Commands are created with the `work` command.


```bash
node work make:command HelloWorld
```

This creates the file `app/Console/Commands/HelloWorldCommand.js`.

```js
const {
  Command
} = require('lesswork-cmd');

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
node work example:HelloWorld
```