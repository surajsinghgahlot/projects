### Infra Diagram:
![Screenshot](arch.png)

### Description:
1. Client were have having 3 container one of each
    a. Node-api
    b. python-api
    c. Node Reacts.
2. They were ready with container and they are looking for someone who will help to deploy on farget(ecs).
3. They were also looking to automate with only with Jenkins not with any other CD tools.
4. Along with above all they were also looking to covert all above things to terraform script, so that they can deploy the same to their client.

### Website: 
``````
https://api.zerovoltelectric.com/
http://webapi.zerovoltelectric.com/
https://python.zerovoltelectric.com:9000/
``````

### Used Apps:
1. Amazon ECS fargate to deploy our server.
2. Jenkins for CI/CD.
3. Amazon ECR to save dockerimage.
4. Bitbucket to manage codebase.

### Apps Into:
1. **AWS EC2 fargate**:<br/>
                    a. It helps you to run your containers without having to manage servers or clusters of Amazon EC2 instances. <br/>
                    b. You no longer have to provision, configure, or scale clusters of virtual machines.

2. **Jenkins**:<br/>
                     a. It is an open source automation server based on Java. <br/>
                     b. It helps automate the parts of software development related to building, testing, & deploying, facilitating CI/CD <br/>
                     c. It is a server-based system that runs in servlet containers such as Apache Tomcat. <br/>
                     d. It comes with variety of plugins to support.

3. **AWS ECR**:<br/>
            a. It is a fully managed container registry where you can save application docker images and its artifacts.

4. **Bitbucket**:<br/>
            a. It is a developer platform that allows developers to create, store, manage and share their codes. <br/>
            b. It also help developer to manage the different versions(history) of code.

### Solution:
1. They were already ready with their code base running dockerimage, so we started implimenting it.
2. We created a EC2 instance to run Jenkins and we start installing plugin like: <br/>
    a. Docker, to build the docker iamge and push it to ECR. <br/>
    b. Fargate, to deploy the new docker image into the fargate. <br/>
    c. Email auth(oidc), implemented their official email provider for authenticate. <br/>
    d. Bitbucket, to implement their repo where there code lives.
2. Created a Jenkins file compose of 5 steps:<br/>
    a. Pull latest code.
    b. Build Docker image with the help of dockerfile.
    c. Push it to the ECR.
    d. Deploy that image to Fargate.
3. Same process we have implement in all three repo.
4. Whenever developer push the code in bitbucket the Jenkins build a docker with the help of dockerfile and push it to ECR and then after it deploy the same dockerimage in fargate.
