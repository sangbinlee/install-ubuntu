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





# tomcat  - Working with Docker Images
    
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
    
# Running a Docker Container

    
    sangbinlee9@master:~$ sudo docker ps -a
    CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
    sangbinlee9@master:~$ sudo docker ps -l
    CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
    
        
     
    
    
    sangbinlee9@master:~$ sudo docker ps
    CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
    sangbinlee9@master:~$ sudo docker ps -a
    CONTAINER ID   IMAGE           COMMAND             CREATED         STATUS                        PORTS     NAMES
    a6d5b87e4026   tomcat:latest   "catalina.sh run"   2 minutes ago   Exited (130) 14 seconds ago             beautiful_varahamihira
    sangbinlee9@master:~$ sudo docker ps -l
    CONTAINER ID   IMAGE           COMMAND             CREATED         STATUS                        PORTS     NAMES
    a6d5b87e4026   tomcat:latest   "catalina.sh run"   3 minutes ago   Exited (130) 20 seconds ago             beautiful_varahamihira
    sangbinlee9@master:~$ sudo docker start a6d5b87e4026
    a6d5b87e4026
    sangbinlee9@master:~$ sudo docker ps -l
    CONTAINER ID   IMAGE           COMMAND             CREATED         STATUS         PORTS      NAMES
    a6d5b87e4026   tomcat:latest   "catalina.sh run"   5 minutes ago   Up 4 seconds   8080/tcp   beautiful_varahamihira
    sangbinlee9@master:~$ sudo docker ps -a
    CONTAINER ID   IMAGE           COMMAND             CREATED         STATUS         PORTS      NAMES
    a6d5b87e4026   tomcat:latest   "catalina.sh run"   5 minutes ago   Up 9 seconds   8080/tcp   beautiful_varahamihira
    sangbinlee9@master:~$
    
    
    sangbinlee9@master:~$ sudo docker ps -a
    CONTAINER ID   IMAGE           COMMAND             CREATED          STATUS         PORTS      NAMES
    a6d5b87e4026   tomcat:latest   "catalina.sh run"   13 minutes ago   Up 8 minutes   8080/tcp   beautiful_varahamihira
    sangbinlee9@master:~$ sudo docker stop a6d5b87e4026
    a6d5b87e4026
    sangbinlee9@master:~$ sudo docker ps -a
    CONTAINER ID   IMAGE           COMMAND             CREATED          STATUS                       PORTS     NAMES
    a6d5b87e4026   tomcat:latest   "catalina.sh run"   13 minutes ago   Exited (143) 2 seconds ago             beautiful_varahamihira

    
    sangbinlee9@master:~$ sudo docker ps -a
    CONTAINER ID   IMAGE           COMMAND             CREATED          STATUS                            PORTS     NAMES
    a6d5b87e4026   tomcat:latest   "catalina.sh run"   14 minutes ago   Exited (143) About a minute ago             beautiful_varahamihira
    sangbinlee9@master:~$ sudo docker rm a6d5b87e4026
    a6d5b87e4026
    sangbinlee9@master:~$ sudo docker ps -a
    CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
    sangbinlee9@master:~$


# ufw

    sangbinlee9@master:~$ sudo ufw enable
    sangbinlee9@master:~$ sudo ufw allow 22
    sangbinlee9@master:~$ sudo ufw allow 8080
    sangbinlee9@master:~$ sudo ufw status









