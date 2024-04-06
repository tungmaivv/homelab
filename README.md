
# homelab

This is my homelab setup

## setup TrueNAS Scale

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
  
    >suso apt update  
    >sudo apt install nfs-common  
    >showmount -e 192.168.1.100

    - Docker nodes  
  
    >suso mkdir /var/docker-data  
    >sudo apt install nfs-common  
    
    - Dremio nodes

    >suso mkdir /var/docker-data 
    >sudo apt install nfs-common 
  


