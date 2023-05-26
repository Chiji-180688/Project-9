	# PROJECT-9 DOCUMENTATION

Step1: Installing and Configuring Jenkins Server
1. An Ubuntu based aws ec2 server was created and named Jenkins
2. Jdk was installed
`sudo apt update`
`sudo apt install default-jdk-headless`
![jdk installed](./Project-9%20Images/jdk%20installed.png)
3. Jenkins was installed
`curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins`
![jenkins installed](./Project-9%20Images/jnkns%20installed-main.png)
4. Confirming Jenkins status
`sudo systemctl status jenkins`
![jenkins active](./Project-9%20Images/jnkns%20active%20and%20running.png)
5. Opening port 8080
![port 8080 opened](./Project-9%20Images/port%208080%20opened.png)
6. Performing initial Jenkins setup
[Jenkins url](http://184.73.65.3:8080)
![unlocking jenkins](./Project-9%20Images/unlocking%20jnkns.png)
`sudo cat /var/lib/jenkins/secrets/initialAdminPassword`
![jenkins key](./Project-9%20Images/jnkns%20key.png)
7. Installing Plugins
![jenkins plugins](./Project-9%20Images/jnkns%20plugins.png)
![getting started](./Project-9%20Images/getting%20started%20with%20jnkns.png)
![jenkins ready](./Project-9%20Images/jnkns%20is%20ready.png)
![jenkins dashboard](./Project-9%20Images/jnkns%20dashboard.png)

Step2: Configuring Jenkins to retrieve source codes from github using webhooks
1. Enabling webhooks in my github repository settings
![webhook enabled](./Project-9%20Images/webhook%20added.png)
2. Creating a freestyle project
![freestyle project](./Project-9%20Images/freestyle%20project%20created.png)
3. Connecting to github using it's url
4. Configuring jenkins freestyle project
5. Running build
![build success](./Project-9%20Images/build%20success.png)
![console ouput](./Project-9%20Images/build%20success2.png)
6. Configuring automatic build by enabling triggering job from github webhook and post build actions
![updating readme.md](./Project-9%20Images/readme1.png)
![build2](./Project-9%20Images/confirmatory%20build%20success.png)
![build2](./Project-9%20Images/confirmatory%20build%20success2.png)
![console output for build2](./Project-9%20Images/confirmatory%20build%20successful2.png)
7. Confirming that artifacts are stored in jenkins local server
![confirmation](./Project-9%20Images/server%20confirmation.png)
![confirmation2](./Project-9%20Images/server%20confirmation2.png)
![confirmation](./Project-9%20Images/server%20confirmation3.png)

Step3: Configuring Jenkins to copy files to NFS server via SSH
1. Installing publish over ssh
![publish over ssh](./Project-9%20Images/publish%20over%20ssh%20plugin%20installed.png)
2. Configuring project to copy artifacts over to nfs server 
![configuration](./Project-9%20Images/private%20key.png)
![configuration2](./Project-9%20Images/configuring%20job%20to%20copy%20to%20nfs.png)
3. Updating README.md
![updating readme.md](./Project-9%20Images/readme2.png)
4. Confirming automatic build
![console output](./Project-9%20Images/git%20automation%20successful.png)
5. Checking README.md file on nfs server
`cat /mnt/apps/README.md`
![nfs file updated](./Project-9%20Images/nfs%20files%20successfully%20updated.png)
