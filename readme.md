VM Provisioning:

1. Sign in to Azure Portal
2. Go to Virtual Machines
3. Click Create > Azure Virtual Machine
4. create a new resource group (rg_surname)
5. enter VM name (ubuntu.test.surname) and choose Ubuntu Image
6. generate new ssh keypair for the VM. Take note of the VM Username
7. Allow SSH inbound port
8. Keep other settings default and launch the new VM. Make sure to keep a copy of the generated key pair.
9. Visit the new VM, go to Networking > Add inbound port rule > allow public access to port 80
10. Optionally, restrict SSH access to only your IP or the Cascadeo VPN IP

Generating SSH for Github
1. Connect to the server using the downloaded SSH key.
2. change directory by running cd ~/.ssh
3. run ssh-keygen -t ed25519 -C "youremail@address.com"
4. You will be asked to give a filename for your SSH key and optionally a passphrase for the key.
5. Start the ssh-agent using eval "$(ssh-agent -s)"
6. Add the SSH private key to the ssh-agent using ssh-add ~/.ssh/<key_name>
7. Add the SSH Key to your Github account.

Adding SSH key to your Github
1. Login to Github
2. In the upper-right corner, click your profile picture > Settings > Access > SSH and GPG keys
3. Select New SSH key/Add SSH key
4. Go back to the terminal for your VM and copy the contents of the .pub file using cat ~/.ssh/<filename>.pub
5. Paste the contents to Github and add a name for the key
6. Click Add SSH Key

Hosting a Static Website in the VM
1. In the VM terminal, check if git is installed using git --version
1.a. If not yet installed, run "sudo apt update" then "sudo apt install git"
2. run sudo pat update if you have not yet
3. run the following commands to install ansible
3.a. sudo apt install software-properties-common
3.b. sudo apt-add-repository --yes --update ppa:ansible/ansible
3.c. sudo apt install ansible
4. run the following commands to install apache
4.a sudo apt install apache2 -y
4.b. sudo mkdir /var/www/html
4.c. sudo chown -R $USER:$USER /var/www/html
4.d. sudo chmod -R 755 /var/www/html
5. verify if apache is installed by visiting the public IP of your VM.
6. run the following commands to clone the git repository for the 
6.a. cd /
6.b. cd /var/www/html
6.c. rm index.html 
6.d. git clone git@github.com:sageimmortal/static_website.git .
7. Visit the public IP of your VM to check if the static website is working after.
