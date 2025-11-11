Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/bionic64"

  # Lab wants a host-only private network:
  config.vm.network "private_network", ip: "192.168.33.10"

  # Provision: install Apache, write a test page
  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    sudo apt-get install -y apache2
    echo "Hello From Vagrant" | sudo tee /var/www/html/index.html
  SHELL
end
