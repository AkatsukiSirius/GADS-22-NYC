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

Step 1: Download and install VirtualBox

 - Go to the Virtualbox download page and download the appropriate binary. 
 - Open the binary and follow the installations instructions.

Step 2: Download and install Vagrant

    Go the Vagrant download page and download the appropriate binary. Open the binary and follow the installations instructions.

Step 3: Download and start the Data Science Toolbox

    Open a terminal (also known as the command prompt in Microsoft Windows). Create a directory, for example "gadatasciencetoolbox", and navigate to it:

$ mkdir MyDataScienceToolbox
$ cd MyDataScienceToolbox

    Next, run the following commands:

$ vagrant init data-science-toolbox/dst
$ vagrant up

Step 4: Log in (on Mac OS X and Linux)

    If you are running Mac OS X or some other UNIX-like operating system, you can log in to the Data Science Toolbox by simply running the following command in a terminal:

vagrant ssh

Step 4: Log in (Windows)

    If you are running Microsoft Windows, you need to use a third-party application in order to log in to the Data Science Toolbox. We recommend Putty for this. Go to its download page and download putty.exe. Run putty.exe and enter the following values:

Host Name (or IP address): 127.0.0.1
Port: 2222
Connection type: SSH

(If you want, you can save these values as a session by clicking the "Save" button, so that you do not need to enter these values again.)

Next, click the "Open" button and enter "vagrant" for both the username and the password.
Step 5: Install GA Data Science Bundle

    Run the following commands:

vagrant@data-science-toolbox:~$ dst update
vagrant@data-science-toolbox:~$ dst add gads

(Note that vagrant@data-science-toolbox:~ indicates that this command should be run on the Data Science Toolbox.)
Step 6: Set up IPython Notebook

Now that you are logged into your new virtual machine, invoke the following command to create a password-protected profile:

vagrant@data-science-toolbox:~$ dst setup base

Next, $ exit out of the virtual machine and use your favorite text editor to open up the Vagrantfile in the MyDataScienceToolbox directory. Uncomment and edit the line somewhere around line 22 to the following:

config.vm.network "forwarded_port", guest: 8888, host: 8888

This line instructs Vagrant to open up port 8888 so that the IPython Notebook server is accessible from your browser. Restart the Data Science Toolbox and log in again so that the changes take effect:

$ vagrant reload
$ vagrant ssh

To start the IPython Notebook server, run:

vagrant@data-science-toolbox:~$ sudo ipython notebook --profile=dst

    You can now access the IPython Notebook server at https://localhost:8888. Because the SSL certificate is self-signed, you may get a warning message from your browser. The image below shows how Chrome complains about this. Because you know what's on the server-side, you can just click on the "Proceed anyway" button.

Fork the assignments repo:

Once you've setup the Data Science Toolbox, clone your fork of the class repository. We'll be using the Fork and Pull git model. You will be pushing changes to your forked repository, and submitting pull requests to the class repository.

From the github help page:

    The Fork & Pull Model lets anyone fork an existing repository and push changes to their personal fork without requiring access be granted to the source repository. The changes must then be pulled into the source repository by the project maintainer.

For example, from the home directory:

vagrant@data-science-toolbox:~$ cd ~/; git clone git@github.com/<my git handle>/fall_2014_assignments.git

