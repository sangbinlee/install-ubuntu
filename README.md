# download ubuntu server iso file
  
    https://ubuntu.com/download/server

# download rufus and install
  
    https://rufus.ie/ko/

    ![image](https://github.com/sangbinlee/install-ubuntu/assets/4024414/0637332c-107d-43f7-9eb3-d374c447ef1b)

# Create a bootable USB stick with Rufus on Windows
  
    https://ubuntu.com/tutorials/create-a-usb-stick-on-windows#5-write-the-iso
  
# Install Ubuntu Server

    https://ubuntu.com/tutorials/install-ubuntu-server#3-boot-from-install-media

    https://ubuntu.com/server/docs/install/step-by-step

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



# reboot now


# history
  
    
    sangbinlee9@master:~$ history
        1  java -version
        2  sudo apt install openjdk-8-jre-headless
        3  java -version
        4  docker -version
        5  uname -a
        6  lsb_release -a
        7  sudo apt-get update
        8  sudo apt-get install ca-certificates curl gnupg
        9  sudo install -m 0755 -d /etc/apt/keyrings
       10  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
       11  sudo chmod a+r /etc/apt/keyrings/docker.gpg
       12  echo   "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
       13    "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" |   sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
       14  sudo apt-get update
       15  sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
       16  sudo docker run hello-world
       17  reboot now
       18  sudo reboot now
       19  history
       20  sudo docker run hello-world
       21  history



# docker status

    
    sangbinlee9@master:~$ sudo systemctl status docker
    [sudo] password for sangbinlee9:
    ● docker.service - Docker Application Container Engine
         Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled)
         Active: active (running) since Fri 2023-08-04 14:14:46 UTC; 47min ago
    TriggeredBy: ● docker.socket
           Docs: https://docs.docker.com
       Main PID: 774 (dockerd)
          Tasks: 11
         Memory: 100.4M
            CPU: 1.144s
         CGroup: /system.slice/docker.service
                 └─774 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock
    
    Aug 04 14:14:45 master dockerd[774]: time="2023-08-04T14:14:45.807090537Z" level=info msg="detected 127.0.0.53 nameserver, assuming systemd-resolved, so using resolv.conf: /run/systemd/resolve/resolv.conf"
    Aug 04 14:14:45 master dockerd[774]: time="2023-08-04T14:14:45.912733667Z" level=info msg="[graphdriver] using prior storage driver: overlay2"
    Aug 04 14:14:45 master dockerd[774]: time="2023-08-04T14:14:45.916673794Z" level=info msg="Loading containers: start."
    Aug 04 14:14:46 master dockerd[774]: time="2023-08-04T14:14:46.344812557Z" level=info msg="Default bridge (docker0) is assigned with an IP address 172.17.0.0/16. Daemon option --bip can be used to set a pr>
    Aug 04 14:14:46 master dockerd[774]: time="2023-08-04T14:14:46.390936064Z" level=info msg="Loading containers: done."
    Aug 04 14:14:46 master dockerd[774]: time="2023-08-04T14:14:46.441182778Z" level=info msg="Docker daemon" commit=a61e2b4 graphdriver=overlay2 version=24.0.5
    Aug 04 14:14:46 master dockerd[774]: time="2023-08-04T14:14:46.441433515Z" level=info msg="Daemon has completed initialization"
    Aug 04 14:14:46 master systemd[1]: Started Docker Application Container Engine.
    Aug 04 14:14:46 master dockerd[774]: time="2023-08-04T14:14:46.474173161Z" level=info msg="API listen on /run/docker.sock"
    Aug 04 14:23:13 master dockerd[774]: time="2023-08-04T14:23:13.697530209Z" level=info msg="ignoring event" container=6503ce28c1a90958777dc42b4d129b5890a685c4165d0803e6ccc17f523b6aa2 module=libcontainerd na>
    lines 1-22/22 (END)





