# CI-CD-Pipeline

Jenkins CI/CD Training :

Break 1 : 11:30 to 11:45

Break 2 : 1:30 to 2:30

Break 3 : 3:45 to 4:00

Create a ec2-instance in AWS :

1. Ubuntu - 22.04


2. keypair - .pem format


3. instance size - t2.micro/t2.medium


4. storage - 10 gb


5. VPC and sg - default


6. Launch instance ...
Jenkins - CI/CD

DevOps - developer + ops

Tools in devops - git , github ... docker (containers)

              k8 - nodes , tf - IaC , ansible - Config mgmt, 
jenkins ci-cd -- alternatives - azure devops (managed by azure)

jenkins is independent of cloud

jenkins server - UI (scripts - groovy )

ci-cd >> code(github) + sq + junit + build tools (docker)

automation pipeline - cron jobs, triggers

IaaS - azure admins (more config and more control)

PaaS - developers (less config and less control - more user friendly)

SaaS - end-users (very less confg and low control)

private cloud - syncehron - central LMS

restriction - url (security)

authentication (MFA) + authorizaton - Active Directory

accessing from untrusted device (fingerprint + auth. app code )

on-premises (private cloud)

public cloud but if it share only 50% of data on cloud (aws)

Covid - 19 , antidote (sharing their research via community cloud)

VM - ip address required to SSH and log into machine

EC2 - ECC - elastic compute cloud - modify 2 GB to 4 GB RAM and any compute power

        offers elasticity in compute (instance size)
SSH - linux (22) and RDP - windows (3389)

ipadress and username- key pair

cd downloads ..

ssh -i key-pair username@public-ip

commands :

whoami

cat /etc/os-release

sudo hostnamectl set-hostname jenkins

Installation of jenkins --

Link -- https://www.jenkins.io/doc/book/installing/linux/#debianubuntu

Steps - 1. Download latest openjdk -

sudo apt update sudo apt install fontconfig openjdk-17-jre java -version

   2. Install jenkins - 
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc
https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]"
https://pkg.jenkins.io/debian-stable binary/ | sudo tee
/etc/apt/sources.list.d/jenkins.list > /dev/null sudo apt-get update sudo apt-get install jenkins

   3. Check jenkins status -


sudo systemctl status jenkins ....



   4. Go to http://public-ip:8080
            
            
            
      sudo -i
            
            
      copy the path of pswd and use "cat" command with path to get pswd
    
    
      paste the pswd and follow instructions
        
        
        
    5. you will get jenkins dashboard ...
To Create jenkins CI/CD pipeline :

1. Make sure jenkins is installed on VM, up and running

2. Make sure Docker is installed on VM, up and running

3. Fork this repo..   https://github.com/ajit010/ci-cd-pipeline.git
    
4. Use this command in VM -- sudo usermod -aG docker jenkins

  (to give jenkins full access on docker)
    
5. After this, restart jenkins using cmd - sudo systemctl restart jenkins
    
6. Install  Git Plugins and Docker Pipeline Plugin
    
    
7. Create a New item - Pipeline

   Under Pipeline section - select pipeline from SCM -- use your forker repo URL
    
    
8. Save and apply ... Click on Build Now ..


9. Add webhook trigger in github 
    
    http://18.234.36.131:8080/github-webhook/
