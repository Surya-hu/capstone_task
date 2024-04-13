## Final Project Submission (Capstone)

Using the below commands cloned the repo from the documentation provided.
git add .
git commit -m "capstone"
git remote add origin https://github.com/Surya-hu/capstone.git
git branch -M main
git push -u origin main

Created EC2 instance and installed docker using below commands  
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

![image](https://github.com/Surya-hu/capstone_task/assets/119995742/e23443a8-6ed6-440d-aec6-d4feb33a4981)


Using docker-compose deployed the another container with port:3000 and running successful as shown below  

![image](https://github.com/Surya-hu/capstone_task/assets/119995742/b3d09dee-7850-4d11-bbb8-a3316669b5a1)


Creating build.sh file for building docker image and run it using docker file and docker-compose.  

![image](https://github.com/Surya-hu/capstone_task/assets/119995742/b866bb39-3b38-4994-8664-c758f3901da7)

Before creating deploy.sh file created docker hub reposs one for Dev and another one for prod(private).  

![image](https://github.com/Surya-hu/capstone_task/assets/119995742/02f99a18-128a-4121-94e6-722b6e0a529e)

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

![image](https://github.com/Surya-hu/capstone_task/assets/119995742/b06954f8-3d17-4e7d-b78d-72710198067f)

Created Jenkinsfile:  
This file will use build.sh and deploy.sh files to deploy and run the application


![image](https://github.com/Surya-hu/capstone_task/assets/119995742/9113687d-caee-401b-9c83-68dd4373333c)

Given jenkins user previllage to ubuntu user using `sudo usermod -aG jenkins ubuntu`  

Then created pipline in jenkins using below procedure.

1. Add new Item
2. Entered the name fo the pipline as capstone_dev and capstone_prod
3. In general tab selected GitHub project
4. In buil triggers selected GitHub hook trigger for GITScm polling
5. 
6. 


