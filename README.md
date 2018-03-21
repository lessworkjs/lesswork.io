# overview

> Create and deploy your own AWS serverless application based on the nodejs [lesswork framework](https://github.com/Askedio/lesswork-framework).

# features
* Local development with `serverless-offline`.
* Testing with `mocha` and `serverless-mocha-plugin`.
* Code coverage with `nyc`.
* Documentation with `serverless-aws-documentation`.
* YAML based environment & configurations.

# install
1. Create your [aws credentials](https://serverless.com/framework/docs/providers/aws/guide/credentials/) ([video](https://www.youtube.com/watch?v=bFHmgqbAh4M)) and insert them into `~/.aws/credentials` under a profile named `lesswork`
```text
[lesswork]
aws_access_key_id=
aws_secret_access_key=
```

2. Download [lesswork](https://github.com/lessworkjs/lesswork), install serverless, install lesswork, deploy:
```bash
npm install -g serverless
npm install
npm run deploy
```

3. Browse to your `/dev/helloWorld` route. You should see:
```json
"Hello World!"
```


