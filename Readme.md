### Infra Diagram:
![Screenshot](arch.png)

### Description:
1. Client had a establised product running on 2 EC2 instance with autoscalling features enabled, with 1 as backend & 1 as frontend. Plus with RDS as database.
2. The frontend was created in ReactJs and Backend was created in NodeJs.
3. To get the better reliable product and to save time for development, he wants to move to container system for both Prod and Dev env.
4. They were also looking to automate with only with Jenkins not with any other CD tools.

### Website: 
``````
https://dev.biskane.com
https://biskane.com
``````

### Used Apps:
1. Amazon EKS, where apps deployed.
2. Amazon RDS for database.
3. Amazon CloudFront for caching.
4. Amazon ECR to store the container images.
5. Amazon Certificate Manager for SSL.
6. Jenkins for CD.
7. Bitbucket as a version controling system.

### Apps Into:
1. **AWS EKSe**:<br/>
        a. It s a managed Kubernetes service to run you containers.<br/>
        b. It gives you the advantage of all the performance like scale, reliability, & availability of AWS infrastructure, as well as integrations with AWS networking & security services.

2. **Jenkins**:<br/>
            a. It is an open source automation server based on Java.<br/>
            b. It helps automate the parts of software development related to building, testing, & deploying, facilitating CI/CD.<br/>
            c. It is a server-based system that runs in servlet containers such as Apache Tomcat.<br/>
            d. It comes with variety of plugins to support.

3. **AWS ECR**:<br/>
            a. It is a fully managed container registry where you can save application docker images and its artifacts.

4. **Bitbucket**:<br/>
            a. It is a developer platform that allows developers to create, store, manage and share their codes.<br/>
            b. It also help developer to manage the different versions(history) of code.

5. **Amazon CloudFront**:<br/>
                    a. It is a is a content delivery network (CDN) service built for high performance, security.<br/>
                    b. It works like a loadbalancer which help to route your traffic according to your convenience in all regions.

6. **Amazon Certificate Manager**:<br/>
            a. It provision, manage, & deploy public & private SSL/TLS certificates for use with AWS services.<br/>
            b. It removes the time-consuming manual process of purchasing, uploading, & renewing SSL/TLS certificates.

### Solution:
1. We helped them to containerized their both applications.
2. We created a EC2 instance to run Jenkins and we start installing plugin like: <br/>
    a. Docker, to build the docker iamge and push it to ECR. <br/>
    b. Helm, we used helm package manager to manage
    c. Email auth(oidc), implemented their official email provider for authenticate. <br/>
    d. Bitbucket, to implement their repo where there code lives.
3. Created a Jenkins file compose of 5 steps:<br/>
    a. Pull latest code.
    b. Build Docker image with the help of dockerfile.
    c. Push it to the ECR.
    d. Use helm chart to deploy that image to EKS.
4. Created helm chart for both backend and frontend.
5. Whenever developer push the code in bitbucket the Jenkins build a docker with the help of dockerfile and push it to ECR and then after it deploy the same dockerimage in EKS.
6. We customized the helm files as well as Jenkinsfile and by manupulating their values in runtime, we are able to use the same helm files for dev/prod deployment.


## NOTE: WE PROVIDE THE SAME INFRA SOLUTION FOR BOTH AZURE/AWS/GCP, ONLY COMPONENT GET CHANGES