# oracle

    docker pull wvbirder/database-enterprise:12.2.0.1-slim




    
    sangbinlee9@master:~$ sudo docker pull wvbirder/database-enterprise:12.2.0.1-slim
    12.2.0.1-slim: Pulling from wvbirder/database-enterprise
    f07cd347d7cc: Pull complete
    e6d45c5d2f56: Pull complete
    0c3e3e3a81c6: Pull complete
    522e6a16038b: Pull complete
    7f4b317ad325: Pull complete
    Digest: sha256:25b0ec7cc3987f86b1e754fc214e7f06761c57bc11910d4be87b0d42ee12d254
    Status: Downloaded newer image for wvbirder/database-enterprise:12.2.0.1-slim
    docker.io/wvbirder/database-enterprise:12.2.0.1-slim
    sangbinlee9@master:~$ sudo docker images
    REPOSITORY                     TAG             IMAGE ID       CREATED        SIZE
    tomcat                         8               511ab3e2b780   9 days ago     426MB
    tomcat                         latest          7ba61facbe26   9 days ago     425MB
    hello-world                    latest          9c7a54a9a43c   3 months ago   13.3kB
    tomcat                         7               9dfd74e6bc2f   2 years ago    533MB
    wvbirder/database-enterprise   12.2.0.1-slim   27c9559d36ec   5 years ago    2.08GB
    
    







    docker run -dit --name local_db -p 1521:1521 wvbirder/database-enterprise:12.2.0.1-slim
    
    sangbinlee9@master:~$ sudo docker run -dit --name local_db -p 1521:1521 wvbirder/database-enterprise:12.2.0.1-slim
    776e2c6bf260447a48a4a4bbdaf3a6be71b70d6ca732ad6b0dc55d42dd942ac7
    sangbinlee9@master:~$



    docker ps -a (정상적으로 프로세스가 떳는지 확인)

    
    sangbinlee9@master:~$ sudo docker ps
    CONTAINER ID   IMAGE                                        COMMAND                  CREATED          STATUS                             PORTS                                                 NAMES
    776e2c6bf260   wvbirder/database-enterprise:12.2.0.1-slim   "/bin/sh -c '/bin/ba…"   49 seconds ago   Up 48 seconds (health: starting)   0.0.0.0:1521->1521/tcp, :::1521->1521/tcp, 5500/tcp   local_db
    



    // Docker 실행 로그를 확인하면서 완료될때 까지 기다린다.
    docker logs -f local_db
    
    
    sangbinlee9@master:~$ sudo docker logs -f local_db
    Setup Oracle Database
    Oracle Database 12.2.0.1 Setup
    Fri Aug 4 17:31:51 UTC 2023
    
    Check parameters ......
    log file is : /home/oracle/setup/log/paramChk.log
    paramChk.sh is done at 0 sec
    
    untar DB bits ......
    log file is : /home/oracle/setup/log/untarDB.log
    untarDB.sh is done at 18 sec
    
    config DB ......
    log file is : /home/oracle/setup/log/configDB.log
    Fri Aug 4 17:32:09 UTC 2023
    Start Docker DB configuration
    Call configDBora.sh to configure database
    Fri Aug 4 17:32:09 UTC 2023
    Configure DB as oracle user
    Setup Database directories ...
    
    SQL*Plus: Release 12.2.0.1.0 Production on Fri Aug 4 17:32:09 2023
    
    Copyright (c) 1982, 2016, Oracle.  All rights reserved.
    
    Connected to an idle instance.
    
    SQL>
    File created.
    
    SQL> ORACLE instance started.
    
    Total System Global Area 1342177280 bytes
    Fixed Size                  8792536 bytes
    Variable Size             352323112 bytes
    Database Buffers          973078528 bytes
    Redo Buffers                7983104 bytes
    Database mounted.
    Database opened.
    SQL>
    Database altered.
    
    SQL>
    NAME                                 TYPE        VALUE
    ------------------------------------ ----------- ------------------------------
    spfile                               string      /u01/app/oracle/product/12.2.0
                                                     /dbhome_1/dbs/spfileORCLCDB.or
                                                     a
    SQL>
    NAME                                 TYPE        VALUE
    ------------------------------------ ----------- ------------------------------
    encrypt_new_tablespaces              string      CLOUD_ONLY
    SQL>
    User altered.
    
    SQL>
    User altered.
    
    SQL> Disconnected from Oracle Database 12c Enterprise Edition Release 12.2.0.1.0 - 64bit Production
    update password
    
    Enter password for SYS:
    create pdb : ORCLPDB1
    
    SQL*Plus: Release 12.2.0.1.0 Production on Fri Aug 4 17:32:20 2023
    
    Copyright (c) 1982, 2016, Oracle.  All rights reserved.
    
    
    Connected to:
    Oracle Database 12c Enterprise Edition Release 12.2.0.1.0 - 64bit Production
    
    SQL>   2    3    4    5
    Pluggable database created.
    
    SQL>
    Pluggable database altered.
    
    SQL>
    Pluggable database altered.
    
    SQL> Disconnected from Oracle Database 12c Enterprise Edition Release 12.2.0.1.0 - 64bit Production
    Reset Database parameters
    
    SQL*Plus: Release 12.2.0.1.0 Production on Fri Aug 4 17:32:34 2023
    
    Copyright (c) 1982, 2016, Oracle.  All rights reserved.
    
    
    Connected to:
    Oracle Database 12c Enterprise Edition Release 12.2.0.1.0 - 64bit Production
    
    SQL>
    System altered.
    
    SQL> Disconnected from Oracle Database 12c Enterprise Edition Release 12.2.0.1.0 - 64bit Production
    
    LSNRCTL for Linux: Version 12.2.0.1.0 - Production on 04-AUG-2023 17:32:34
    
    Copyright (c) 1991, 2016, Oracle.  All rights reserved.
    
    Starting /u01/app/oracle/product/12.2.0/dbhome_1/bin/tnslsnr: please wait...
    
    TNSLSNR for Linux: Version 12.2.0.1.0 - Production
    System parameter file is /u01/app/oracle/product/12.2.0/dbhome_1/admin/ORCLCDB/listener.ora
    Log messages written to /u01/app/oracle/diag/tnslsnr/776e2c6bf260/listener/alert/log.xml
    Listening on: (DESCRIPTION=(ADDRESS=(PROTOCOL=tcp)(HOST=0.0.0.0)(PORT=1521)))
    Listening on: (DESCRIPTION=(ADDRESS=(PROTOCOL=ipc)(KEY=EXTPROC1521)))
    
    Connecting to (DESCRIPTION=(ADDRESS=(PROTOCOL=TCP)(HOST=0.0.0.0)(PORT=1521)))
    STATUS of the LISTENER
    ------------------------
    Alias                     LISTENER
    Version                   TNSLSNR for Linux: Version 12.2.0.1.0 - Production
    Start Date                04-AUG-2023 17:32:34
    Uptime                    0 days 0 hr. 0 min. 0 sec
    Trace Level               off
    Security                  ON: Local OS Authentication
    SNMP                      OFF
    Listener Parameter File   /u01/app/oracle/product/12.2.0/dbhome_1/admin/ORCLCDB/listener.ora
    Listener Log File         /u01/app/oracle/diag/tnslsnr/776e2c6bf260/listener/alert/log.xml
    Listening Endpoints Summary...
      (DESCRIPTION=(ADDRESS=(PROTOCOL=tcp)(HOST=0.0.0.0)(PORT=1521)))
      (DESCRIPTION=(ADDRESS=(PROTOCOL=ipc)(KEY=EXTPROC1521)))
    The listener supports no services
    The command completed successfully
    
    DONE!
    Remove password info
    Docker DB configuration is complete !
    configDB.sh is done at 43 sec
    
    Done ! The database is ready for use .
    # ===========================================================================
    # == Add below entries to your tnsnames.ora to access this database server ==
    # ====================== from external host =================================
    ORCLCDB=(DESCRIPTION=(ADDRESS=(PROTOCOL=TCP)(HOST=<ip-address>)(PORT=<port>))
        (CONNECT_DATA=(SERVER=DEDICATED)(SERVICE_NAME=ORCLCDB.localdomain)))
    ORCLPDB1=(DESCRIPTION=(ADDRESS=(PROTOCOL=TCP)(HOST=<ip-address>)(PORT=<port>))
        (CONNECT_DATA=(SERVER=DEDICATED)(SERVICE_NAME=ORCLPDB1.localdomain)))
    #
    #ip-address : IP address of the host where the container is running.
    #port       : Host Port that is mapped to the port 1521 of the container.
    #
    # The mapped port can be obtained from running "docker port <container-id>"
    # ===========================================================================
    ORCLPDB1(3):Database Characterset for ORCLPDB1 is WE8DEC
    ORCLPDB1(3):Opatch validation is skipped for PDB ORCLPDB1 (con_id=0)
    2023-08-04T17:32:34.398072+00:00
    ORCLPDB1(3):Opening pdb with no Resource Manager plan active
    Pluggable database ORCLPDB1 opened read write
    Completed:     alter pluggable database ORCLPDB1 open
        alter pluggable database all save state
    Completed:     alter pluggable database all save state
    2023-08-04T17:32:34.545695+00:00
    ALTER SYSTEM SET encrypt_new_tablespaces='DDL' SCOPE=BOTH;
    2023-08-04T17:32:49.054076+00:00
    Thread 1 advanced to log sequence 15 (LGWR switch)
      Current log# 3 seq# 15 mem# 0: /u04/app/oracle/redo/redo03.dbf
    2023-08-04T17:33:21.144619+00:00
    TABLE SYS.WRP$_REPORTS: ADDED INTERVAL PARTITION SYS_P1427 (4964) VALUES LESS THAN (TO_DATE(' 2023-08-05 01:00:00', 'SYYYY-MM-DD HH24:MI:SS', 'NLS_CALENDAR=GREGORIAN'))
    TABLE SYS.WRP$_REPORTS_DETAILS: ADDED INTERVAL PARTITION SYS_P1428 (4964) VALUES LESS THAN (TO_DATE(' 2023-08-05 01:00:00', 'SYYYY-MM-DD HH24:MI:SS', 'NLS_CALENDAR=GREGORIAN'))
    TABLE SYS.WRP$_REPORTS_TIME_BANDS: ADDED INTERVAL PARTITION SYS_P1431 (4963) VALUES LESS THAN (TO_DATE(' 2023-08-04 01:00:00', 'SYYYY-MM-DD HH24:MI:SS', 'NLS_CALENDAR=GREGORIAN'))
    





 



    docker exec -it local_db bash -c "source /home/oracle/.bashrc; sqlplus sys/Oradoc_db1@ORCLCDB as sysdba"
    
    
    sangbinlee9@master:~$ sudo  docker exec -it local_db bash -c "source /home/oracle/.bashrc; sqlplus sys/Oradoc_db1@ORCLCDB as sysdba"
    [sudo] password for sangbinlee9:
    
    SQL*Plus: Release 12.2.0.1.0 Production on Fri Aug 4 17:36:29 2023
    
    Copyright (c) 1982, 2016, Oracle.  All rights reserved.
    
    
    Connected to:
    Oracle Database 12c Enterprise Edition Release 12.2.0.1.0 - 64bit Production
    
    SQL> alter session set "_ORACLE_SCRIPT"=true;
    
    Session altered.
    
    SQL> create user test identified by test;
    
    User created.
    
    SQL> grant connect, resource, dba to test;
    
    Grant succeeded.
    
    SQL> update sys.props$ set value$='KOREAN_KOREA.UTF8' where name='NLS_LANGUAGE';
    
    1 row updated.
    
    SQL> update sys.props$ set value$='UTF8' where name='NLS_CHARACTERSET';
    
    1 row updated.
    
    SQL> update sys.props$ set value$='UTF8' where name='NLS_NCHAR_CHARACTERSET';
    
    1 row updated.
    
    SQL> commit;
    
    Commit complete.
     
    SQL> shutdown immediate;
    Database closed.
    Database dismounted.
    ORACLE instance shut down.
    ERROR:
    ORA-12514: TNS:listener does not currently know of service requested in connect
    descriptor
    
    
    Warning: You are no longer connected to ORACLE.
    SQL> conn /as sysdba
    Connected to an idle instance.
    SQL> startup;
    
    ORACLE instance started.
    
    Total System Global Area 1342177280 bytes
    Fixed Size                  8792536 bytes
    Variable Size             369100328 bytes
    Database Buffers          956301312 bytes
    Redo Buffers                7983104 bytes
    Database mounted.
    Database opened.
    SQL> SQL>
    
    
    
