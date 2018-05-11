# Senior-Design-CS-Scheduler
This is the code that was used for the CS Class Scheduler web application. This includes the frontend, backend, and algorithm code.

This is the code that was created for the CS Class Sceduler. The code has been reformatted to be impleted in a clean install. Changes were made like not including passwords or working url endpoints.

We do not want to login as root since it can be very dangerous. We are going to create a new user that will have root prileges
https://www.digitalocean.com/community/tutorials/how-to-create-a-sudo-user-on-ubuntu-quickstart

After, try login in as the new user that was created and run a simple root script.
sudo ls -la /root

If you can see the information then the user has root access. Now we will close down root login.
sudo vi /etc/ssh/sshd_config

find PermitRootLogin and change it from yes to no
run this to restart the shell.

sudo systemctl restart sshd

The following instructions is to create and install the API to a Digital Ocean Server.
https://www.digitalocean.com/community/tutorials/how-to-install-apache-tomcat-7-on-ubuntu-14-04-via-apt-get

installing MySQL
https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-16-04

Create a new user in MySQL and allowing limited access to those users
https://dev.mysql.com/doc/refman/8.0/en/adding-users.html

Once this is installed, go to the GUI and login in with the credentials that you inserted in the tomcat-users.xml 
This adding of users with passwords was done in step 5 of the following link.
https://www.digitalocean.com/community/tutorials/how-to-install-apache-tomcat-7-on-ubuntu-14-04-via-apt-get

Now that the GUI is open. We will drop the war file for the api. 

In the shell open MySQL and create a new database and insert everything from the School.sql file.

Inside the api files redirect to the database.java inside the accessObjects folder and enter the database information password, username, and url. *The credentials from the server should be the same as the local one it can get difficult keeping track of info if they are both different* 

Open Eclipe and open an existing project use the directory to find the repo and select the RESTfulProject inside the Jersey folder.
You can test local by setting up a local server and running http://localhost:8080/RESTfulProject/REST/WebService/Paths
If no status code error shows up and the information from the database shows up then - File -> Export -> war file

Once up try the ip address of the server with the url /RESTfulProject/REST/WebService/Paths and it should display as the local.

Frontend stuff is drag and drop using Filezilla but for the csv file it should be inserted into the folder that contains the installation of apache. 
The file should be dropped here from root /var/lib/tomcat7 .

FAQ
The server stopped working?
Run this in the shell- sudo systemctl restart tomcat7.service
if that didnt work restart the whole project from step 1.

The roadmap is taking a long time or not loading.
Does the server have more than 1 gb of memory. If not that is why, it requires more than a gigabyte of memory to execute. Dont be cheap get the good server.

My CIN does not work if I log in.
The CIN has to exist first inside the database for it to work on register and login.

Is this project complete?
No, we did not implement a few endpoints, save function for the roadmap, and a few other things to make it better and nice. 

Does it contain an easter egg?
I can't say you have to find it. 
