Codebuild notes
=============

let's learn codebuild integrations

# codebuild-integrations

Command to deploy a codebuild

```bash

aws cloudformation deploy --template-file codebuild-template.yml \
    --stack-name prod-codebuild-hellloworld \
    --parameter-overrides \
    Env=prod \
    BuildSpec=lambda-deploy/sam-upload-buildspec.yml \
    CodeBuildType=lambda-upload \
    Location=https://github.com/poltorres7/codebuild-integrations \
    SecondaryLocation=https://github.com/poltorres7/lambdas \
    --tags Env=Dev Course=DevOps \
    --capabilities CAPABILITY_IAM CAPABILITY_NAMED_IAM


aws cloudformation deploy --template-file codebuild-template.yml \
    --stack-name prod-codebuild-hellloworld \
    --parameter-overrides \
    Env=prod \
    BuildSpec=lambda-deploy/sam-deploy-buildspec.yml \
    CodeBuildType=lambda-deploy \
    Location=https://github.com/poltorres7/codebuild-integrations \
    SecondaryLocation=https://github.com/poltorres7/lambdas \
    --tags Env=Dev Course=DevOps \
    --capabilities CAPABILITY_IAM CAPABILITY_NAMED_IAM

```