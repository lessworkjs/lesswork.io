# Database
> WORK IN PROGRESS

The default ORM is provided by [adonis-lucid](http://adonisjs.com/docs/3.2/lucid).


## Installation
Install `adonis-lucid`
```bash 
npm install adonis-lucid --save
```

Edit `config/app.js` and in your `providers` object add the following:
```js 
'adonis-lucid/providers/DatabaseProvider',
'adonis-lucid/providers/LucidProvider',
'adonis-lucid/providers/FactoryProvider'
```

Edit `config/app.js` and in your `alises` object add the following:
```js 
Database: 'Adonis/Src/Database'
```
## Configuration
The database configuration is located in `config/database.js`.



## Usage 
Once installed you can use the `database` with the `use` command.

```js
const db = use('Database');
```

