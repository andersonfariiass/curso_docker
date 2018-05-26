# -*- mode: ruby -*-
# vi: set ft=ruby :


VAGRANTFILE_API_VERSION = "2"

[
  { :name => "vagrant-reload" },
  { :name => "vagrant-vbguest" },
].each do |plugin|

  if not Vagrant.has_plugin?(plugin[:name])
    raise "#{plugin[:name]} is required. Please run `vagrant plugin install #{plugin[:name]}`"
  end
end

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

	# VM do Gerenciador do docker
	config.vm.define "docker" do |docker|

		# Hostname da VM
		docker.vm.hostname = "docker.localdomain"
		
		# Imagem que será utilizada para configurar a VM
		docker.vm.box = "ubuntu/xenial64"
		
		# Configuracao da Rede e IP
		docker.vm.network "private_network", ip: "192.168.50.10"
		
		# Executa script para a configuracao do ambiente
		docker.vm.provision "shell", inline: "/bin/bash /vagrant/init-config.sh curso_docker"

		
		# Restart da VM para efetivar as atualizacoes dos pacotes instalados
		docker.vm.provision :reload		
		

		# Configuracoes passadas ao Provisionador, neste caso o VirtualBox
		docker.vm.provider "virtualbox" do |vbox|
		        
			# Desabilitar Tela
			vbox.gui = false
		
			# Nome da VM no VirtualBox
			vbox.name = "curso_docker"
			
			# Qtd de CPUs
			vbox.customize [ "modifyvm", :id, "--cpus", "1" ]
		        
			# Qtd de Memoria RAM
			vbox.customize [ "modifyvm", :id, "--memory", "512" ]
		end
	end
end
