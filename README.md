# multi-cloud-CI
This repo showcases a multi-cloud CI pipeline setup using GitHub Actions to automate installation, linting, and testing across AWS, Azure, and Google Cloud.

The general steps across all cloud providers are as follows: 
1. Create a repo containing Python project scaffold in Github.
    a. Files required: 
      - Makefile (format specific requiring tabs)
      - Requirements.txt
      - Python source code
      - Python testing code 

2. Navigate to cloud provider console and create a new project.

3. Open up cloud provider shell (Azure/GCP only) and set project in shell.

4. Install Python environment using `python3 -m venv ~/.envname` and activate Python environment using `source ~/.envname/bin/activate`

5. Create ssh key in cloud provider shell using `ssh-keygen -t rsa` and click return on all prompts.
   Run `cat /home/fi/key.pub` on printed path to view the public key and copy it.
   Go to Githubs > Settings > SSH and GPG keys > Create new SSH key > Add copied public key > Name key.

6.  Git clone repo made in Step 1 into your cloud shell.
  
7.  Run make all in folder of repo in cloud shell (or make [instruction] if you intend to run each component of Makefile individually)
   
8.  Set up a Github Actions configuration file (main.yaml) in .github/workflows/ folder. 
   - This can be done by selecting the `Actions` tab above followed by `Setting up workflow yourself`. 
   - The main.yaml file is format specific. Requires spaces not tabs. 
   - Once main.yaml is created, the Github Actions workflow is automatically initiated and can be viewed under `All Workflows` and is labelled by the name given in your main.yaml file. 

