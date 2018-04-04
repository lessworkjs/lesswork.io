# Database
> WIP

The default ORM is provided by [adonis lucid](https://adonisjs.com/docs/4.1/lucid), [repo](https://github.com/adonisjs/adonis-lucid).

# MySQL 
> We recommend DyanmoDB!

You may have connection issues with MySQL and other similar databases.  

## Installation

```bash 
npm install @adonisjs/lucid
```

Edit `config/app.js` and in your `providers` object add the following:
```js 
const providers = [
  ...
  '@adonisjs/lucid/providers/LucidProvider',
];
```


In your `commands` object add the following:
```js
const commands = {
  ...
  'Refresh': '@adonisjs/lucid/src/Commands/MigrationRefresh',
  'Reset': '@adonisjs/lucid/src/Commands/MigrationReset',
  'Rollback': '@adonisjs/lucid/src/Commands/MigrationRollback',
  'Run': '@adonisjs/lucid/src/Commands/MigrationRun',
  'Seed': '@adonisjs/lucid/src/Commands/Seed',
  'Status': '@adonisjs/lucid/src/Commands/MigrationStatus',
};
```



In your `workProviders` object add the following:
```js 
const  = [
  ...
  '@adonisjs/lucid/providers/MigrationsProvider',
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
 get() {
    const User = use('App/Models/User')

    const users = yield User.all();

    this.Response.success(users);
  }
```

View the [adonis lucid docs](https://adonisjs.com/docs/3.2/lucid)


## Migrations
> WIP

Lessworks migration command names are under the `migrate` namespace to match Laravels.

View the [adonis migration docs](https://adonisjs.com/docs/4.1/migrations)

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




View the [adonis seeds and factories docs](https://adonisjs.com/docs/4.1/seeds-and-factories)