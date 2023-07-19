VM Provisioning:

1. Sign in to Azure Portal
2. Go to Virtual Machines
3. Click Create > Azure Virtual Machine
4. create a new resource group (rg_surname)
5. enter VM name (ubuntu.test.surname)
6. generate new ssh keypair for the VM. Take note of the VM Username
7. Allow SSH inbound port
8. Keep other settings default and launch the new VM. Make sure to keep a copy of the generated key pair.
9. Visit the new VM, go to Networking > Add inbound port rule > allow public access to port 80
10. Optionally, restrict SSH access to only your IP or the Cascadeo VPN IP

