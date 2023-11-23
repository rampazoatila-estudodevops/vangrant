Vagrant.configure("2") do |config|
 
  config.vm.box = "ubuntu/focal64"
  
  config.vm.network "forwarded_port", guest: 80, host: 8080
  
  config.vm.synced_folder "./html", "/var/www/html"
  
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
    vb.cpus = 3
    vb.name = "Maquina"
  end

  config.vm.provision "shell", inline: <<-SHELL
    apt update
    apt install -y nginx
    apt install net-tools
  SHELL
end
