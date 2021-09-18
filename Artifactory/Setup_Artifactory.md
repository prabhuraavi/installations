# Artifacotry Setup
An artifact repository manages your end-to-end artifact lifecycle and supports different software package management systems while providing consistency to your CI/CD workflow. An artifact repository is both a source for artifacts needed for a build and a target to deploy artifacts generated in the build process.

JFrog Artifactory is a universal DevOps solution providing end-to-end automation and management of binaries and artifacts through the application delivery process that improves productivity across your development ecosystem. It enables freedom of choice supporting 25+ software build packages, all major CI/CD platforms, and DevOps tools you already use.

## Pre-requisites: 
1. An AWS T2.small EC2 instance (Linux)
1. Open port 8081 and 8082 in the security group



first you need to install any one db 

mariadb installation procedure fallow below url:


https ://mariadb.com/resources/blog/installing-mariadb-10-on-centos-7-rhel-7/


step1 :- Installing MariaDB Server

  $ sudo yum install mariadb-server

step2 :- Installing MariaDB Server 10.4
To deploy MariaDB Community Server 10.4 on RHEL 7 or CentOS 7, first download and use the mariadb_repo_setup script to configure the MariaDB repositories for YUM:



$ sudo yum install wget
$ wget https://downloads.mariadb.com/MariaDB/mariadb_repo_setup
$ chmod +x mariadb_repo_setup
$ sudo ./mariadb_repo_setup


step3 :- To install MariaDB Community Server and dependencies

$ sudo yum install MariaDB-server

step4 :- Configuring and Securing MariaDB Server

$ sudo systemctl start mariadb.service

step5 :- Specific security practices should always follow any business-specific requirements and governance. Some basic steps should be taken to help harden the MariaDB Community Server 5.5 or 10.4 deployment:

$ sudo mysql_secure_installation


* add a user name it as jfrog
  adduser jfrog

* create a password for sonar
  passwd jfrog

enter password and confirm it (as usual give it as root)


* now switch to sonar user by using 
su jfrog

cd /home/frog/


## Installation Steps 

1. Login to instance as a `root` user and install Java
   ```sh 
    yum install java-1.8* -y 
   ```
1. Download Artifactory packages onto /opt/   
   For Latest version of Artifactory OSS [download it from here](https://jfrog.com/open-source/)   
For Older version of Artifactory OSS [download it from here](https://jfrog.bintray.com/artifactory/)   
For Latest version of Artifactory Pro [download it from here](https://jfrog.com/artifactory/)

   ```sh 
   cd /opt 
   wget https://jfrog.bintray.com/artifactory/jfrog-artifactory-oss-6.9.6.zip
   ```

1. extract artifactory tar.gz file
   ```sh
   unzip jfrog-artifactory-oss-6.9.6.zip
   ```
1. Go inside to bin directory and start the services
   ```sh
   cd /opt/jfrog-artifactory-oss-6.9.6/bin
   ./artifactory.sh start
   ```
1. access artifactory from browser
   ```sh
   http://<PUBLIC_IP_Address>:8081 
   ```

1. Provide credentials 
   ```sh 
   username: admin
   password: passwrod 
   ```

## Not able to start Artifactory services?
 Make sure You meet the Artifactory [system requirements](https://www.jfrog.com/confluence/display/JFROG/System+Requirements)

---
---

### Integrate Artifactory with Jenkins [Click here](https://youtu.be/BVxhLIfunmI)
### Integrate Artifactory with Maven [Yet to release]()
### How to install Maven on EC2 instance [Click here](https://youtu.be/wgfsVmHnAiM)
### How to install Jenkins on EC2 instance [Click here](https://youtu.be/M32O4Yv0ANc)
