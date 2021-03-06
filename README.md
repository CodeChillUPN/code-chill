


# code-chill
[![Travis branch](https://img.shields.io/travis/CodeChillAlluna/code-chill/master.svg?style=flat-square)](https://travis-ci.org/CodeChillAlluna/code-chill)  [![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](https://github.com/CodeChillAlluna/code-chill/blob/master/LICENSE)  [![Maintainability](https://api.codeclimate.com/v1/badges/b61e96a6f14db189b5b1/maintainability)](https://codeclimate.com/github/CodeChillAlluna/code-chill/maintainability)  [![Codacy Badge](https://api.codacy.com/project/badge/Grade/3373b12b915d4be68943182e1c2ff979)](https://www.codacy.com/app/Lulu300/code-chill?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=CodeChillAlluna/code-chill&amp;utm_campaign=Badge_Grade)  [![Coverage Status](https://coveralls.io/repos/github/CodeChillAlluna/code-chill/badge.svg?branch=master)](https://coveralls.io/github/CodeChillAlluna/code-chill?branch=master)

Master project : Online development environment.

If you want to know more about this project check our website : https://codechillalluna.github.io/code-chill/


# Summary



* If you want to easily set up our project using our vagrant click [here](#vagrant-installation-guide)  **(Recommended)**



* If you want to install our latest release click [here](#release-installation-guide)



* If you want to set up our project without vagrant click [here](#vagrantless-installation-guide)



# Vagrant installation guide



## Environment installation



### Requirements



* **Vagrant** is needed, you can download it here : https://www.vagrantup.com/downloads.html



* **VirtualBox** needs to be installed. You can download it here : https://www.virtualbox.org/wiki/Downloads

* **Git** If you want to clone our repo instead of downloading a ZIP file. https://git-scm.com/

### Download



Choose either of the solutions:



- Cloning the repository : `git clone https://github.com/CodeChillAlluna/code-chill.git`  **(Recommended)**



- Downloading the repository : `https://github.com/CodeChillAlluna/code-chill/archive/master.zip`





### Setup vagrant



1. Move to the project directory : `cd code-chill` or cd `cd code-chill-master` if you download the project from the ZIP file.



2. Run the command : `vagrant up` (It takes some times, up to 30 minutes).



2. Wait for Vagrant to download all dependencies.



3. Run `vagrant ssh` to connect to the virtual machine.



4. You should be connected to the VM, in `/vagrant` where the project is located otherwise just go to to `cd /vagrant`.



### Common vagrant commands



- Connect to the VM: `vagrant ssh`



- Shutdown the VM: `vagrant halt`



- Launch the VM: `vagrant up`



- Reload the VM: `vagrant reload`



- Delete the VM: `vagrant destroy`



- Verify packages are up to date: `vagrant provision`

### Launch API and Client
The last step is to run the API and the Client. In order to do that you will need to open a second terminal connect to the vagrant `vagrant ssh`. One terminal to run the API and the other one for the Client.
Follow the <a href="#usage">Usage</a> part to run them. If you only want to run the project to try it and you don't plan to install it on a real server, run the API and the Client in Development mode.



# Release installation guide



You can run our releases in our vagrant or install it on your own machine.



You can download our releases <a  href="https://github.com/CodeChillAlluna/code-chill/releases">here</a>



## Install with Vagrant



1. Extract the release in your vagrant folder (You need to setup our vagrant first).



2. Follow <a  href="#vagrant-installation-guide">Vagrant installation guide through Setup Vagrant</a>



3. Launch <a  href="#production-mode">API (Production mode)</a>



4. Launch <a  href="#production-mode-1">Client (Production mode)</a>



## Install without Vagrant



1. Extract the release on your machine.



2. Install all the dependancies (Check `install/install.sh` in our repo to have all dependancies).



3. Launch <a  href="#production-mode">Server</a>



4. Launch <a  href="#production-mode-1">Client</a>




# Vagrantless installation guide



## Environment installation



### Requirements



You will find all our project dependancies in our repo `install/install.sh`



### Download



Choose either of the solutions:



- Cloning the repository : `git clone https://github.com/CodeChillAlluna/code-chill.git`  **(Recommended)**



- Downloading the repository : `https://github.com/CodeChillAlluna/code-chill/archive/master.zip`



- Downloading our release : `https://github.com/CodeChillAlluna/code-chill/releases`





# Usage



## API (Spring)

### Development Mode



To run the API in development mode, you will have to use the following command lines :



1. `cd /vagrant/src/spring` : will place you in the source dictionnary.



2. `sh mvnw spring-boot:run`: will compile the source code and launch the spring server



3. Server API accessible at `http://localhost:8080/`


### Production Mode


To build the API, you will have to use the following command lines :

1. `cd /vagrant/src/spring` : will place you in the source dictionnary.



2. `sh mvnw clean package` : will compile java files to create a runnable jar package.



3. `cd target` : will place you in the build dictionnary of the project.



4. `java -jar spring-0.0.1-SNAPSHOT.jar` : will launch the Spring project, depending on what you are using the version might not always be "0.0.1".



5. Server API accessible at `http://localhost:8080/`

## Client (React)

  ### Development Mode



To run the client in development mode, you will have to use the following command lines :



1. `cd /vagrant/src/client` : will place you in the source dictionnary.



2. `yarn install --no-bin-links` : will install if they are missing and update the dependencies of the project.



3. `yarn start`: will check your code validity and launch the node server.
If you have a problem with xterm :
`cd /vagrant/src/client/node_modules/xterm` and
`npm install --no-bin-links`
After return in the right folder `cd /vagrant/src/client`
and run again `yarn start`.


5. Website accessible at `http://localhost:3000/`

### Production Mode



To build the client, you will have to use the following command lines :



1. `cd /vagrant/src/client` : will place you in the source dictionnary.



2. `yarn install --no-bin-links` : will install if they are missing and update the dependencies of the project.



3. `yarn build` : will build the project.
If you have a problem with xterm :
`cd /vagrant/src/client/node_modules/xterm` and
`npm install --no-bin-links`
After return in the right folder `cd /vagrant/src/client`
and run again `yarn build`.



5. `serve -s build` : will launch the project properly.



6. Website accessible at `http://localhost:5000/`
