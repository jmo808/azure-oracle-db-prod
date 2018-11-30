# Deploy a Production Oracle DB Server in Azure

## Install Azure Ansible Package

``` 
sudo apt install pip
pip install ansible[azure]
``` 

## Install Azure CLI
[RedHat](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli-yum?view=azure-cli-latest)

[Ubuntu](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli-apt?view=azure-cli-latest)

## Login into Azure Subscription
```
az login
az account set --subscription "<Subscription Name>"
```
 
## Run the Playbook

Clone this repo.
Edit secrets.yml and enter desired password and password hash salt.
Edit properties.yml and enter desired deployment parameters.

Run the playbook
```
ansible-playbook deploy-oracle-server.yml
```

NOTE: This playbook assumes that you aren't using Ansible Tower and that your Ansible deployment computer can access the Azure subnet you are deploying the Oracle server to. If your deployment computer does not have network access to the Oracle server subnet the playbook will fail after deploying the Azure Infrastructure.
