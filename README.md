# Multi-Cloud CI Pipeline with GitHub Actions

This repository showcases a multi-cloud CI pipeline setup using **GitHub Actions** to automate installation, linting, and testing across **AWS**, **Azure**, and **Google Cloud**.

![image](https://github.com/user-attachments/assets/c98bc14d-7aa4-499c-96c2-5a59da8c5f4f) 
## General Workflow

The following steps outline how to set up a multi-cloud CI pipeline using GitHub Actions:

### 1. Create a Repository on GitHub
Start by creating a new repository on GitHub that will contain your Python project scaffold.

#### Required Files:
- `Makefile` (format specific requiring tabs)
- `requirements.txt`
- `source_python.py`
- `test_python.py`
- CI configuration file (`main.yaml`)

### 2. Set Up Cloud Provider Project
Navigate to the console of your chosen cloud provider and create a new project.

### 3. Cloud Shell Configuration (Azure/GCP)
Open up the cloud provider shell (i.e AWS CloudShell, Google Cloud Shell or Azure Cloud Shell) and set the project in the shell.

### 4. Set Up Python Environment
Install and activate a Python environment using the following commands:
`python3 -m venv ~/.envname`
`source ~/.envname/bin/activate`

### 5. Generate SSH Key From Cloud Shell and Configure Github (if not already done) 
Create an SSH key in the cloud provider shell:
`ssh-keygen -t rsa`
Press enter on all prompts and view the public key using `cat` on .pub path.
Copy the output and add it to Github under Settings > SSH & GPG keys > Create new SSH key

### 6. Clone the Github Repository 
git clone `github-repo`

### 7. Run Makefile
Navigate to repo directory in the cloud shell and run `Make all` or `Make <instruction>` if you want to run the install, lint, test steps individually. 

### 8. Setup Github Actions Workflow In Your Github Repo
Create a GitHub Actions configuration file (`main.yaml`) in the `.github/workflows/` folder.

#### Steps:

- Navigate to the **Actions** tab in your GitHub repository.
- Select **Set up a workflow yourself**.
- Configure the `main.yaml` file (ensure it uses spaces, not tabs).

Once `main.yaml` is created, the GitHub Actions workflow will be automatically triggered and can be viewed under the **Actions** tab in the repository.

### 9. Monitor CI Pipeline

The workflow will be labeled by the name given in your `main.yaml` file and can be monitored under **All Workflows** in the **Actions** tab.
