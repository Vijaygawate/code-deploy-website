# code-deploy-udemy
Deployment of static website on s3 bucket through aws codepipeline 

**Step1**
Create 2 buckets (manually)
Bucket1 : unique name (to store artifacts after build)
Bucket2: unique name (destination bucket)
enable versioning 
In destination bucket >> properties >> enable static hostic website (index.html)

**Step2**
Services >> Codepipeline >> build >> getting started >> create project 
Name -- codebuild 
source--github 
repo--select from options 
connect to github 
env >> amazon linux
runtime - stad
image version --latest
new service role 
diable cloudwatch logs 
Crete 

**Step3**
Services >> Codepipeline >> create pipeline 
Name: mypipeline 
new service role 
custom location -- artifact vala bucket 
source stage--github 
build stage--codebuild 
project name --codebuild 
single 
deploy provider--amazon s3
bucket -- destination bucket
enable extract file before deploy
public read write 
create pipeline 

Note: If pipeline fails 
edit service role in pipeline and give full access 

**Step4**
test the s3 static url
