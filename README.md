# aws-codepipeline-example

This is a (being developed) example of an AWS Codepipeline stack
used to build and deploy SAM Serverless apps.  

The example serverless app is at: https://github.com/samkeen/aws-SAM-helloworld

The `codepipeline-infra.yaml` template represents the one-time build of supporting pipeline infrastructure 
for the serverless apps.

This includes;
- Shared S3 bucket for Piplelines to move code artifacts between their stages
- Shared S3 bucket for packaged Lambda code (target of `sam package ...`)
- Shared IAM Service Role for the CodePipelines
- Shared IAM Service Role for the CodeBuild Projects

The actual CodePipeline is build it a Cloudformation template held within the Serverless app repo 
(see: https://github.com/samkeen/aws-SAM-helloworld/blob/master/pipeline.yaml)