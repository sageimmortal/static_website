# Tier 3 Exam
## Deploying Azure VM
1. Go to the portal.azure.com and login the using the given credentials.
2. Go to the Virtual Machine and create VM using an Ubuntu OS
3. rename your resource groups and VM and allow the public access in port 22 and 443
4. create new Key Pair
5. Leave everything as a default and proceed to create your VM
6. Download the key pair that was use to create the VM

## Accessing the VM and installing Git and Ansible and Apache.
1. ssh to your created VM using its public IP and the keypair that you downloaded
2. check if GIt or ansible is installed using the command.
```sh
$ git --version
$ ansible --version
```
In Ubuntu 20.x git is already installed.

3. Proceed to install the ansible. Using the commands
```sh
$ sudo apt update
$ sudo apt install software-properties-common
$ sudo add-apt-repository --yes --update ppa:ansible/ansible
$ sudo apt install ansible
```

4. Installing Apache Web Server
```sh
$ sudo apt update
$ sudo apt install apache2
```
Open the browser and visit the public IP of the VM and check if the apache web server is now visible.

# Configuring your Github
1. Login to your personal Github account and go to settings and the SSH and GPG keys
2. in your VM type this command to generate a public key
```sh
$ sudo ssh-keygen
```
use sudo to have the root user access in the Git.
3. and leave everything as default
4. your public key will be generated in /root/.ssh/id_rsa.pub
5. Concatenate your public key
```sh
$ cat /root/.ssh/id_rsa.pub
```
6. copy the public key and paste it in your Github account SSH and GPG keys.


# Git Clone
1. In your VM cd to /var/www/html and clone the git repository
```sh
$ sudo git clone <ssh url>
```
2. After cloning the repository. Check your VM public IP for updated index.html
3. Create a new git branch in your /var/www/html
```sh
$ sudo git checkout -b branch-<surname>
```
4. You will be changed to your new branch, To check where branch you are working in.
```sh
$ sudo git branch
```
5. edit the title and about us in the index.html in the new branch.
```sh
$ sudo vi index.html
```
6. The changes will also be seen in the browser
7. create a readme.md. in the branch-<surname>
8. git add and commit the changes.
```sh
$ git add .
$ git commit -m "message"
```
9, check your git remote access.
```sh
$ git remote -v
```
10. if the remote access incorrect you can add the origin by this command.
```sh
$ git remote add origin <url>
```
11. push the branch in the github.
```sh
$ git push origin <branch>
```
