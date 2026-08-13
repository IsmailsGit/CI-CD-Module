# CI/CD Assignment 1

## Build a basic CI pipeline that runs tests or checks automatically on each push.

For this test I used my previous Terraform assignment code and made the pipeline based off of this.

My Task1.yaml file containing the pipeline

<img width="1189" height="692" alt="image" src="https://github.com/user-attachments/assets/06b17325-8e41-499b-92c9-8008a7758849" />

My Git Actions Workflow

<img width="947" height="488" alt="image" src="https://github.com/user-attachments/assets/9b01c064-233b-4a76-90b8-eb0a36ea8788" />

<img width="1061" height="566" alt="image" src="https://github.com/user-attachments/assets/37449f86-887b-40b0-8b3a-02ca79823830" />


As you can see my lint and validate are working as expected, tflint checks to see if my terraform code is in line with terraform code best practices, so that also means that just because tflint picks up an error that doesn't necessarily mean it doesn't work.

This assignment helped me understand how a basic CI pipeline works and what is the need for certain commands.
