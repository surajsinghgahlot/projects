### Infra Diagram:
![Screenshot](arch.png)

### Description:
1. It's a simple project where users want to run their apps on EC2 instance with the help of docker-compose.
2. It's not a reliable solution but client want this to for the testing purpose.

### Website: 
``````
https://api.teleradiologyhub.com
https://viewer.teleradiologyhub.com
``````

### Used Apps:
1. Amazon EC2, where apps deployed.
2. Docker-Compose.

### Apps Into:
1. **AWS EC2**:<br/>
        a. IT allows users to rent virtual computers on which to run their own computer applications.

2. **Docker-Compose**:<br/>
            a. It allows you to define and manage multi-container applications in a single YAML file.
            b. It is also knows as mini kubernetes, usualy used to test the application on local, before deploying into the Kubernetes.

### Solution:
1. We helped them to containerized their both api and web applications.
2. Created a docker-compose file where, backend and frontend both resided in a network as well as backend application need a volume to save data, so everything is mention there in docker-compose.
3. We created a EC2 instance and install docker into it.
4. Trained them how to use the docker-compose and helped them to how to clean the unused images so that EC2 volume remain unused.