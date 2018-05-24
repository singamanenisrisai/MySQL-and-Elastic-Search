The following is the installation procedure we have followed to run Queries in both MySQL and Elastic Search.

Step 1: We choose Amazon EC2 as our Instance for Infrastructure as a Platform. For that we have to register for amazon web services.

Step 2: Now we connected to remote server using "Putty".

Step 3: After connecting to remote server we need to update MySQL(If already there) in server. The following are the commands to update MySQL Query:
	> sudo apt-get update
	> sudo apt-get install mysql-server
	> systemctl status mysql.service
	> mysql_secure_installation
	> sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf (Locate blind-address 127.0.0.1 and change it to 	   0.0.0.0)
	> sudo systemctl restart mysql.service
	> mysql -h localhost -u myname -p password mydb
	> mysql -u root -p yourpassword
	> CREATE USER 'myuser'@'localhost' IDENTIFIED BY 'mypass';
	> CREATE USER 'myuser'@'%' IDENTIFIED BY 'mypass';
	> CREATE DATABASE busDB;
	> GRANT ALL ON *.* TO 'myuser'@'localhost';
	> GRANT ALL ON *.* TO 'myuser'@'%';

Step 4: After successfully setting up MySQL in Server now we installed GUI for performing Queries on Data for that we choose DataGrip to run Queries on Database.

Step 5: After executing required Queries now we installed ElasticSearch in our Server.

Step 6: The following are the commands need to be performed in terminal to install ElasticSearch:
	> sudo add-apt-repository -y ppa:webupd8team/java
	> sudo apt-get update
	> sudo apt-get -y install oracle-java8-installer
	> wget -qO - https://packages.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
	> echo "deb https://artifacts.elastic.co/packages/6.x/apt stable main" | sudo tee -a  /etc/apt/sources.list.d/elastic-6.x.list
	> sudo apt-get update && sudo apt-get install elasticsearch
	> sudo nano /etc/elasticsearch/elasticsearch.yml
	> sudo service elasticsearch restart

Step 7: After seting up ElasticSearch we used PostMan as interface to run our queries in server.

As a reference we followed Dalhousie University CSCI 5408 Course material :
   https://web.cs.dal.ca/~kosmajac/CSCI5408_tutorials/a1.html#aws

ElasticSearch and MySQL implementation is present in their respective folder.


