# IT Jobs Watch Data

## Introduction
The aim of this project is to take a simple jobs watch application, and provision it using. Once that is completed, it was the aim to push the completed code to the dev branch in github, which would trigger a jenkins job to run the Spec and InSpec tests. If these tests in Jenkins passed, it would then merge the code into the master branch of the github repository. Following this, a new jenkins job would be triggered by the merge to master branch, this job would then run the packer file to create the AMI in AWS.

## Installation

what we needed pre installed, python 3 and apt, pycharm

## Usage
_Pre-Requisites_
* Pycharm IDE
* Python 3.x + installed

### Installing packages
The necessary packages needed to run this program should automatically be picked up by pycharm. You may find a few pop ups within the IDE that state there are dependencies missing, if you simply install these through the IDE you should be set up correctly.  

# Creating the vagrantfile

Firstly, I configured the vagrant file so that it would provision the ubuntu virtual machine using the chef cookbook (Python) I was going to create which would allow the application to work.

### Python Cookbook ###

# Creating the Recipe

For the application to work we needed install all of the python packages listed in the app/requirements.txt file (this came to 19 python packages in total)  to ensure that python3 was installed as that was the compatible version. Additionally we needed to install pip so that we could use it as a tool to install multiple python packages. Once pip was installed, we installed all of the requirements needed for the running of the application. These requirements were located in the requirements.txt file of the /app folder. Installing these requirements proved difficult as the testing assured us that the shell command has been executed, however we could not tell if the packages themselves had definitely been installed (this we discovered not to be the case when we started to run the InSpec tests). Lastly in the recipe we had to create the directory and file where the application would store the jobs watch data once we had run the application.

# Creating the default_Spec tests

To ensure that our recipe file was running correctly, we introduced a series of tests that were executed when running the chef exec rspec command. Each installation stage of our recipe had its only test to ensure the packages had been installed and the directories/files were created. This section of the project was completed relatively quickly with the only minor errors we ran into being small syntax mistakes or spelling errors.

# creating the InSpec tests


### Running and using the program
To use the program simply right click on the `main.py` file and then click `Run 'main'`. This will run the command line user interface.

Follow the instructions to download via the various options given.

# Next steps
* Adding a job details search option (essentially be able to search for a specific role and return the details in a CSV)
* create a connected database for full deployment
* Build a scheduler as part of a full deployment to poll and add to the database
