# AWS CI/CD Project

## Introduction

This project demonstrates a robust CI/CD pipeline for a Java Full Stack application deployed on AWS. The pipeline automates the build, test, and deployment processes using a variety of AWS services, ensuring seamless integration and delivery of code changes.

## Technologies Used

- **VProfile Java Application**: A full-stack Java application codebase.
- **Elastic Beanstalk**: AWS Elastic Beanstalk is used to deploy and manage the application, including instances and a load balancer.
- **Bitbucket**: Source code repository where the Java application code is hosted.
- **Amazon RDS**: Amazon MySQL RDS is used as the database service for the Java application.
- **AWS CodeBuild**: A fully managed build service that compiles the source code, runs tests, and produces software packages.
- **AWS CodeCommit**: A source control service that manages and stores the code in a Git repository.
- **AWS CodePipeline**: A CI/CD service that automates the build, test, and deployment phases of the application.

## How It Works

1. **Source Code Management**:
   - The source code is managed and versioned using Bitbucket.
   - Any new commits to the Bitbucket repository are monitored by AWS CodePipeline.

2. **CI/CD Pipeline**:
   - **AWS CodePipeline**:
     - Detects new commits in the Bitbucket repository.
     - Triggers the CI/CD pipeline to start the build and deployment process.
   - **AWS CodeBuild**:
     - Fetches the latest commit from Bitbucket.
     - Builds the latest code version and runs tests.
   - **Elastic Beanstalk Deployment**:
     - The built code is deployed to Elastic Beanstalk.
     - Utilizes a rolling update strategy, updating 50% of instances at a time to ensure minimal downtime.

3. **Auto-Scaling**:
   - Elastic Beanstalk is configured with auto-scaling policies.
   - Minimum of 2 instances and a maximum of 4 instances based on network load and demand.

## Pipeline Configuration

- **CodePipeline**:
  - Fetches the latest commit from Bitbucket repository.
  - Triggers AWS CodeBuild for building the code.
- **CodeBuild**:
  - Builds the code and produces deployment artifacts.
- **Elastic Beanstalk**:
  - Deploys the built code with a rolling update strategy.
- **Auto-Scaling**:
  - Ensures high availability and scalability with defined minimum and maximum instance counts.

## Setup Instructions

1. **Setup AWS Services**:
   - Configure Elastic Beanstalk environment with instances and load balancer.
   - Set up Amazon RDS for MySQL database.
   - Create a CodeBuild project.
   - Configure CodePipeline with Bitbucket as the source and CodeBuild for build.

2. **Commit Source Code**:
   - Push your Java application code to Bitbucket.

3. **Pipeline Execution**:
   - CodePipeline will automatically detect changes and trigger the build and deployment process.
   
## Demonstration

https://drive.google.com/file/d/1Vz6QFo1gyDB0lpG6yR9DWItVil8cQrw_/view

## Conclusion

This CI/CD setup provides a streamlined approach to managing and deploying Java applications on AWS. By leveraging AWS CodePipeline, CodeBuild, and Elastic Beanstalk, the project ensures efficient handling of code changes and deployment processes while maintaining high availability through auto-scaling policies.
