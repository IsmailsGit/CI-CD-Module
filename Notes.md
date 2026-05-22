# Notes for the CI/CD Module

### What is CI/CD?
CI/CD stands for Continuous Integration and Continuous Deployment/Delivery 

Continuous Integration is all about automatically integrating code changes frequently. 

For example - Imagine you and your team are working on different features of a project. Now instead of waiting for everyone to finish their part and then merging everything, which can get messy, CI allows you to integrate changes several times a day, more than 100 times a day. This way, we can catch and fix errors quickly, making the whole development process smoother.

Continuous Deployment - Every change that passes all stages of the production pipeline is automatically released to the users. It means no more manual deployments. This process is fully automated.

Continuous Delivery - Once our code is integrated, we want to ensure it's always in a deployable state. That's where continuous delivery comes in. This part makes sure that our software can be released reliably at any time. Think of it as having a release-ready version of your product after every change that passes all stages of the testing pipeline.

### Overview and Why we need CI/CD

<img width="711" height="184" alt="image" src="https://github.com/user-attachments/assets/72968cd0-7c51-4de8-8244-fbc6af3b4f3f" />


 1. You have a change in commit. You push your code, you commit it. This is where developer makes changes.
 
 2. Then you have the Build trigger. So what happens is the commit you just pushed is triggered and it sends an automated build process. 
 
 3. Then you have the actual Build. Now this code is compiled and all dependencies are assembled and built.
 
 4.  Notify of Build Outcome - Then once the build is done, the system notifies the team whether it succeeded or failed.

 5. Then after that, you have Automated Tests that are run to ensure the changes don't break existing functionality.
 
 6.  Notify of Test Outcome - Similar to the build step, you have the outcome of the tests and then it's communicated to the team. 
 
 7. Then you Deliver the Build to Staging. Now, if the test passes, the build is delivered to a staging environment for further testing. 
 
 8. Then once that's done, you can Deploy to Production. Finally, the code is deployed to a production environment where users can access it.


Why is CI/CD so Important?

These are just some of the benefits, but there are much more. 

Firstly, you have fast delivery. Automating the integration and deployment processes means we can deliver new features and fixes much faster, improve quality.

By continuously testing and integrating code, we catch and fix bugs early, improving the overall quality of the software.
 
Then you have reduced risks by doing smaller incremental changes to your code that are easier to test and deploy, reducing risks of big failures. 
  
And lastly, better collaboration. CI/CD encourages collaboration among team members. Everyone's work is integrated frequently, so there are fewer conflicts and better communication.


#### Other popular CI/CD Tools

GitLab CICD. GitLab CICD is integrated right into GitLab

Jenkins is one of the most popular CICD tools out there, and it's open source. It's like the Swiss army knife of CICD. Yes, super powerful and can almost do anything with the right plugins. However, it's also known for being quite complex.

CircleCI is a cloud-based CICD tool that's known for its speed and simplicity. It integrates well with GitHub and Bitbucket

TravisCI, just like CircleCI, is also another cloud-based CICD service, and it integrates well with GitHub.

GitHub Actions is integrated directly into GitHub.

AWS, Azure, and GCP who also have their native CICD services. Each of these tools has its own strengths and might be better suited for different projects or team setups.

### 7. Role of CI/CD in DevOps

CICD is a vital part of the DevOps process. DevOps cannot live without CICD. 

