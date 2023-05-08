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
	# sudo apt-get mysql-server php libapache2-mod-php php-mysql

    # Set MySQL root password
    #sudo mysql -e "ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '123456789'"

    # Restart Apache
    sudo systemctl restart apache2
  SHELL
end