# tomcat
    
    sangbinlee9@master:~$ sudo docker run -d --name="tomcat-test" -p 8080:8080 tomcat:8
    Unable to find image 'tomcat:8' locally
    8: Pulling from library/tomcat
    9d19ee268e0d: Pull complete
    f2b566cb887b: Pull complete
    2699dbfb6757: Pull complete
    38ab1613eab3: Pull complete
    1d4c657a9280: Pull complete
    0a66037568bd: Pull complete
    75da0ea6a69f: Pull complete
    Digest: sha256:c4f7458a0b96c12b86acabd29f61cff9bc13f14cd61b3841a41ad40fd4c3de4a
    Status: Downloaded newer image for tomcat:8
    3a3680399a002933d6affff7d4af548bd900e8022fe600b189692f4001176e38

    
        
    sangbinlee9@master:~$ sudo docker ps
    CONTAINER ID   IMAGE      COMMAND             CREATED         STATUS         PORTS                                       NAMES
    3a3680399a00   tomcat:8   "catalina.sh run"   9 minutes ago   Up 9 minutes   0.0.0.0:8080->8080/tcp, :::8080->8080/tcp   tomcat-test
    

    
    
    sangbinlee9@master:~$ sudo docker search tomcat
    NAME                          DESCRIPTION                                     STARS     OFFICIAL   AUTOMATED
    tomcat                        Apache Tomcat is an open source implementati…   3573      [OK]
    tomee                         Apache TomEE is an all-Apache Java EE certif…   109       [OK]
    bitnami/tomcat                Bitnami Tomcat Docker Image                     49                   [OK]
    bitnamicharts/tomcat                                                          0
    secoresearch/tomcat-varnish   Tomcat and Varnish 5.0                          0                    [OK]
    vulhub/tomcat                                                                 0
    islandora/tomcat                                                              0
    wnprcehr/tomcat                                                               0
    hivdb/tomcat-with-nucamino                                                    0
    jumpserver/tomcat                                                             0
    sismics/tomcat                Apache Tomcat Servlet Container                 1
    eclipse/rdf4j-workbench       Dockerfile for Eclipse RDF4J Server and Work…   6
    semoss/docker-tomcat          Tomcat, Java, Maven, and Git on top of debian   0                    [OK]
    eclipse/hadoop-dev            Ubuntu 14.04, Maven 3.3.9, JDK8, Tomcat 8       0                    [OK]
    gbif/ipt                      The GBIF Integrated Publishing Toolkit (IPT)…   0
    dhis2/base-dev                Images in this repository contains DHIS2 WAR…   0
    eclipse/alpine_jdk8           Based on Alpine 3.3. JDK 1.8, Maven 3.3.9, T…   1                    [OK]
    misolims/miso-base            MySQL 5.7 Database and Tomcat 8 Server neede…   0
    dhis2/base                    Images in this repository contains DHIS2 WAR…   0
    jelastic/tomcat               An image of the Tomcat Java application serv…   4
    cfje/tomcat-resource          Tomcat Concourse Resource                       2
    rightctrl/tomcat              CentOS , Oracle Java, tomcat application ssl…   7                    [OK]
    amd64/tomcat                  Apache Tomcat is an open source implementati…   6
    arm64v8/tomcat                Apache Tomcat is an open source implementati…   8
    softwareplant/tomcat          Tomcat images for jira-cloud testing            0                    [OK]

    
    
    
    sangbinlee9@master:~$ sudo docker pull tomcat
    Using default tag: latest
    latest: Pulling from library/tomcat
    9d19ee268e0d: Already exists
    f2b566cb887b: Already exists
    2699dbfb6757: Already exists
    38ab1613eab3: Already exists
    1d4c657a9280: Already exists
    9f132165bd73: Pull complete
    e647b8ebf378: Pull complete
    Digest: sha256:7af5900fcc06062d767a80c834c0933be355727376faad61ceabfea91fa2b4f1
    Status: Downloaded newer image for tomcat:latest
    docker.io/library/tomcat:latest
    sangbinlee9@master:~$


    sangbinlee9@master:~$ sudo docker images
    REPOSITORY    TAG       IMAGE ID       CREATED        SIZE
    tomcat        8         511ab3e2b780   9 days ago     426MB
    tomcat        latest    7ba61facbe26   9 days ago     425MB
    hello-world   latest    9c7a54a9a43c   3 months ago   13.3kB
    tomcat        7         9dfd74e6bc2f   2 years ago    533MB
    

    

# ufw

    sangbinlee9@master:~$ sudo ufw enable
    sangbinlee9@master:~$ sudo ufw allow 22
    sangbinlee9@master:~$ sudo ufw allow 8080
    sangbinlee9@master:~$ sudo ufw status









# oracle




# data import , restore






# deploy 

