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

<img width="460" height="233" alt="image" src="https://github.com/user-attachments/assets/f59196db-648d-44b1-b120-3bc69512eb8f" />

First, you have the continuous integration. Here you have the code, build, and test. In the code section, that basically means developers write code and commit changes frequently to the version control system, such as GitHub, GitLab, Bitbucket, and so on. Then your code is automatically built, ensuring it compiles correctly and all dependencies are in place. Then you have automated tests. These tests are run to verify that your code that has been updated does not introduce any bugs or issues.


On the right side, the CD. Based on feedback, the next steps are planned. The successfully tested code is then released onto a staging or a production environment. Then it's deployed. The application is deployed to a production environment which is live, making it available to users. After that, you're monitoring your code.

By using automated pipelines, CICD ensures that the processes are consistent across different environments. It eliminates the "it works on my machine problem" and ensures that the code runs smoothly from development to production.

### How CI/CD fits into the DevOps Architecture

<img width="690" height="387" alt="image" src="https://github.com/user-attachments/assets/35397d25-9c84-4951-a397-b5489e6da13b" />

First you have your source control. This is where developers store and manage their code, tools like GitHub, GitLab, Bitbucket, and much more that are commonly used for this purpose. Source control allows multiple developers to work on the same project without conflicts, maintaining a history of changes and allowing for collaboration.

Then you have the CI/CD. Once the code is in your source control, we move to the CI/CD stage. Here, CI/CD automates the build, test, and deployment process. This stage, like we said, ensures that your code changes are continuously integrated, tested, and deployed.

Then after that, you have the monitoring and logging. Now, after your code is deployed, you need to monitor something. This is where monitoring and logging come into play. This stage involves continuously monitoring the application to ensure it runs smoothly. Tools like Prometheus, Grafana, and ELK are used to help track the performance of your code to find any issues and log important events. This feedback loop is crucial for maintaining and improving the application over time.

You can go back and forth between these stages. For example, you might find an error in your logs and you want to go back and fix your CI/CD or your code and then downwards.

To summarize, you have your source control where you manage and store code. Then you have CI/CD where you automate integration, testing, and deployment of code. And then you have the monitoring and logging. This ensures the applications run smoothly.

## GitHub Actions

### Github Actions & CI/CD Workflow

<img width="481" height="281" alt="image" src="https://github.com/user-attachments/assets/b7b79661-335b-4536-a2bf-c99959b1db2b" />

First, you have your code. Everything starts with writing the code. You have your code, developers write new features or fix bugs and make changes to the code base. Then, you commit it.

Once changes are ready, the developers commit the code to a repository. This is where GitHub Actions kicks in.

You have your GitHub Actions workflow. The committed code triggers a GitHub Actions workflow. This workflow now is defined in a YAML file. It specifies what actions to take when certain events, like commit, occur. Then, you have the pipeline itself. The workflow enters the CI pipeline. Now, here's what happens step by step.

You have the build. The first step is to build your code. Now, this involves compiling the code and resolving dependencies to ensure everything is set up correctly. Next, you have some automated tests. Now, these tests essentially verify that the new code doesn't break anything, and any existing functionality is not also broken. And also, new features are working as expected. This step is crucial for maintaining code quality. The test outcome is checked. If the test passes, the workflow moves on to the next step. If they fail, the process stops and developers are notified to fix any issues.

Then, if the build and tests are both successful, the code is packaged. Now, this usually means that it creates a new deployment version of the product or your application, whether it's a Docker image or a compiled binary. Then, your code is packaged and then deployed. This can be to a staging, a testing environment, or even production, depending on the workflow steps. Once your code is pushed to production, you want to monitor it. Continuous monitoring ensures your application is running smoothly and any issues are quickly addressed.

### Use cases for Github Actions
Continuous integration -  GitHub Actions can automatically build and test your code every time you push changes to your repository. Now, this ensures that your code is always in a good state and any issues are caught early.

For example, you have a code running unit tests on every pull request. That ensures that any new code doesn't break existing functionality and maintains the quality of your code base.

Continuous deployment - After your code passes all tests, GitHub Actions can automatically deploy to production or any other environment. Now, this speeds up the release process and reduces manual intervention. An example of this would be deploying a web application to a cloud service like AWS, Azure, or GCP. Now, this can be set to happen automatically after all tests pass, ensuring quick and reliable releases.

Automation - GitHub Actions can automate repetitive tasks in your workflow, freeing up time for more important work. Now, a real example would be managing project board automation. For instance, moving cards or tasks between columns on a GitHub project board based on issues or pull requests. Now, this helps keep your project board up to date without manual effort.

## Writing YAML
YAML stands for YAML Ain't Markup Language.

YAML is the language of DevOps. Without YAML, a lot of things like Kubernetes, CICD and much more we cannot do without DevOps.

Yaml is essentially a human-readable data serialization standard that is often used for configuration of files. That is basically what it is.

3 concepts of YAML

<img width="237" height="93" alt="image" src="https://github.com/user-attachments/assets/6bf22f13-44ae-4356-a0c3-bddf7e0db6a4" />

