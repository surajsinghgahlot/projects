### Intro: <br />
Client's had a small medicale platform app where he want to manage his user through basic portal, where a user can do: <br />
1. Signup. <br />
2. Sign. <br />
3. Can reset password. <br />
<br />
And client also want to send welcome email to register email's address with user's username/password, and a link to reset password. <br />

## Solution: <br />
1. Amazon Congnito to manager user's identity. <br />
2. Amazon SES to manage sender's email. <br />
3. Amazon Lambda function to send emails. <br />