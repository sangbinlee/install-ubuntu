# download ubuntu server iso file
  
  https://ubuntu.com/download/server

# download rufus and install
  
  https://rufus.ie/ko/

  ![image](https://github.com/sangbinlee/install-ubuntu/assets/4024414/0637332c-107d-43f7-9eb3-d374c447ef1b)

# Create a bootable USB stick with Rufus on Windows
  
  https://ubuntu.com/tutorials/create-a-usb-stick-on-windows#5-write-the-iso
  
# Install Ubuntu Server

  https://ubuntu.com/tutorials/install-ubuntu-server#3-boot-from-install-media



# check Ubuntu Server version
  
  sangbinlee9@master:~$ uname -a
  Linux master 5.15.0-78-generic #85-Ubuntu SMP Fri Jul 7 15:25:09 UTC 2023 x86_64 x86_64 x86_64 GNU/Linux
  
  sangbinlee9@master:~$ lsb_release -a
  No LSB modules are available.
  Distributor ID: Ubuntu
  Description:    Ubuntu 22.04.2 LTS
  Release:        22.04
  Codename:       jammy



# connect openSSH server
 
  

# check java version


  sangbinlee9@master:~$ java -version
  Command 'java' not found, but can be installed with:
  sudo apt install openjdk-11-jre-headless  # version 11.0.20+8-1ubuntu1~22.04, or
  sudo apt install default-jre              # version 2:1.11-72build2
  sudo apt install openjdk-17-jre-headless  # version 17.0.8+7-1~22.04
  sudo apt install openjdk-18-jre-headless  # version 18.0.2+9-2~22.04
  sudo apt install openjdk-19-jre-headless  # version 19.0.2+7-0ubuntu3~22.04
  sudo apt install openjdk-8-jre-headless   # version 8u382-ga-1~22.04.1

# install jdk 8
  
  sangbinlee9@master:~$ sudo apt install openjdk-8-jre-headless
  [sudo] password for sangbinlee9:


# check java version
  
  sangbinlee9@master:~$ java -version
  openjdk version "1.8.0_382"
  OpenJDK Runtime Environment (build 1.8.0_382-8u382-ga-1~22.04.1-b05)
  OpenJDK 64-Bit Server VM (build 25.382-b05, mixed mode)

# check docker version


# install docker 

  https://docs.docker.com/engine/install/ubuntu/

## Set up the repository  
  sudo apt-get update
  sudo apt-get install ca-certificates curl gnupg
    
  sudo install -m 0755 -d /etc/apt/keyrings
  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
  sudo chmod a+r /etc/apt/keyrings/docker.gpg  


  
  echo \
    "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
    "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
    sudo tee /etc/apt/sources.list.d/docker.list > /dev/null


  sudo apt-get update

## Install Docker Engine
  sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

  sudo docker run hello-world






# oracle

# and reboot

