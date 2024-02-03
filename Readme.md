### Description:
Client's want to have small medicale platform app where he want to manage his user through basic SSO platform, where a user can do: <br />
1. Signup. <br />
2. Sign. <br />
3. Can reset password. <br />

And client also want to send welcome email to register email's address with user's username/password, and a link to reset password. <br />

### Used Apps:
1. Amazon Amplify for UI react app. <br />
2. Amazon Cognito to manager user's identity. <br />
3. Amazon SES to manage sender's email. <br />
4. Amazon Lambda function to send emails. <br />

### Apps Into:
1. **AWS Amplify**: <br />
                    a. This is everything you need to build full-stack web UI and mobile apps. <br />
                    b. We hosted our react UI on here and guess what it comes with inbuild URL, just like AWS cloudfront & S3 have. <br />
                    c. We can use the same URL as a domain or it can help you to map with cloudfront/domain . <br />

2. **Amazon Cognito**: <br />
                     a. The service helps you implement customer identity and access management into your web and mobile applications. <br />
                     b. You can quickly add user authentication and access control to your applications in minutes. <br />
                     c. It is fully AWS managed apps so it comes with scalelibilty.

3. **Amazon SES**: <br />
                    a. It is a cloud-based email service provider that can integrate into any application for high volume email automation.

4. **Amazon Lambda function**: <br />
                    a. It is a compute service & serverless applications that runs your code in response to events and it automatically manages the compute resources.
