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

1. Step one Install Debian Os Server
tsupp guys, in this page im gonna show you why im using this Operation System for my project and how to install this Os.
by the way, there is os server except debian os which you can install, example:

> Windows server
> Ubuntu server
> Centos
> etc


   1. First, download the ISO file of Debian from the official website of Debian.
   
   2. Create a New Debian Virtual Machine
   
   3. First, set a name for the VM (for example Debian), then choose Linux
      as the “Type” of the VM, and finally choose Debian (64bit) as the “Version”.
   
   4. now, click on the “ISO Image” and select the downloaded Debian ISO file
      from the host operating system. Then, click on “Next”.
   
   5. In hardware settings, setting memory, 2 core processor, and click “Next”.
   
   6. Create a virtual hard disk of 60 GB, and hit “Next”.
   
   7. The following table in the image summarizes the configuration of the new virtual machine. Finally, click on “Finish”.
   
   8. start your vm.
   
   9. choose Graphical Install
   
   10. choose your language
   
   11. set a hostname and then continue
   
   12. set a domain name and then continue
   
   13. set your root password and then continue
   
   14. write full name and password of the user --> continue
   
   15. set up time zone, disk partition, and then click next until the system reboot.   

2. Step two Install Apache2 Web Server

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
   
   8. open your web browser and then type this.
   ---> http://your_server_ip
    
   9. if you want something changes in your landing page so using this command
   ---> sudo nano /var/www/your_domain/index.html
   
   10. make sure type this command after you change the index file
   ---> systemctl restart apache2

3. Step three Install Webmin
   -----Install Webmin Server Management-----

What is Webmin?
Webmin is a web-based server management control panel for Unix-like systems. 
Webmin allows the user to configure operating system internals, such as users, disk quotas, services and configuration files, 
as well as modify and control open-source apps, such as BIND, Apache HTTP Server, PHP, and MySQL.

lets begin the installation and configuration.

   1. First, update your server’s package index
   ---> sudo apt update && sudo apt upgrade
   
   2. Open the file in your preferred editor. Here, we’ll use nano
   ---> sudo nano /etc/apt/sources.list
   
   3. Download the Webmin PGP key with wget and add it to your system’s list of keys:
   ---> wget -q -O- http://www.webmin.com/jcameron-key.asc | sudo apt-key add
   
   4. Next, update the list of packages repo and then install Webmin
   ---> sudo apt update
   ---> sudo apt install webmin
   
   5. Wait until the process end, if you want to change the password for root login in webmin just using this command
   ---> sudo /usr/share/webmin/changepass.pl /etc/webmin root [new password]
   
   6. Open your Web Browser Chrome/Edge and then type:
   ---> https://<your server ip address>:10000
   
     username : root
     password : <password>



   
   7. next, you will find dashboard page and lot tools which you can use it.
   

4. Step four Install WinSCP
   

