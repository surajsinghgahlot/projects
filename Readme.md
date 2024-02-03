### Infra Diagram:
![Screenshot](arch.png)

### Description:
1. Client was using a IOT platform know as openremote(https://github.com/openremote/openremote). <br/>
2. They want to host the openremote after adding their some custom plugin on a server on 2 different AWS account. <br/>
3. One account will host dev env & another will host the production env. <br/>
4. They also want to automate the whole process with CD so that apps will deploy on server with a git push on dev & git merge on prod. <br/>

### Website: 
```
    platform.herd-itt.com
    platform-dev.herd-itt.com
```

### Used Apps:
1. Amazon EC2 fargate to deploy our server. <br/>
2. Amazon CodePipeline for CI/CD. <br/>
3. Amazon ECR to save dockerimage. <br/>
4. Github to manage codebase. <br/>

### Apps Into:
1. **AWS EC2 fargate**:
                    a. It helps you to run your containers without having to manage servers or clusters of Amazon EC2 instances. <br/>
                    b. You no longer have to provision, configure, or scale clusters of virtual machines <br/>

2. **Amazon CodePipeline**:
                     a. It isa  fully managed CD service that helps to automate the release pipelines for fast & reliable application & infrastructure updates with new codebase. <br/>
                     b. It can intregrate with any version control system like github, codecommit etc. <br/>
                     c. It composite of two steps i.e codebuild and codedeploy and together it is called codepipeline. <br/>

3. **AWS ECR**:
            a. It is a fully managed container registry where you can save application docker images and its artifacts. <br/>

4. **Github**:
            a. It is a developer platform that allows developers to create, store, manage and share their codes. <br/>
            b. It also help developer to manage the different versions(history) of code. <br/>

### Solution:
1. Openremote is a open sources and they guys already build their application to run on container. <br/>
2. We used the same container to run the apps on the fargate(EC2). <br/>
3. But we also modify the Dockerfile so that their will also compile with container. <br/>
4. We created 2 branch in the repo one for dev and one for prod and connected with codepipeline through a oath read token. <br/>
5. The token gives access to codepipeline to pull the code, and along with dockerfile we also create a buildspec.yml & appspec.yml file. <br/>
6. Buildspec.yml & appspec.yml is a template file which gives instruction to codebuild & codedeply about the steps to perform on them. <br/>
7. Whenever developer push the code in github the codebuild build a docker with the help of dockerfile and push it to ECR and then after codedeploy deploy the same dockerimage in fargate. <br/>
