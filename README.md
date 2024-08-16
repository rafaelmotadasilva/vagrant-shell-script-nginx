<h1>
    <img align="center" width="40px" src="vagrant-logo.png" alt="Vagrant logo">
    <span>Criando uma máquina virtual pelo Vagrant com servidor web</span>
</h1>

Repositório desenvolvido para fins educativos.

## Objetivo

Criar uma máquina virtual através de um arquivo do Vagrantfile. O provisionamento inclui a instalação do Nginx no Ubuntu 20.04, a configuração de um site (https://viacep.com.br/exemplo/jquery/), e a sincronização de uma pasta do host com a máquina virtual para hospedar o site no Nginx.

## Vagrantfile

Este é um exemplo simples de Vagrantfile, no entanto, há muitas opções que podem ser incluídas nesse arquivo.

```
# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-20.04"
  config.vm.network "public_network"
  config.vm.provision "shell", path: "install_nginx.sh"
  config.vm.synced_folder "website/", "/var/www/html"
end
```

Se mais de uma interface de rede estiver disponível na máquina host, o Vagrant solicitará que você escolha qual interface a máquina virtual deve fazer a ponte.

## Executando o script

A maneira mais simples de usar o script acima é copiar e colar o conteúdo em um arquivo chamado `Vagrantfile`.

Em seguida, em um terminal, execute o seguinte comando:

```
vagrant up
```
