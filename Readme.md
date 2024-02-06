## Infra Diagram:
![Screenshot](arch.png)

### Description:
1. Client had a establised product running on Azure apps service as backend & VM as frontend, where the users info are stored in database.
2. The frontend was created in ReactJS and Backend was created DotNet.
3. They want to have a solution which can run both AWS and Azure with Multi-tenant architecture.
4. Deploying a whole achitecture was time taking, that's why they want us to find a solution where they can deply everthing within mins.

## Website:
     https://m9999.dev.mandatlyonline.net

### Used Apps:
1. Amazon EKS, where backend api i.e DotNet is deployed.
2. Amazon S3 where reactjs was deployed to host a static website.
3. Amazon RDS to store info of users.
4. Amazon ECR to store the container images.
5. Amazon CloudFront for path based routing.
6. Amazon Certificate Manager for SSL.

### Apps Into:
1. **Amazon EKS**: <br/>
                    a. It s a managed Kubernetes service to run you containers.  <br/>
                    b. It gives you the advantage of all the performance like scale, reliability, and availability of AWS infrastructure, as 
                        well as integrations with AWS networking & security services.

2. **Amazon S3**: <br/>
                a. It is an object storage service, which main purpose is to store the static objects like photo etc. <br/>
                b. It also give the advantage to host the static website.

3. **AWS ECR**: <br/>
            a. It is a fully managed container registry where you can save deploy application images and artifacts. <br/>

4. **Amazon CloudFront**: <br/>
                    a. It is a is a content delivery network (CDN) service built for high performance, security. <br/>
                    b. It works like a loadbalancer which help to route your traffic according to your convenience in all regions. <br/>
                    c. It also works with path based routing for example: <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;website.com\api ====> backend <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;website.com\index.html ====> frontend

5. **Amazon Certificate Manager**: <br/>
                    a. It provision, manage, & deploy public & private SSL/TLS certificates for use with AWS services. <br/>
                    b. It removes the time-consuming manual process of purchasing, uploading, & renewing SSL/TLS certificates.

### Solution:
1. We find out that their fronted was static so we decided to host that on S3 backed by cloudfront to call index.html
2. We helped them to containerized their Dotnet applications to run on Kubernetes.
3. Nginx was used as webserver infront of Dotnet with all the path routs configure plus by using ELB the inbound/outboud traffic was established for the container.
4. The toughest challenge was to create cloudfront in such a way that it can route the traffic by path based & with custom headers.
5. At last we created lots of terraform scripts to deploy all the application with 4-5 steps.


## NOTE: WE PROVIDE THE SAME INFRA SOLUTION FOR BOTH AZURE/AWS/GCP, ONLY COMPONENT GET CHANGES