# Incident Report

## Summary
Between the hours of 7:00pm and 8:00pm on 9/20/23 users encountered an 503 error while trying to use our URL Shortner Web Application. The event was triggered by an application update. The update contained change in the code to update the application and a bug in the code cause the 503 error

## Leadup 
At 6:00pm on 9/20/23, an hour before the incident occured, a change was introduced to code of our web application and deployed to the production server. This change resulted in users not being able to access our web application

## Impact

For 1 hour between 7:00pm and 8:00pm on 9/20/23 our users experienced this incident. The incident affected all customers who tried to use our web application and internal employees who tried to access the application

## Detection

This incident was detected when the update was deployed to the production server and an employee navigated to the web application then they encounter the error.

Code checks and an approval system will be setup before code is commited and deployed to the production environment. We will also adopt a least privilege access control where users will only have access to specific data, resources and applications needed to complete their task.

## Response

After being told by the employee about the error, measures were taken to debug the code and restore the web application to a working version.

## Recovery

Steps were taken to restore service by debugging and looking at server logs and saw that there was a type error in the application code. This took about an hour to fix and users were able to access the web application again. As we have an SLA to uphold a rollback would of been more effective and would of shortned the downtime of the web application instead of heading straight into debugging, which took longer.

**Working Application after Debugging**
![working app v2](screenshots/Screenshot%202023-09-22%20at%203.16.39%20PM.png)

**Working Application after Rollback to V1**
![working app v1](screenshots/Screenshot%202023-09-22%20at%203.16.25%20PM.png)

**ElasticBeanstalk Logs**
![Logs](screenshots/Screenshot%202023-09-22%20at%202.31.10%20PM.png)
