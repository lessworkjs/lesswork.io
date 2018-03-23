> Create and deploy your own serverless applications using the [lesswork framework](https://github.com/Askedio/lesswork-framework).

# Features 
* Local development with `serverless-offline`.
* Testing with `mocha` with `nyc` code coverage.
* Documentation with `serverless-aws-documentation`.
* YAML Environment & JS Configurations.
* IoC by `adonis-fold`.


# Thanks
Thanks to `adonisjs`. Without it this wouldn't be possible.

Thanks to `laravel`. Without it I wouldn't know what eloquent code looks like.


# TO-DO
## lesswork app
* install frontend like laravel and adonis do
```
lesswork new ./app
```
## vendor publish
* copy configs, or w/e, from vendors, like laravel

## dynamodb
* good for default configuration examples

## auth: jwt, get token
* create a post route example that returns a valid token 
* change 'secret' to get from config

## make commands 
* need dupe prevention 

## provider command 
* create app/Providers and store provider there 
* warn user to add to providers object in config/app.js


## adonis orm commands
* implement the seed and migration commands


## exceptions
* create an exception handler and throw correct callbacks
* allow users to create their own exceptions'

## mocks
* testing and stuff..

## add events to code base 
* like in kernel or startup, register globals, etc

## translations 
* nothing fancy, resources/lang folder like laravel 


