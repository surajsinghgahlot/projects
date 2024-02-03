### Description:
1. Client was using a IOT platform know as openremote(https://github.com/openremote/openremote). <br/>
2. They want to host the openremote after adding their some custom plugin on a server on 2 different AWS account. <br/>
3. One account will host dev env with URL(platform-dev.herd-itt.com) & another will host the production with URL(platform.herd-itt.com). <br/>
4. They also want to automate the whole process with CD so that apps will deploy on server with a git push on dev & git merge on prod. <br/>

### Used Apps:
1. Amazon EC2 fargate to deploy our server. <br/>
2. Amazon CodePipeline for CI/CD. <br/>
3. Github to manage codebase. <br/>

### Apps Into:
1. **AWS EC2 fargate**: <br/>
                    a. It helps you to run your containers without having to manage servers or clusters of Amazon EC2 instances. <br/>
                    b. You no longer have to provision, configure, or scale clusters of virtual machines <br/>

2. **Amazon CodePipeline**: <br/>
                     a. It isa  fully managed CD service that helps to automate the release pipelines for fast & reliable application & infrastructure updates with new codebase. <br/>
                     b. It can intregrate with any version control system like github, codecommit etc. <br/>

3. **Github**: <br/>
                    a. It is a developer platform that allows developers to create, store, manage and share their codes. <br/>
                    b. It also help developer to manage the different versions(history) of code. <br/>

### Solution:
1. Openremote is a open sources and they guys already build their application to run on container. <br/>
2. We used the same container to run the apps on the fargate(EC2). <br/>
3. But we also modify the Dockerfile so that their will also compile with container. <br/>
4. We created 2 branch in the repo one for dev and one for prod. <br/>
5. 

3. Whenever a new user comes to website it for signup, it clicks on sinup button.
4. By clicking on  SINGUP URL, our reacts code hits cognito URL which helps users to create their identity.
5. Once user create it's identity, cognito automatically trigger the lambda to send welcome email by using SES email.
6. The lambda have the email templates loaded with client's website details.
7. Same method we implemented for rest of the 2 use cases.
