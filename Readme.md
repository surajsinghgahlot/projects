### Infra Diagram:
![Screenshot](arch.png)

### Description:
1. It's a simple project where we helped the client to host their python app on AWS.
2. The current dev infra was on EC2 and their performing everything manually, like deploying new code installing new plugings etc.
3. They are now ready to move to prod for which they want a reliable solutions, along with they want automate the whole process with CI/CD so that apps will deploy on server with a git push.

### Used Apps:
1. Amazon EC2 ElasticBeanstalk to deploy apps.
2. Amazon CodePipeline for CD.
3. Amazon ECR to save dockerimage.
4. Github to manage codebase.

### Apps Into:
1. **AWS EC2 ElasticBeanstalk**: <br/>
                    a. It is a service for deploying & scaling web applications. <br/>
                    b. It automatically handles the deployment—from capacity provisioning, load balancing, and auto scaling to application health monitoring.

2. **Amazon CodePipeline**: <br/>
                     a. It isa  fully managed CD service that helps to automate the release pipelines for fast & reliable application & infrastructure updates with new codebase. <br/>
                     b. It can intregrate with any version control system like github, codecommit etc. <br/>
                     c. It composite of two steps i.e codebuild and codedeploy and together it is called codepipeline.

3. **AWS ECR**: <br/>
            a. It is a fully managed container registry where you can save deploy application images and artifacts.

4. **Github**: <br/>
            a. It is a developer platform that allows developers to create, store, manage and share their codes. <br/>
            b. It also help developer to manage the different versions(history) of code.

### Solution:
1. We helped them to containerize their application and the image is saved in ECR.
2. We used the same container to run the apps on the beanstalk.
3. The reason to choose beanstalk instead of fargate as it is more cheeper then fargate & client's developer was more friendly to it.
4. We created 2 branch in the repo one for dev and one for prod and connected with codepipeline through a oath read token.
5. The token gives access to codepipeline to pull the code, and along with dockerfile we also create a buildspec.yml & appspec.yml file.
6. Buildspec.yml & appspec.yml is a template file which gives instruction to codebuild & codedeply about the steps to perform on them.
7. Whenever developer push the code in github the codebuild build a docker image with the help of dockerfile and push it to ECR and then after  codedeploy deploy the same dockerimage in beanstalk.
