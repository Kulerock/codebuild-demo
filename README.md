# codebuild-demo
## Using AWS Code Build + Code Pipeline
## Deployment
Requirements:
* [AWS SAM CLI](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-install.html)

```bash
# set AWS profile (for CICD account)
export AWS_PROFILE=change_me

# deploy
sam deploy \
  --template pipeline.cfn.yaml \
  --stack-name cicd-nginx \
  --no-fail-on-empty-changeset \
  --confirm-changeset \
  --capabilities CAPABILITY_IAM \
  --parameter-overrides \
      Env=dev
```
