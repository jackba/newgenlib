## What is NGL WorkBench? ##
NGL WorkBench is a NewGenLib Utility Application. This utility application has tools like
  1. Printing patron cards
  1. Printing barcode labels
  1. Import patron data from XML and spread sheets
In the future, NGL WorkBench will have migration tools for various ILMS systems.
## Getting started with NGL WorkBench ##
### Download ###
For both Windows and Linux you can download the NGL WorkBench from? http://sourceforge.net/projects/newgenlib/files/NGL%20Work%20Bench/Version%201.0/NGLWorkBench.zip/download
### Installation ###
We recommend to do the installation on the Server. You can also install it on client machines.

Step 1: The above link will download a zip file named? NGLWorkBench.zip.

Step 2: If you extract the above zip file, you will get 2 directories. One is NGLWorkBench and the second file is NGLWorkBenchFiles

Step 3: Place NGLWorkBenchFiles directory in C: Drive (in /usr directory if you are on Linux). You can place NGLWorkBench directory anywhere

Step 4: In C:/NGLWorkBenchFiles (For linux /usr/NGLWorkBenchFiles) directory you will find a file named database.properties. Open it with your favourite text editor. And edit the below values carefully
```
host=localhost

port=5432

username=newgenlib

password=newgenlib

databaseName=newgenlib
```
Save the file.

<u>''If you are installing on a client system, then make a note of the Server IP address. For example, if the server IP is 192.168.1.4, then instead of host=localhost put the IP address. Which means the line looks like this host=192.168.1.4''</u>

Step 5: Now double click on RunNGLWorkBench.bat file to run the application