First is Key-Value Pairs. This is the fundamental of YAML. Now this is the basic building block, the Key-Value Pair. You have the key and you have the value. Simple as, you can create, for example, name and then you put your name there, your surname and then you have your age, put your age there. That's what Key-Value is. That's what is supporting YAML.


<img width="213" height="135" alt="image" src="https://github.com/user-attachments/assets/d88850bd-5d8f-418c-8efa-d228e36d22fb" />

Second is Lists essentially what they are, are sequences of items. So lists are defined using a dash followed by a space and then a certain list item.

<img width="218" height="109" alt="image" src="https://github.com/user-attachments/assets/d6bc3c88-8d26-4fa0-9584-5ea9c598d4cb" />

Third is Nested data structures, one of the most powerful features of YAML is its ability to represent nested data structures. You can nest elements by using indentation, as you can see, two spaces. You can have the parent, then you have the child which is nested, and then the key value. That's simply what YAML is.

## Pipelines
 ### Workflow syntax and structure
First, before anything, you must have a workflow file. Now, this workflow file is defined in a YAML file and is usually located in the .github slash workflows. Any workflow that you have, cia.yaml, main.yaml, is triggered by GitHub as a pipeline.

<img width="656" height="359" alt="image" src="https://github.com/user-attachments/assets/049c35f3-b611-461c-b3db-21502ab26d8f" />

First, you have the name field. Now the name is quite arbitrary. It's simply the name of your workflow. It's the label that helps you identify what this workflow does. Just the name. That's it.

Then you have the trigger. So in this case, it will say on trigger on what occasion, whether it's a push, a pull request, or a schedule like a cron job. This defines the events that will trigger the workflow. In this case, we have on push. This means that our workflow will run every time there is a push to a repository. That means they get push. You can have a pull request. That means if you have a pull request that is merged, it will trigger it or not, or a schedule, whether it's a cron job or not.

Then you have the jobs. Now the jobs are basically a series of tasks that run as part of the workflow. Each job runs in its own virtual environment and can be configured to run on different operating systems. In our example, we have a single job named build.

You have the runs on. Within each job, you specify the environment using runs on. Now this tells GitHub actions what operating system to use for the job. Here we're using the latest version of Ubuntu, a Unix machine. We can also have a Windows OS or even Mac OS. We can also have a workflow or pipeline to run in a container if you wanted to. By default, GitHub actions users commonly use OSs like Ubuntu.
 
Then you have the steps. Jobs are composed of steps. Now steps are individual tasks that run in a sequence. Each step can either run a command or use an action. Now actions are reusable pieces of code that can perform a variety of tasks. Now here you have the first thing. You have checkout code. Our first step uses an action to check out the code from the repository.

GitHub workflows has a marketplace of reusable and community created actions. Some are by GitHub themselves and some are by other organizations like AWS and more. Now this specific action pulls the latest code from your repo so that subsequent steps can work with it. And you have more examples like setup node, npm install, npm tests. These are just some examples that you can have in your steps.

### Advanced Github Actions
Using Conditions and Expressions

<img width="565" height="243" alt="image" src="https://github.com/user-attachments/assets/ab516844-8760-45fd-b897-f7f3f7ac2f06" />

Conditions - Allow you to control when a job or step should run based on certain criteria.

Expressions - Provide a way to perform calculations, manipulate strings and more within your workflow file.

Matrix builds and Parallel testing

<img width="418" height="407" alt="image" src="https://github.com/user-attachments/assets/c2dfe1bb-62cc-49bd-8374-06c8ec3cc4a3" />

Matrix builds - Allows you to run multiple job configurations in parallel.

Useful for testing across different environments e.g. python versions and operating systems.

### Securing Workflows
Secrets & Encrypted vars

What are Secrets?

Secrets are sensitive pieces of information such as API keys, passwords or any credentials that you don't want to expose in your codebase.

How to manage Secrets in Github Actions

<img width="324" height="296" alt="image" src="https://github.com/user-attachments/assets/e884af31-1aec-481e-9473-0692c1123b96" />


<img width="439" height="302" alt="image" src="https://github.com/user-attachments/assets/e935b3ab-640e-4753-a8c5-4a71b72111fc" />

### Reusable CI/CD
Customs Actions

What are Customs Actions?

They're reusable units of code that automate specific tasks in your CI/CD pipeline. Now there are three types of actions. You have JavaScript actions; these are actions that use Node.js to run JavaScript code. Then you have Docker actions; yes, they're in containers. And then you have composite actions, which are pieces that are reusable.

How to create a Custom Action

<img width="244" height="178" alt="image" src="https://github.com/user-attachments/assets/5803444c-e46c-4619-8d69-aa7b15326c7a" />

Sharing and reusing Custom Actions in different projects

<img width="254" height="253" alt="image" src="https://github.com/user-attachments/assets/4879faa5-9ab1-448e-a9be-8360eb12e4ae" />

Benefits of Reusable Actions

Consistency - Using reusable actions helps maintain consistency across different repositories like we said. By standardizing your CI/CD process, you ensure that all your projects follow the same steps and quality checks. This reduces the likelihood of errors and makes sure your workflows are more predictable.

Efficiency - Reusable actions save a lot of time and effort. Instead of writing the same code for each project or the same pipeline, you can create an action once and reuse it whenever needed. 










