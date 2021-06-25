# [Learn DevOps: CI/CD with Jenkins using Pipelines and Docker](https://www.udemy.com/course/learn-devops-ci-cd-with-jenkins-using-pipelines-and-docker/)

## 1.  ** **Introduction to Jenkins****

> Jenkins is a free and open source automation server. It helps automate the parts of software development related to building, testing, and deploying, facilitating continuous integration and continuous delivery.

![BUILD PIPELINE WITH JENKINS. As we all know Jenkins is a well-known… | by  Prashant Bhatasana | AppGambit | Medium](https://miro.medium.com/max/951/1*H9jHoRaRnJ0KnqmPs6xeUA.jpeg)

### 1. Different Types of Jenkins Jobs

Jenkins provides the option of choosing from different types of jobs to build your project.

Below are the types of jobs you can choose from:

- **Freestyle**

Freestyle build jobs are general-purpose build jobs, which provides maximum flexibility. It can be used for any type of project.

- **Pipeline**

This project runs the entire software development workflow as code. Instead of creating several jobs for each stage of software development, you can now run the entire workflow as one code.

- **Multiconfiguration**

The multiconfiguration project allows you to run the same build job on different environments. It is used for testing an application in different environments.

- **Folder**

This project allows users to create folders to organize and categorize similar jobs in one folder or subfolder.

- **GitHub Organization**

This project scans your entire GitHub organization and creates Pipeline jobs for each repository containing a Jenkinsfile

- **Multibranch Pipeline**

This project type lets you implement different Jenkinsfiles for different branches of the same project.

### 2. Jenkins Pipelines vs Jenkins Job DSL

- Jenkins Job DSL creates new jobs based on the code you write
- Jenkins Pipeline is a job type, you can create a jenkins pipeline job that will handle the build/test/ deployment of one project

## 2. **Jenkins Integrations**

### 1. Email integration

### 2. Slack integration

### 3. GitHub and BitBucket integration

### 4. JFrog Artifactory integration

### 5. Custom API Integration

## 3. **Advanced Jenkins usage**

### 1.  Introduction to Jenkins Slaves

- SSH

- JNLP (Java Web Start )

### 2. Blue Ocean

A new frontend for Jenkins.

### 3. ssh-agent

### 4. Jenkins credentials

- **Secret text** - a token such as an API token (e.g. a GitHub personal access token),
- **Username and password** - which could be handled as separate components or as a colon separated string in the format `username:password` (read more about this in [Handling credentials](https://www.jenkins.io/doc/book/pipeline/jenkinsfile#handling-credentials)),
- **Secret file** - which is essentially secret content in a file,
- **SSH Username with private key** - an [SSH public/private key pair](http://www.snailbook.com/protocols.html),
- **Certificate** - a [PKCS#12 certificate file](https://tools.ietf.org/html/rfc7292) and optional password, or
- **Docker Host Certificate Authentication** credentials.

