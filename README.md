# FINAL PROJECT OS SERVER & SYSADMIN
HELLO, IM RAFID.
Before you read this page, im so sorry cuz im using english language to describe my final project. so take the note and read slowly.
i want to introduce my final project web server first.
what is web server?

A web server is software and hardware that uses HTTP (Hypertext Transfer Protocol) and other protocols to respond to client requests made over the World Wide Web. 
The main job of a web server is to display website content through storing, processing and delivering webpages to users. 
Besides HTTP, web servers also support SMTP (Simple Mail Transfer Protocol) and FTP (File Transfer Protocol), used for email, file transfer and storage.

So What is needed to create a web server?:
1. OS Debian Server
2. Web Server Apache2
3. Webmin Server Management
4. WinSCP
5. SSH Server


-------My Journey about the project--------


17 November 2023
---> install Debian Os 
---> install & Config Web Server

28 November 2023
---> Install Web Min & Konfig 

7 Desember 2023
---> Install Webmin & Add Website file
---> brought a cheapest web domain

8 Desember 2023
---> register cloudflare account
---> trying to tunneling my web server 

-------Remineder-------
if you needed the tutorial i will share on repo file. go check it!



1. Step one Install Apache2 Web Server

There is 2 famous web server which lot of people using. Nginx and Apache webserver.
As a Web server, Apache is responsible for accepting directory (HTTP) requests from Internet users and 
sending them their desired information in the form of files and Web pages. 
Much of the Web's software and code is designed to work along with Apache's features.

the reason why iam using this web server
> easy for beginner
> simple Configuration
> light and lot of community 

so lets begin!

1. go update first.
---> sudo apt update

2. install the apache2
---> sudo apt install apache2

3. check the firewall if you using firewall to connect.
---> sudo ufw app list

4. type this command
--->sudo ufw allow 'Apache'

5. check the firewall status
--->sudo ufw status

6. and then check status apache2
---> sudo systemctl status apache2
  Output
● apache2.service - The Apache HTTP Server
     Loaded: loaded (/lib/systemd/system/apache2.service; enabled; vendor preset: enabled)
     Active: active (running) since Thu 2020-04-23 22:36:30 UTC; 20h ago
       Docs: https://httpd.apache.org/docs/2.4/
   Main PID: 29435 (apache2)
      Tasks: 55 (limit: 1137)
     Memory: 8.0M
     CGroup: /system.slice/apache2.service
             ├─29435 /usr/sbin/apache2 -k start
             ├─29437 /usr/sbin/apache2 -k start
             └─29438 /usr/sbin/apache2 -k start

7. open your web browser and then type this.
---> http://your_server_ip
 
8. if you want something changes in your landing page so using this command
---> sudo nano /var/www/your_domain/index.html

9. make sure type this command after you change the index file
---> systemctl restart apache2
