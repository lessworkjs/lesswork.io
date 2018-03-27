# Localization
> WIP 

Formatting provided by [intl-messageformat](https://www.npmjs.com/package/intl-messageformat).

Translation files are stored in `resources/lang/{locale}`.

# Create the translation resource.
Create the file `recourese/lang/en-US/messages.js`

```js
module.exports = {
  'welcome': 'Welcome to our application',
};
```

# Get a translation

```js 
__('message.welcome');

# Is the same as
trans('message.welcome');

# Is the same as
const Lintl = use('Lintl');
const translated = Lintl.translate('message.welcome');
```


# Change Localization
```js 
App.setLocale('en-ES');
App.isLocale('en-ES'); // true
App.getLocale(); // en-ES
```


# Formatting Numbers 
You can format numbers with [int numberFormat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NumberFormat).

```js
numberFormat(123, {
      style: 'currency',
      currency: 'EUR'
});

# Is the same as 
const Lintl = use('Lintl');
Lintl.numberFormat(123, {
    style: 'currency',
    currency: 'EUR'
});
```

# Formatting Dates
You can format dates with [int dateFormat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/DateTimeFormat).

```js
const date = dateFormat(new Date());

# Is the same as 
const Lintl = use('Lintl');
Lintl.dateFormat(new Date());
```