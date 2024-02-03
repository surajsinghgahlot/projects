## Infra Diagram:
![Screenshot](arch.png)

### Description:
1. Client had a well establised product running on Azure apps service as backend and VM as frontend. <br/>
2. The frontend was created in ReactJS and Backend was created DotNet. <br/>
3. They want to have a solution which can run both AWS and Azure with Multi-tenant architecture. <br/>
4. Deploying a whole achitecture was time taking, that's why they want us to find a solution where they can deply everthing within mins. <br/>

## Website:
     https://m9999.dev.mandatlyonline.net

### Used Apps:
1. Amazon EKS, where backend api i.e DotNet is deployed. <br/>
2. Amazon S3 where reactjs was deployed to host a static website. <br/>
3. Amazon ECR to store the container images. <br/>
4. Amazon CloudFront for path based routing. <br/>
5. Amazon Certificate Manager for SSL. <br/>

### Apps Into:
1. **Amazon EKS**: <br/>
                    a. It s a managed Kubernetes service to run you containers.  <br/>
                    b. It gives you the advantage of all the performance like scale, reliability, and availability of AWS infrastructure, as well as integrations with AWS networking & security services <br/>

2. **Amazon S3**: <br/>
                     a. It is an object storage service, which main purpose is to store the static objects like photo etc. <br/>
                     b. It also give the advantage to host the static website. <br/>

3. **AWS ECR**: <br/>
            a. It is a fully managed container registry where you can save deploy application images and artifacts. <br/>

4. **Amazon CloudFront**: <br/>
                    a. It is a is a content delivery network (CDN) service built for high performance, security. <br/>
                    b. It works like a loadbalancer which help to route your traffic according to your convenience in all regions. <br/>
                    c. It also works with path based routing for example: <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;website.com\api ====> backend <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;website.com\index.html ====> frontend <br/>

5. **Amazon Certificate Manager**: <br/>
                    a. It provision, manage, & deploy public & private SSL/TLS certificates for use with AWS services. <br/>
                    b. It removes the time-consuming manual process of purchasing, uploading, & renewing SSL/TLS certificates. <br/>

### Solution:
1. We find out that their fronted was static so we decided to host that on S3 backed by cloudfront to call index.html. <br/>
2. We helped them to containerized their Dotnet applications to run on Kubernetes. <br/>
3. Nginx was used as webserver infront of Dotnet with all the path routs configure plus by using ELB the inbound/outboud traffic was established for the container. <br/>
4. The toughest challenge was to deploy cloudfront in such a way that it can divert the traffic by path based and with custom headers. <br/>
5. 
