# vagrant-docker-java11-maven3.8.4
 this repository contain a vagrantfile and a docker file for a ready to go development environment for java 11 (jdk11) and maven version 3.8.4 by using vagrant and docker.

# How make it work ?

## Requirements
- [Vagrant](https://www.vagrantup.com/)
- [docker](https://www.docker.com/products/docker-desktop)
- (optional) [Visual Studio Code](https://code.visualstudio.com/)

## Customize

To make the vagrantfile working you need to modify at least the `config.vm.synced_folder` line and change the path to the folder of your project that you want to use in the VM (in that case all you java project or at least the one you are working on atm). Otherwise you will not be able to access it on the vagrant VM


## Start the environnement
First of all launch docker if it isn't already running

then to start the environnement you need to first clone the repository and open the repository folder in a terminal/CMD and run the command `vagrant up --provider=docker`

that's it ! the first time may take some times depending on you internet connection as it download the docker image and install the tools needed for your development !

## Stop the environnement

to stop the environnement you can just run the command `vagrant destroy` or  `vagrant halt`

even if you destroy the vagrant VM your file will be saved as it is saved in real time (everything you change on files in the VM will be change on the files on your host machine in the same time).

# How to use it ?

that's cool we have our vm running now but how do I code now ? 

well I personally use VSC to it but since your ide allow ssh connection you can use it.

run the command in the repository folder `vagrant ssh-config > vm_ssh_config`

it will create the file `vm_ssh_config` in the folder with the information needed to connect to VSC (as I don't use another IDE idk if it can be use by others, it's to you to search depending on the IDE you are using)

if you can't use the ssh file to connect you can connect with the string `vagrant@127.0.0.1:2222` and vagrant as password (you can change it in the dockerfile line 20 --> `RUN echo -n 'vagrant:yourPassword' | chpasswd`)

enjoy !
# Why ?

you are probably wondering why ? why did I make and use a development environment with vagrant instead of directly installing the tools I needed on my machine ?

The reason is simple, I have two PCs. A desktop computer and a laptop. I use my desktop computer as my main computer but for my courses I need a laptop to be able to work in my school premises. During the lockdown I was taking my classes from home so all my tools were installed on my desktop computer. Recently I had to go back to my school premises to attend my classes and I had to reinstall everything on my laptop which took a long time and was annoying.

In the meantime I discussed this with one of my classmates and he told me that he was using vagrant now for his development environment as he had too many installation problems.

I had already tried to use vagrant but had problems running it with VirtualBox because of compatibility issues between Hyper-V and VirtualBox on Windows (I never succeed to use hyper-V either).

Since I was already using docker for my databases and stuff I decided to use it with vagrant when I saw that it was possible! 

I decided to make a repository to save my different development environment and to be able to recover them easily ! but if you want to use them don't hesitate and enjoy !

