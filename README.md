# blockchain-hyperledger fabric installation on Azure

Develop consortium Hyperledger fabric and deploy on Microsft Azure


### Prerequisites

### Build a fabric network from scratch

• Ubuntu 16.04 VM (you can also use Mac)
• Pre-requisites:
– Docker - v1.13 or higher
– Docker Compose - v1.8 or higher
– Node.js & npm - node v6.2.0 - v6.10.0 (v7+ not supported); npm comes with
your node installation.
– Git client - needed for clone commands
– Go - version 1.9.x

### Step-1- Choose Ubuntu Server
 ![Choose Server](https://github.com/asifwaquar/images/blob/master/images/azure.png)


### Step-2 Create VM
  ![Crete VM](https://github.com/asifwaquar/images/blob/master/images/config1.png)
  ![Crete VM](https://github.com/asifwaquar/images/blob/master/images/config2.png)

### Step-3

Downlod Hyperledger Composer and provide permission
curl -O https://hyperledger.github.io/composer/v0.19/prereqs-ubuntu.sh
chmod u+x prereqs-ubuntu.sh

Execute below script after that
./prereqs-ubuntu.sh
Step 3 — Install Go Language
sudo apt-get update
sudo apt-get -y upgrade
Step 4- Now download GO binaries
cd /tmp
wget https://dl.google.com/go/go1.11.linux-amd64.tar.gz

Step-5 Install GO Code and move to desired location
sudo tar -xvf go1.11.linux-amd64.tar.gz
sudo mv go /usr/local

Step-5 Setup GO Root
export GOROOT=/usr/local/go
export GOPATH=$HOME/go
export PATH=$GOPATH/bin:$GOROOT/bin:$PATH

Step-6 Update current shell session 
source ~/.profile

Step-7 Verify Installation
go version
go env

Step-8
Clone code to your home directory to setup network and install chain code
git clone -b master https://github.com/asifwaquar/blockchain-architecture.git
cd Start/fabric-code
git checkout 1.4.1


Download platform binaries 

	curl -sSL https://goo.gl/6wtTN5 | bash -s 1.4.1 1.4.1 0.4.6

 Export path

	export PATH=<path to download location>/bin:$PATH

 Step-9

  Install network 

	cd fabric-code/first-network

    


 Step-10

	Generate Certificates

./byfn.sh -m generate

Step-11

Bring network Up


	./byfn.sh -m up

 
Results

Starting with channel 'mychannel' and CLI timeout of '10'
Continue? [Y/n]
proceeding ...
Creating network "net_byfn" with the default driver
Creating peer0.org1.example.com
Creating peer1.org1.example.com
Creating peer0.org2.example.com
Creating orderer.example.com
Creating peer1.org2.example.com
Creating cli


 ____    _____      _      ____    _____
/ ___|  |_   _|    / \    |  _ \  |_   _|
\___ \    | |     / _ \   | |_) |   | |
 ___) |   | |    / ___ \  |  _ <    | |
|____/    |_|   /_/   \_\ |_| \_\   |_|

Channel name : mychannel
Creating channel...
Query Result: 90
2017-05-16 17:08:15.158 UTC [main] main -> INFO 008 Exiting.....
===================== Query on peer1.org2 on channel 'mychannel' is successful =====================

===================== All GOOD, BYFN execution completed =====================


 _____   _   _   ____
| ____| | \ | | |  _ \
|  _|   |  \| | | | | |
| |___  | |\  | | |_| |
|_____| |_| \_| |____/




