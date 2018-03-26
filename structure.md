# Structure

## Introduction
Lesswork ships with a minimal directory structure. 

Many directories are created with `make` commands. You can also browse the documentation for examples.

## Root Directories
####  `app`
This directory contains the core off your application. Everything here will be `autoloaded` into your applications container.

####  `bootstrap` 
This directory contains your application itself. You can modify these files.

####  `config`
This directory contains all of the `javascript` based configuration files.

####  `test`
This directory contains your `mocha` tests.

## App Directories 

####  `Console` 
* Commands
This directory contains your `lesswork` console commands.


####  `Http`
The follow folders are all `autoloaded` as `serverless` functions.
* Controllers
* Routes
* Authentication
* Functions

####  `Listeners`
This directory contains your listener files.



