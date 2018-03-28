# Structure

## Introduction
Lesswork ships with a minimal directory structure. 

Many directories are created with `make` commands. You can also browse the documentation for examples.

## Root Directories
####  `app`
This directory contains the core off your application. Everything here will be `autoloaded` into your applications container.

####  `config`
This directory contains all of the `javascript` based configuration files.

#### `routes`
This directory contains all of your routes. You can group routes by creating multiple files.

####  `test`
This directory contains your `mocha` tests.

#### `resources`
This directory contains your language files in locale directories.

## App Directories 

####  `Console` 
* Commands
This directory contains your `lesswork` console commands.


####  `Http`
The follow folders are all `autoloaded` as `serverless` functions.
* Controllers
* Authentication
* Functions

####  `Listeners`
This directory contains your listener files.



