# curso_docker

Neste repositorio conterá os arquivos e procedimentos necessários para subir um ambiente básico virtualizado para curso de docker.

Listagem de arquivos:
		
	Vagrantfile - Arquivo que automatiza o provisionamento da maquina virtual.
	init-config.sh - Shell Script que automatiza a instalação dos pacotes necessários, e algunas configurações da VM.

Procedimeto para configuração do ambiente
	
	Faça download e instalação do vagrant no site oficial https://www.vagrantup.com/downloads.html
	Faça download e instalação do VirtualBox
	Faça download deste projeto (git clone https://github.com/andersonfariiass/curso_docker.git)
	Dentro do diretório raiz (curso_docker/) execute o comando - vagrant up
	Para acessar a vm digite o comando: vagrant ssh nome_da_vm

Executando os procedimentos acima,será criado no VirtualBox uma VM:
	
	curso_docker: 192.168.50.10

