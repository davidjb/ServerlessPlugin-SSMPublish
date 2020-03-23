# :zap: serverless-ssm-publish
[![serverless](http://public.serverless.com/badges/v3.svg)](http://www.serverless.com)
[![npm version](https://badge.fury.io/js/serverless-ssm-publish.svg)](https://badge.fury.io/js/serverless-ssm-publish)
[![npm downloads](https://img.shields.io/npm/dt/serverless-ssm-publish.svg?style=flat&logo=npm)](https://www.npmjs.com/package/serverless-ssm-publish)
[![MIT licensed](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/ColdFire87/serverless-ssm-publish/master/LICENSE)
[![Coverage Status](https://coveralls.io/repos/github/ColdFire87/serverless-ssm-publish/badge.svg?branch=develop)](https://coveralls.io/github/ColdFire87/serverless-ssm-publish?branch=develop)
[![Build Status](https://travis-ci.org/ColdFire87/serverless-ssm-publish.svg?branch=develop)](https://travis-ci.org/ColdFire87/serverless-ssm-publish)

Publish custom data to AWS SSM Parameter Store

## Install

`npm install serverless-ssm-publish --save-dev`

## Usage
```yaml
custom:
  # Can specify value on command line `sls deploy --secretToken MY_SECRET_VALUE`
  secretToken: ${opt:secretToken}

  ssmPublish:
    enabled: true
    params:
      - Path: /global/tokens/secretToken
        Value: ${self:custom.secretToken}
        Secure: true
      - Path: /service/config/storageBucket
        Value: !Ref StorageBucket
        Secure: false         # false is default value
```

## Version History
* 1.0.0
  - Initial release
