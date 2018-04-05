# Installation

> Node 8.10 is required. 

Download & install [node](https://nodejs.org/en/download/) then use [n](https://www.npmjs.com/package/n) to switch between versions.
```bash
npm i n -g
n 8.10
```


## Install Lesswork
Lesswork is installed and managed with its own global application.

> Once installed you will be provided directions on how to create a sample endpoint and start your dev server. 

```bash
npm i -g serverless with-lesswork
lesswork new ./app
```

## Local Development Server
You can launch your application with [serverless-offline](https://www.npmjs.com/package/serverless-offline) for local development.

```js 
lesswork serve
```

## Playing Around
Use the included [repl](https://nodejs.org/api/repl.html) terminal to play around.

```js
lesswork tinker
```

## Deploying
Create a [aws credential](https://serverless.com/framework/docs/providers/aws/guide/credentials/) ([video](https://www.youtube.com/watch?v=bFHmgqbAh4M)) and insert it into `~/.aws/credentials` under a profile named `lesswork`
```text
[lesswork]
aws_access_key_id=
aws_secret_access_key=
```

When you're ready, deploy! 
```bash 
sls deploy --stage=production
```