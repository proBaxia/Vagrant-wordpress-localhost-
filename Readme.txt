THIS PROJECT IS TO USE Vagrant TO CREATE A WORDPRESS SITE 
**********************************************************
create a folder > project-wordpess and a Vagrantfile to create ubuntu/focal64  Vagrant init copy and paste this in 
your vagrant file 
-------------------------------------------------------------------------------------
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.ssh.insert_key = false

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
    vb.cpus = 2
  end

  config.vm.network "private_network", ip: "192.168.33.10"
  config.vm.network "forwarded_port", guest: 80, host: 8080
  
  config.vm.provision "shell", inline: <<-SHELL
    # Update package list
    sudo apt-get update

    # Install some useful packages
    sudo apt-get install -y git curl

    # Install Apache, MySQL, and PHP
    sudo apt-get install -y apache2
    # Restart Apache
    sudo systemctl restart apache2
  SHELL
end
--------------------------------------------------------------------------------------------------
"vagrant status" to check if your vagrant is runing
"vagrant ssh" to login into your ubuntu
"sudo apt-get update -y"
go to your browser and check if your apache server is runing, copy an paste "localhost:8080" to your browser
"sudo apt-get install mariadb-server mariadb-client"
"sudo systemctl start mariadb"
"sudo systemctl status mariadb"
"sudo mysql_secure_installation"

NOTE: RUNNING ALL PARTS OF THIS SCRIPT IS RECOMMENDED FOR ALL MariaDB
      SERVERS IN PRODUCTION USE!  PLEASE READ EACH STEP CAREFULLY!

In order to log into MariaDB to secure it, we'll need the current
password for the root user.  If you've just installed MariaDB, and
you haven't set the root password yet, the password will be blank,
so you should just press enter here.

Enter current password for root (enter for none):
OK, successfully used password, moving on...

Setting the root password ensures that nobody can log into the MariaDB
root user without the proper authorisation.

Set root password? [Y/n] y
New password:
Re-enter new password:
Password updated successfully!
Reloading privilege tables..
 ... Success!


By default, a MariaDB installation has an anonymous user, allowing anyone
to log into MariaDB without having to have a user account created for
them.  This is intended only for testing, and to make the installation
go a bit smoother.  You should remove them before moving into a
production environment.

Remove anonymous users? [Y/n] y
 ... Success!

Normally, root should only be allowed to connect from 'localhost'.  This
ensures that someone cannot guess at the root password from the network.

Disallow root login remotely? [Y/n] y
 ... Success!

By default, MariaDB comes with a database named 'test' that anyone can
access.  This is also intended only for testing, and should be removed
before moving into a production environment.

Remove test database and access to it? [Y/n] y
 - Dropping test database...
 ... Success!
 - Removing privileges on test database...
 ... Success!

Reloading the privilege tables will ensure that all changes made so far
will take effect immediately.

Reload privilege tables now? [Y/n] y
 ... Success!

Cleaning up...

All done!  If you've completed all of the above steps, your MariaDB
installation should now be secure.

Thanks for using MariaDB!

"sudo apt-get install php -y"
"sudo apt-get install php"
"sudo apt-get install wget -y"
"apt install unzip -y"
wget https://wordpress.org/latest.tar.gz
"unzip latest.zip" or "tar -xzvf latest.tar.gz"
cd wordpress
"sudo cp -r * /var/www/html"
"cd /var/www/html"
"sudo rm -rf index.html"
"sudo apt install php-mysql php-cgi php-cli php-gd -y"
"sudo systemctlrestart apache2"
"sudo chown -R www-data:www-data /var/www/"
paste to your browser "localhost:8080"
"sudo mysql -u root -p"
create a database = "create database wordpress;"
create user "wordpress"@"%" identified by "Try#####rf!";
now grant all privileges
grant all privileges on wordpress.* to "wordpress"@"%";
now exit from the mysql >> exit
go to your browser and  paste to your browser localhost:8080 and install wordpress from your browser
select your language >> English and press continue 
Enter your Database connection 
Database Name  >> The name of the Database you wang to use with wordpress Name
Username       >> your Database username 
Password       >> Your Database Password
Database Host  >> your local host or web Host   
click on and submit 

create your Site Title  proBxai.com  
            Username     language
			password     12hshstgyDD!>!
			your Email   language890@gmail.com
			
click in Install wordpress

login username or Email Address
LOGIN PASSWORD 
              WELCOME TO WORDPRESS 
THIS IS THE PROJECT I CREATED WITH Vagrant TO CREATE A WORDPRESS SITE ON MY LOCALHOST
**************************************************************************************
5/8/2023  If there is mistake on please let me know . wordpess is working fine on my localhost
Thank you 
 