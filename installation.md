# Installation

> Node 6 required. Use [n](https://www.npmjs.com/package/n) to switch.


## Install using the `lesswork-cli` tool:
```bash
npm i -g lesswork-cli
lesswork new app
```

Once installed you will be provided directions on how to create a sample route and start your dev server. 


## Ready to deploy?
Create a [aws credential](https://serverless.com/framework/docs/providers/aws/guide/credentials/) ([video](https://www.youtube.com/watch?v=bFHmgqbAh4M)) and insert it into `~/.aws/credentials` under a profile named `lesswork`
```text
[lesswork]
aws_access_key_id=
aws_secret_access_key=
```

When you're ready, deploy! 
```bash 
sls deploy 
```

## View your routes
When you run the dev server or deploy you will be provided a list of URLS or routes.

Browse to your `HelloWorld` route and you will see:
```json
{"hello":"world"}
```