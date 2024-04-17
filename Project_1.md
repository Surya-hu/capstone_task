## Final Project Submission (Capstone)

Using the below commands cloned the repo from the documentation provided.  
Git clone https://github.com/sriram-R-krishnan/devops-build  
git init  
git add .  
git commit -m "capstone"  
git remote add origin https://github.com/Surya-hu/capstone_1.git  
git branch -M main  
git push -u origin main  
GITrepo URL: https://github.com/Surya-hu/capstone_1  

Created EC2 instance and installed docker using below commands 

![image](https://github.com/Surya-hu/capstone_task/assets/119995742/3378b034-85ec-48d7-a683-2220ec37bb71)

SG group has more ports other than 80 to use prometheus, grafana and jenkins. 

![image](https://github.com/Surya-hu/capstone_task/assets/119995742/d3fdb962-b528-4877-8ee7-f592bca0f872)


sudo apt update  
sudo apt install docker.io  
docker --version  

Docker file created to build the docker image  

![image](https://github.com/Surya-hu/capstone_task/assets/119995742/76e3438b-d8c4-41b7-ac7f-829020c32f0b)


Docker successfully created and running as shown below  

![image](https://github.com/Surya-hu/capstone_task/assets/119995742/9da9fec4-1974-4bea-bb4d-6bf9ed310c77)

Verified the same with public ip and found it working fine  

![image](https://github.com/Surya-hu/capstone_task/assets/119995742/b29013fc-7c62-4635-981c-fa9bfcf6daa0)

Installed docker-compose using docker documentation and successfully installed  

![image](https://github.com/Surya-hu/capstone_task/assets/119995742/c61db8d4-3982-4294-b4c7-b4506bc66d29)

Docker-compose file  

![image](https://github.com/Surya-hu/capstone_task/assets/119995742/efbc8364-a9c1-46b0-bf72-1b6cb413c473)



Using docker-compose deployed the another container with port:80 and running successful as shown below  

![image](https://github.com/Surya-hu/capstone_task/assets/119995742/8b13a815-99c2-4793-8125-9a3ea73219a7)



Creating build.sh file for building docker image and run it using docker file and docker-compose.  

![image](https://github.com/Surya-hu/capstone_task/assets/119995742/7caa5bd4-3b51-4ac8-93c4-3aa48bc19553)


Before creating deploy.sh file created docker hub reposs one for Dev and another one for prod(private).  

![image](https://github.com/Surya-hu/capstone_task/assets/119995742/02f99a18-128a-4121-94e6-722b6e0a529e)

Created deploy.sh file as shown below:  

![image](https://github.com/Surya-hu/capstone_task/assets/119995742/91ddffd0-c4f1-444e-b0c4-5805850f0131)


Jenkins installaion:  

Installed Java  
`sudo apt update
sudo apt install fontconfig openjdk-17-jre
java -version
openjdk version "17.0.8" 2023-07-18
OpenJDK Runtime Environment (build 17.0.8+7-Debian-1deb12u1)
OpenJDK 64-Bit Server VM (build 17.0.8+7-Debian-1deb12u1, mixed mode, sharing)`

Then installed jenkins:  
`sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins`

![image](https://github.com/Surya-hu/capstone_task/assets/119995742/2e33634b-64ea-4cb9-aee3-475aea1d6883)


Created Jenkinsfile:  
This file will use build.sh and deploy.sh files to deploy and run the application


![image](https://github.com/Surya-hu/capstone_task/assets/119995742/9113687d-caee-401b-9c83-68dd4373333c)

Given jenkins user previllage to ubuntu user using `sudo usermod -aG jenkins ubuntu`  

Then created pipline in jenkins using below procedure.

1. Add new Item
2. Entered the name fo the pipline as capstone_dev and capstone_prod
3. In general tab selected GitHub project
4. In buil triggers selected GitHub hook trigger for GITScm polling
5. In pipline tab selceted pipeline script from SCM
6. Then added Git and Git repo link over here.
7. Apply and Save.

![image](https://github.com/Surya-hu/capstone_task/assets/119995742/e99f00e7-2eee-41ab-8215-75f130808140)


![image](https://github.com/Surya-hu/capstone_task/assets/119995742/37b88eac-6092-4379-8338-33158f74f1f5)


![image](https://github.com/Surya-hu/capstone_task/assets/119995742/9430db83-c060-405b-b3e7-9546a9680229)


![image](https://github.com/Surya-hu/capstone_task/assets/119995742/02005862-f8b8-4b39-8290-585c03499ef6)


![image](https://github.com/Surya-hu/capstone_task/assets/119995742/7fdc9958-cade-4e0e-b101-c069d369ed28)


Commenced build in jenkins to verify if the build gets successfull.

As expected build was successfull, Application deployed with port 80 as shown below and docker image has been pushed to relevant branch repo.

![image](https://github.com/Surya-hu/capstone_task/assets/119995742/90e44790-5f83-4e3e-a715-862ab9ef5322)
 

Docker images pushed accoring to the branch:  

![image](https://github.com/Surya-hu/capstone_task/assets/119995742/8587ff03-bfe5-4788-9157-ec97fcea0c70)

![image](https://github.com/Surya-hu/capstone_task/assets/119995742/e6b2ef38-a61a-41d7-a63a-fd39d0a01e60)

![image](https://github.com/Surya-hu/capstone_task/assets/119995742/54b4db3a-c959-4159-9bd2-058af1f27a5f)


Installed grafana and prometheus using official pages as shown below. and configured dashboard for monitoring up and cpu usage.


![image](https://github.com/Surya-hu/capstone_task/assets/119995742/7c269045-269c-4ecc-81ed-48bf4cb5e192)


![image](https://github.com/Surya-hu/capstone_task/assets/119995742/8c1f6ae5-ffa9-4bfb-b784-427adfad3215)  


Configure the Email notification alert if the application server gets down:

Step 1:  Configured cloudwatch alarm  
step 2:  Created alarm with metric `StatusCheckFailed_Instance`  

![image](https://github.com/Surya-hu/capstone_task/assets/119995742/6c06ad61-b2e4-4434-bd9b-d0a4b14c036f)

step 3:  Created topic in amazon SNS and configured with my gmail ID  

step 4:  Once the alarm state `OK` as shown below  

![image](https://github.com/Surya-hu/capstone_task/assets/119995742/cb5de088-d719-4f62-91d5-165a9593f852)

And finally we have successfully received a notification stating that the instance is down  

![image](https://github.com/Surya-hu/capstone_task/assets/119995742/8926ee3e-2c06-4177-9eb4-042518eadbfb)







