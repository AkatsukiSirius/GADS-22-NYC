#Lesson 1 Introduction to Data Science
###June 3rd 2015

###Objectives for this class:

- Get to know each other!
- Setup your computer environment
- Discuss Data Science

###Download and Install the Anaconda Scientific Python Distribtuion

https://store.continuum.io/cshop/anaconda/

This includes the iPython Notebook environment

###or

###Working within a Virtual Environment

####Step 1: Download and Install VirtualBox

 - Go to the Virtualbox download page and download the appropriate binary. 
 - https://www.virtualbox.org/wiki/Downloads
 - Follow the installations instructions.

####Step 2: Download and Install Vagrant

 - Go the Vagrant download page and download the appropriate binary. 
 - https://www.vagrantup.com/
 - Follow the installations instructions.

####Step 3: Download and start the Data Science Toolbox

 - Open a terminal (also known as the command prompt in Microsoft Windows). 
 - Create a directory, name it, (for example "gadatasciencetoolbox"), then navigate to it:

$ mkdir MyDataScienceToolbox
$ cd MyDataScienceToolbox

- Execute the following commands

$ vagrant init data-science-toolbox/dst
$ vagrant up

Step 4: MAC OS X or LINUX

 - Log in to the Data Science Toolbox by excuting the following command in a terminal:

$ vagrant ssh

####-OR-

####Step 4: MICROSOFT WINDOWS

 - If you are running Microsoft Windows, you need to use a third-party application in order to log in to the Data Science Toolbox. 
 - We recommend Putty. 
 - Download Putty.
 - http://www.putty.org/
 - Execute putty.exe and enter the following values:

Host Name (or IP address): 127.0.0.1
Port: 2222
Connection type: SSH

 - You can save these values as a session by clicking the "Save" button, prevents you from having to re-enter them.
 - Click the "Open" button and enter "vagrant" for both the username and the password.

####Step 5: Install GA Data Science Bundle

 - Execute these commands:

vagrant@data-science-toolbox:~$ dst update
vagrant@data-science-toolbox:~$ dst add gads

 - Note that vagrant@data-science-toolbox:~ indicates that this command should be run on the Data Science Toolbox.

####Step 6: Set up IPython Notebook

 - Now that you are logged into your new virtual machine, execute the following command to create a password-protected profile:

vagrant@data-science-toolbox:~$ dst setup base

- Exit out of the virtual machine

vagrant@data-science-toolbox:~$ exit

- Use your favorite text editor to open up the Vagrantfile in the MyDataScienceToolbox directory. 
- Uncomment and edit the line somewhere around line 22 to the following:

config.vm.network "forwarded_port", guest: 8888, host: 8888

- This line instructs Vagrant to open up port 8888 so that the IPython Notebook server is accessible from your browser.
- Restart the Data Science Toolbox and log in again so that the changes take effect:

$ vagrant reload
$ vagrant ssh

- To start the IPython Notebook server, execute:

vagrant@data-science-toolbox:~$ sudo ipython notebook --profile=dst

- You can now access the IPython Notebook server at https://localhost:8888. 
- Because the SSL certificate is self-signed, you may get a warning message from your browser. 
- Just click to proceed.

####Step 7: Fork the assignments repo:

 - Clone your fork of the class repository. 
 - From the home directory:

vagrant@data-science-toolbox:~$ cd ~/ 
vagrant@data-science-toolbox:~$ git clone git@github.com/https://github.com/ga-students/GADS-22-NYC.git

