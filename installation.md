# Installation

> Node 6 required.


1. Create your [aws credentials](https://serverless.com/framework/docs/providers/aws/guide/credentials/) ([video](https://www.youtube.com/watch?v=bFHmgqbAh4M)) and insert them into `~/.aws/credentials` under a profile named `lesswork`
```text
[lesswork]
aws_access_key_id=
aws_secret_access_key=
```

2. Download [lesswork](https://github.com/lessworkjs/lesswork), install serverless, install lesswork, create an endpoint, and deploy:
```bash
wget https://github.com/lessworkjs/lesswork/archive/master.zip
unzip master.zip
cd lesswork-master
npm install -g serverless
npm install
node work make:endpoint HelloWorld
npm run deploy # or `npm run dev`
```

3. Browse to your `/dev/HelloWorld` route. You should see:
```json
{"hello":"world"}
```