![image](https://github.com/sangbinlee/install-ubuntu/assets/4024414/a9f92652-f350-4db7-a2a7-5205099edacd)









    
    sangbinlee9@master:~$ sudo docker exec -it local\_db bash -c "cat /home/oracle/.bashrc"
    [sudo] password for sangbinlee9:
    # .bashrc
    
    # Source global definitions
    if [ -f /etc/bashrc ]; then
            . /etc/bashrc
    fi
    
    # Uncomment the following line if you don't like systemctl's auto-paging feature:
    # export SYSTEMD_PAGER=
    
    # User specific aliases and functions
    export ORACLE_HOME=/u01/app/oracle/product/12.2.0/dbhome_1
    export OH=/u01/app/oracle/product/12.2.0/dbhome_1
    export PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/u01/app/oracle/product/12.2.0/dbhome_1/bin
    export TNS_ADMIN=/u01/app/oracle/product/12.2.0/dbhome_1/admin/ORCLCDB
    export ORACLE_SID=ORCLCDB;
    sangbinlee9@master:~$ sudo docker exec -it local\_db bash -c "echo \\"export TZ='Asia/Seoul'\\" >> /home/oracle/.bashrc"
    export
    sangbinlee9@master:~$ sudo docker exec -it local\_db bash -c "cat /home/oracle/.bashrc"
    
    
    
    














    
# SQL Developer 23.1
    https://www.oracle.com/database/sqldeveloper/technologies/download/

# data import , restore






# deploy 

