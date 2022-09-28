## STEP 1 -INSTALLING THE NGINX WEB SERVER 
Since this is our first time using apt for this session, start off by updating your server’s package index. Following that, you can use apt install to get Nginx installed:
```
sudo apt update
sudo apt install nginx 
```
When prompted, enter Y to confirm that you want to install Nginx. Once the installation is finished, the Nginx web server will be active and running on your Ubuntu 20.04 server.

To verify that nginx was successfully installed and is running as a service in Ubuntu, run:
```
sudo systemctl status nginx
```
Before we can receive any traffic by our Web Server, we need to open TCP port 80 which is default port that web brousers use to access web pages in the Internet.

As we know, we have TCP port 22 open by default on our EC2 machine to access it via SSH, so we need to add a rule to EC2 configuration to open inbound connection through port 80:

Our server is running and we can access it locally and from the Internet (Source 0.0.0.0/0 means ‘from any IP address’).

First, let us try to check how we can access it locally in our Ubuntu shell, run:

```
curl http://localhost:80
or
curl http://127.0.0.1:80
```
To check and retrieve your public ip address, other than to check it in AWS web console, is to use following command
```
curl -s http://169.254.169.254/latest/meta-data/public-ipv4
```
The URL in browser shall also work if you do not specify port number since all web browsers use port 80 by default.

### STEP 2 -INSTALLING MYSQL
Now that you have a web server up and running, you need to install a Database Management System (DBMS) to be able to store and manage data for your site in a relational database. MySQL is a popular relational database management system used within PHP environments, so we will use it in our project.
Again, use ‘apt’ to acquire and install this software:
```
$ sudo apt install mysql-server



