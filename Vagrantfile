Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/precise64"
  config.vm.box_version = "1.1.0"
  config.vm.hostname = "pg84"
  config.vm.network "private_network", ip: "192.168.56.84"

  config.vm.provision "shell", inline: <<-SHELL
    export DEBIAN_FRONTEND=noninteractive
    sudo sh -c 'echo "deb http://old-releases.ubuntu.com/ubuntu/ precise main universe" > /etc/apt/sources.list'
    sudo apt-get update
    sudo apt-get install -y wget ca-certificates debconf-utils

    # Автоматически отвечаем debconf на obsolete warning
    echo "postgresql-common postgresql-common/obsolete-major error" | sudo debconf-set-selections

    # Устанавливаем PostgreSQL 8.4
    sudo apt-get install -y postgresql-8.4

    # Принудительно донастроить все пакеты
    sudo dpkg --configure -a

    # Проверим статус сервиса
    sudo service postgresql status
  SHELL
end
