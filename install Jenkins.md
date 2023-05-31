# INSTALL AND CONFIGURE JENKINS SERVER

Step 1 – Install Jenkins server

1. Create an AWS EC2 server based on Ubuntu Server 20.04 LTS and name it "Jenkins"

2. Install JDK (since Jenkins is a Java-based application)

```
sudo apt update
sudo apt install default-jdk-headless
```

3. Install Jenkins
```
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
```
```
sudo sh -c 'echo deb https://pkg.jenkins.io/debian-stable binary/ > \
    /etc/apt/sources.list.d/jenkins.list'
```

```
sudo apt update
sudo apt-get install jenkins
```
4- Add the port the port range 8080 on EC2 inbound.
Make sure Jenkins is up and running

```
sudo systemctl status jenkins
```


Just in case you have this error 
![jenkins_not_active](https://github.com/Tyannherve11/Jenkins-CI/assets/37128739/89b63d86-ad7b-4c6c-8e19-6240e0d37a14)

here are the commands
- install the firewalld service

```
sudo yum install -y firewalld
sudo systemctl start firewalld 
```

If your install is correct this is the result

![jenkins running](https://github.com/Tyannherve11/Jenkins-CI/assets/37128739/f69e5189-f1bb-48ec-b440-ed29a1bbc101)

5. Perform initial Jenkins setup.
From your browser access http://<Jenkins-Server-Public-IP-Address-or-Public-DNS-Name>:8080

You will be prompted to provide a default admin password

  
![6013](https://user-images.githubusercontent.com/85270361/210151821-9b9baaf6-e89c-4a9b-b06a-c2c1d6e01930.PNG)

  
Retrieve it from your server:
  
```
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```
  
Then you will be asked which plugings to install – choose suggested plugins.
 

![6014](https://user-images.githubusercontent.com/85270361/210151862-fee4be20-f6b3-4c3b-9830-78ce4a28253b.PNG)

  
Once plugins installation is done – create an admin user and you will get your Jenkins server address.

The installation is completed!
