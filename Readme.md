1. sudo apt update && sudo apt upgrade -y
2. sudo apt install apache2 -y 
3. sudo apt install php -y
4. sudo apt install mariadb-server php-mysql -y
5. sudo service apache2 restart
6. sudo mysql_secure_installation
7. You will be asked Enter current password for root (type a secure password): press Enter
	Type in Y and press Enter to Set root password
	Type in a password at the New password: prompt, and press Enter. Important: remember this root password, as you will need it later
	Type in Y to Remove anonymous users
	Type in Y to Disallow root login remotely
	Type in Y to Remove test database and access to it
	Type in Y to Reload privilege tables now
8. sudo mysql --user=root --password
	> create user root@localhost identified by 'your_password';
	> grant all privileges on *.* to root@localhost;
	> FLUSH PRIVILEGES;
	> exit;
9. sudo apt install phpmyadmin -y 
10. sudo phpenmod mysqli
11. sudo service apache2 restart
12. go to http://localhost/phpmyadmin
13. enter user and password from 8.
14. extract Vending_Machine.zip to path /var/www/html
15. sudo cp vmproject.sql /home/pi/Desktop
16. go to New and create database name 'vmproject'
17. go to import and Browse file vmproject.sql
18. go to dbConfig.php and edit $dbPassword = ""; to $dbPassword = "your_password(from 8.)";
19. open browser and go to localhost/index.php