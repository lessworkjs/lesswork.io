# Database
> WIP

The default ORM is provided by [adonis-lucid](http://adonisjs.com/docs/3.2/lucid).


## Installation
Install `lesswork-lucid`
```bash 
npm install lesswork-lucid --save
```

Edit `config/app.js` and in your `providers` object add the following:
```js 
const providers = [
  ...
  'lesswork-lucid/providers/DatabaseProvider',
  'lesswork-lucid/providers/LucidProvider',
  'lesswork-lucid/providers/SchemaProvider',
  'lesswork-lucid/providers/SeederProvider',
  'lesswork-lucid/providers/MigrationsProvider',
  'lesswork-lucid/providers/FactoryProvider'
];
```


In your `commands` object add the following:
```js
const commands = {
  ...
  'Refresh': 'lesswork-lucid/src/Commands/Refresh',
  'Reset': 'lesswork-lucid/src/Commands/Reset',
  'Rollback': 'lesswork-lucid/src/Commands/Rollback',
  'Run': 'lesswork-lucid/src/Commands/Run',
  'Seed': 'lesswork-lucid/src/Commands/Seed',
  'Status': 'lesswork-lucid/src/Commands/Status',
};
```

In your `alises` object add the following:
```js 
const aliases = {
  ...
  Factory: 'Adonis/Src/Factory',
  Database: 'Adonis/Src/Database',
  Model: 'Adonis/Src/Lucid',
};
```

In your `workProviders` object add the following:
```js 
const workProviders = [
  ...
  'lesswork-lucid/providers/CommandsProvider',
];
```

## Configuration
The database configuration is located in `config/database.js`.

You will need to install the dependencies for whatever database you choose, ie:

```bash
npm install mysql
```

View the [adonis database docs](https://adonisjs.com/docs/3.2/database-setup).

## Usage 
> WIP
Once installed you can use the `database` with the `use` command.

```js
const db = use('Database');
```

View the [adonis query builder docs](https://adonisjs.com/docs/3.2/query-builder)

## Lucid 
> WIP 

Create the file `User.js` in `app/Models`

```js
class User extends use('User') {

}

module.exports = User;
```

Now you can `use` it in your controllers:


```js 
* get() {
    const User = use('App/Models/User')

    const users = yield User.all();

    this.Response.success(users);
  }
```

View the [adonis lucid docs](https://adonisjs.com/docs/3.2/lucid)


## Migrations
> WIP

Lessworks migration command names are under the `migrate` namespace to match Laravels.

View the [adonis migration docs](https://adonisjs.com/docs/3.2/migrations)

## Seeds & Factories 
> WIP 

Create `database/factory.js`

```js
const Factory = use('Factory')

Factory.blueprint('App/Model/User', (fake) => {
  return {
    username: fake.username(),
    email: fake.email(),
    password: fake.password(),
    firstName: fake.first(),
    lastName: fake.last()
  }
})
```




View the [adonis seeds and factories docs](https://adonisjs.com/docs/3.2/seeds-and-factories)