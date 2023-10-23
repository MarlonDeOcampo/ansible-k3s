## How to setup longhorn

### Step-1: Check For The Dependencies And Pre-Requisites For Longhorn In Your Cluster

```sh
    wget https://raw.githubusercontent.com/longhorn/longhorn/v1.3.0/scripts/environment_check.sh
```
after successfully downloaded , run the script

```sh
    bash environment_check.sh 
```
if there is no error, you are clear to proceed with the next installation steps, else you need to install all the necessary packages that are needed to make the installation of longhorm succeed. 

Most of the time, nfs common and iscsid are the errors you will get. To install these two, use the codes below.

```sh
    sudo apt install nfs-common -y
    sudo systemctl enable iscsid
```

### Installation of longhorn using helm

```sh
    helm repo add longhorn https://charts.longhorn.io
    helm repo update
    helm search repo longhorn  --max-col-width 80
    helm show  values longhorn/longhorn > longhorn_values.yml
```

