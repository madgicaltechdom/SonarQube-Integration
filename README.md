# How to Integrate SonarQube with Github Actions  

This document outlines the steps to integrate SonarQube with Github Actions, allowing you to automate code analysis and quality checks for your repository.

Step by step user guide [video](https://drive.google.com/file/d/1S7olin2qi3teOROwdB4oWxwMQB8EyAJx/view?usp=sharing).

## Prerequisites

Before you begin, make sure you have the following:

  - A Github account.
  - A SonarQube account or an instance of SonarQube running on your local machine or on a remote server.
  - Access to the repository you want to integrate SonarQube with.
  - A [GitHub App](https://docs.github.com/en/apps/creating-github-apps/creating-github-apps/creating-a-github-app).
  - GitHub App [permissions](https://docs.sonarqube.org/latest/devops-platform-integration/github-integration/#:~:text=Grant%20access%20for%20the%20following%C2%A0Repository%20permissions%3A%C2%A0)
  
# Step for integration

## Step 1: Set up SonarQube

1. Navigate to https://sonarqube.madgicaltechdom.com in your web browser.

2. Log in to SonarQube with the admin credentials.

3. Create a new project in SonarQube by following these steps:

  - Click the "Create project" button on the SonarQube dashboard.
  - Select Manually.
  - Provide all the details like "Project display name", "Project key", and "branch name" then click "Set Up" button.
  
## Step 2: Configure Github Actions

1. Navigate to your repository in Github and click the "Actions" tab.

2. Click the "New workflow" button and select "Set up a workflow yourself".

3. Give your workflow a name and create a new YAML file.

4. Copy the YML code from this repo to your YML file.

5. Copy the "sonar-project.properties" file in your repo and provide your project key.

## Step 3: Add SonarQube token and host url to Github Secrets

1. Navigate to your repository in Github and click the "Settings" tab.

2. Click "Secrets" in the sidebar.

3. Click "New secret" and enter SONAR_TOKEN as the name.

4. Enter the token generated for your SonarQube project in step 1 as the value.

5. Click "Add secret" to save. 

6. Create one more secret for SONAR_HOST_URL as the name and Enter the URL "https://sonarqube.madgicaltechdom.com" as the value.

That's it! Github Actions will now run a SonarQube analysis on every push to the main branch. You can view the results of the analysis in SonarQube by navigating to the project dashboard.

# Reference 

I got information from the below articles:

  - [Deploy Firebase functions using GitHub Actions](https://davelms.medium.com/deploy-firebase-functions-using-github-actions-7dbafbd4df77)
  - [Changed Files](https://github.com/marketplace/actions/changed-files)
  - [Manual Workflow Approval](https://github.com/marketplace/actions/manual-workflow-approval)
  
## License

This project is licensed under the [MIT License](LICENSE).
