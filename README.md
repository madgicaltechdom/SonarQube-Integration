# How to Integrate SonarQube with Github Actions  

This document outlines the steps to integrate SonarQube with Github Actions, allowing you to automate code analysis and quality checks for your repository.

Step by step user guide [video]().

## Prerequisites

Before you begin, make sure you have the following:

  - A Github account.
  - A SonarQube account or an instance of SonarQube running on your local machine or on a remote server.
  - Access to the repository you want to integrate SonarQube with.
  - A [GitHub App](https://docs.github.com/en/apps/creating-github-apps/creating-github-apps/creating-a-github-app).
  - GitHub App [permissions](https://docs.sonarqube.org/latest/devops-platform-integration/github-integration/#:~:text=Grant%20access%20for%20the%20following%C2%A0Repository%20permissions%3A%C2%A0)
  
NOTE: Do not worry about the GitHub App, permissions, and SonarQube Account these are already created and configured.
  
# Step for integration

## Step 1: Add SonarQube token and host url to Github Secrets

1. Navigate to your repository in Github and click the "Settings" tab.

2. Click "Secrets and variables" in the sidebar then select Actions.

3. Click "New repository secret" button and enter SONAR_TOKEN as the name.

4. Enter the SonarQube token as the value that has been shared with you on Passbolt.

5. Click "Add secret" to save. 

6. Create one more secret for SONAR_HOST_URL as the name and Enter this URL "https://sonarqube.madgicaltechdom.com" as the value.

## Step 2: Configure Github Actions

1. Navigate to your repository in Github and click the "Actions" tab.

2. Click the "New workflow" button and select "Set up a workflow yourself".

3. Give your workflow a name and create a new YML file.

4. Copy the YML code from this repo to your YML file.

5. Copy the "sonar-project.properties" file in your repo and provide your project key and project name(don't use others project key). That's it! Github Actions will now run a SonarQube analysis on every push to the main branch.

## Step 3: Check results of the analysis in SonarQube

1. Navigate to https://sonarqube.madgicaltechdom.com in your web browser.

2. Log in to SonarQube with the admin credentials.

3. In the Projects you will see that your project is integrated.
  
## License

This project is licensed under the [MIT License](LICENSE).
