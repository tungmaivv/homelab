
# homelab

This is my homelab setup

## setup docker swarm
3 nodes docker swarm VM on proxmox

## setup TrueNAS Scale
- setup TrueNAS Scale VM
  - download from https://www.truenas.com/download-truenas-scale/
- Data sets:

>   - proxmox  
>        |---data  
>            |---iso (SMB)   
>            |---backup (SMB)   
>            |---vm-disks (SMB)   
>            |---docker-data (NFS)  
>            |---datalake-dat (NFS)  

- mount nfs shares to docker nodes and dremio nodes
    - all nodes  
  
    >sudo apt update  
    >sudo apt install nfs-common  
    >showmount -e 192.168.1.100  

    - Docker nodes  
  
    >sudo mkdir /var/docker-data  
    >sudo apt install nfs-common  
    >sudo mount -t nfs 192.168.1.100:/mnt/promox/data/docker-data /var/docker-data

    - Dremio nodes  

    >suso mkdir /var/datalake-data   
    >sudo yum install nfs-utils  
    >sudo mount -t nfs 192.168.1.100:/mnt/promox/data/datalake-data /var/datalake-data
  


