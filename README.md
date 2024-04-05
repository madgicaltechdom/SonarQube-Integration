# How to Integrate SonarQube with Github repo using GitHub Actions  

This document outlines the steps to integrate SonarQube with GitHub Actions, allowing you to automate code analysis and quality checks for your repository.

Step-by-step user guide [video](https://drive.google.com/file/d/1rNEKbCRrVD_9dRz_SdmfCImr0dpMJgKa/view?usp=sharing).

NOTE: This SonarQube integration will work on a single branch at a time.

## Prerequisites

Before you begin, make sure you have the following:

  - A GitHub account.
  - A SonarQube account or an instance of SonarQube running on your local machine or on a remote server.
  - Access to the repository you want to integrate SonarQube with.
  - A [GitHub App](https://docs.github.com/en/apps/creating-github-apps/creating-github-apps/creating-a-github-app)(for SonarQube setup).
  - GitHub App [permissions](https://docs.sonarqube.org/latest/devops-platform-integration/github-integration/#:~:text=Grant%20access%20for%20the%20following%C2%A0Repository%20permissions%3A%C2%A0)(for SonarQube setup).
  - AWS SonarQube machine(to create it use SonarQube Bitnami AMI).
  - A domain(for SonarQube setup).
  - [Configure SSL with the Bncert tool](https://www.youtube.com/watch?v=BF4OlDwPZds&t=185s). 
  
# Step for integration

## Step 1: Set up SonarQube

1. Navigate to your domain in your web browser.

2. Log in to SonarQube with the admin credentials.

3. Click on the Administrator icon > My Account > Security > Generate to generate a token for your project. Note down this token as it will be needed later(provide details according to your need like token type and Expires in).

4. Create a new project in SonarQube by following these steps(only for the first time):

  - Click the "Create project" button on the SonarQube dashboard.
  - Select GitHub.
  - Provide all the details like GitHub App details and other details.

## Step 2: Add SonarQube token and host URL to Github Secrets

1. Navigate to your repository in Github and click the "Settings" tab.

2. Click "Secrets and variables" in the sidebar then select Actions.

3. Click the "New repository secret" button and enter SONAR_TOKEN as the name.

4. Enter the SonarQube token as the value that has been shared with you on Passbolt.

5. Click "Add secret" to save. 

6. Create one more secret for SONAR_HOST_URL as the name and Enter your domain as the value.

## Step 3: Configure Github Actions

1. Navigate to your repository in Github and click the "Actions" tab.

2. Click the "New workflow" button and select "Set up a workflow yourself".

3. Give your workflow a name and create a new YML file.

4. Copy the YML code from this repo to your YML file.

5. Copy the "sonar-project.properties" file in your repo and provide your project key and project name(don't use other's project key). That's it! GitHub Actions will now run a SonarQube analysis on every push to the main branch.

## Step 4: Check the results of the analysis in SonarQube

1. Navigate to your domain in your web browser.

2. Log in to SonarQube with the admin credentials.

3. In the Projects you will see that your project is integrated.

## Step 5: To know the SonarQube admin credentials.

1. Connect to the SonarQube machine.

2. Run the below command:

```
sudo cat /home/bitnami/bitnami_credentials
```
  
## License

This project is licensed under the [MIT License](LICENSE).
