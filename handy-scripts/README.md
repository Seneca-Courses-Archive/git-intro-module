# SSH to Linux VMs
[How to use SSH keys with Windows on Azure](https://docs.microsoft.com/en-us/azure/virtual-machines/linux/ssh-from-windows)

Create an SSH key pair in ` powershell `
```powershell
ssh-keygen -m PEM -t rsa -b 2048
```
Createe a VM using your key
```bash
az vm create \
   --resource-group myResourceGroup \
   --name myVM \
   --image UbuntuLTS\
   --admin-username azureuser \
   --ssh-key-value ~/.ssh/id_rsa.pub
```
Connect to your VM
```bash
ssh -i ~/.ssh/id_rsa azureuser@10.111.12.123
```
