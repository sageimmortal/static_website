Azure Deployment. 

1.
Create an Azure Virtual Machine using the following details.
Resource group:rg_Adlaon
Operating system:Linux (ubuntu 20.04)
Size:Standard B2s (2 vcpus, 4 GiB memory)
All else will be as default.
Allow the Access to the following:
SSH and HTTP

2. 
Configure the VM by deafault to use SSH and SSH key to login.
Ensure that the the private file(PEM file) has been properly downloaded during creation of the VM.
Create your private SSH key using the PEM file. 
Note: Do not lose this file and Store it somewhere safe and Avoid the file being edited unecessarily.
3.
As the Azure instance has been created, try to login using SSH parameters using your generated private key from the PEM file.
Note: during the creation of your private file it might not be accepted by the server.
	Try not to use passphrase and just generate the private key.

------------------------

4.
Perform an update of the ubuntu instance, install apache and ansible.
Use the following commands
Commands:
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install ansible
ansible
sudo apt install apache2

5. 
Allow Apache in ufw settings. (Optional)
Note: Check if ufw is installed or Activated.


6.
Create Github key (generate a new Key for Git hub)
