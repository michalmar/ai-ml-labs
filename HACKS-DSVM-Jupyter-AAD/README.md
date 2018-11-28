# Create DSVM (Linux) with AAD and Authenticate with AAD to JupyterHub

Simple guide on how to enable Azure Active Directory (AAD) integration with LInux DSVM and using JupyterHub.

## Motivation

Many requests to simplify loging into JupyterHub in DSVM.

## Prerequisities

### Step 1
Apply extension to allow AAD login to VM (https://docs.microsoft.com/en-us/azure/virtual-machines/linux/login-using-aad#install-the-azure-ad-login-vm-extension)

```
az vm extension set \
    --publisher Microsoft.Azure.ActiveDirectory.LinuxSSH \
    --name AADLoginForLinux \
    --resource-group YOUR_RESOURCE_GROUP \
    --vm-name YOUR_VM_NAME
```

Setup JupyterHub AAD Login - according to https://github.com/jupyterhub/oauthenticator#azure-setup
1. Install oauthenticator
2. Export env variable AAD tenant id
3. Create AAD App - return URL must match 
4. Change jupyterhub_config.py - use oathenticator (domain here is the address of VM
	
