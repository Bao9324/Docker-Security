# Runc Security
This Project is for Application Security Course Project. 
  
Project Goal:  
  
  Improve the security features of Docker, by limiting its access to critical lines of code in the underlying operating system (OS) kernel (Linux kernel in our project).
  
    
  
**Teammates:**


| NAME        |Github NAME |
| ------------- |:-------------:|
| Jin Cheng      | Changy- |
| Eitan Banniettis     | eitanban      | 
| Baochen Wang  | Bao9324      | 
| Jay Dharmendra Solanki | jaydsolanki |

  
  we fork from https://github.com/opencontainers/runc, add rules of blocking risky system calls and modify source code to provide a security version of Runc.

##Requirements  
(we are working on Ubuntu 16.04 64bit)  
Golang : https://golang.org/doc/install  
Libseccomp: `sudo apt-get install libseccomp-dev`   
Docker : https://docs.docker.com/engine/installation/linux/ubuntulinux/  
runc : https://github.com/opencontainers/runc  
  
##Steps
Intall Golang, libseccomp and Docker.  
```
mkdir WORKSPACE  
cd WORKSPACE
git clone https://github.com/Changy-/Docker-Security
cd runc
```
  
 ```
 make  
 sudo make install  
 make test
 ```  
   
###Create Container  
```
mkdir mycontainer
cd mycontainer
# create rootfs
mkdir rootfs
docker export $(docker create busybox) | tar -C rootfs -xvf -
```
Here, all of above steps are the same as original Runc.






