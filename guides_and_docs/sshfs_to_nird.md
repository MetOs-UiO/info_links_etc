# HOW TO SSHFS TO NIRD

Author: Marianne Pietschnig 
Edited by Sara Blichner

---------------------------

One option to access data and code on nird while using the software available on your local machine (e.g. atom/sublime text editors, your local anaconda/python packages or conda environments etc) is to mount nird on your local machine. This means that nird is linked to your local machine and appears as if it were a directory e.g. in your /home folder. 

In order to do so, you need to install and use sshfs. 
Here is a guide which I found helpful for installing and setting up, although below I'll describe some minor tweaks. 

https://www.digitalocean.com/community/tutorials/how-to-use-sshfs-to-mount-remote-file-systems-over-ssh

Below is what I did for my ubuntu machine (see the guide for other options e.g. Mac OS) 

1.) Install sshfs via the command: 
```bash
sudo apt-get install sshfs
```

2.) Make a directory somewhere on your local machine that you want nird to link to, e.g. /home/your_username/mounts/nird (NB: I had to create both the mounts and nird directory). If you follow the guide exactly, it will tell you to create a file in /mnt. This is unhelpful if you don't want to use sudo to sshfs to nird

3.) Mounting NIRD to your local machine: 
Enter the command: 
```bash
sshfs -o reconnect,ServerAliveInterval=15,ServerAliveCountMax=3 your_username@login-tos.nird.sigma2.no:/projects/path-to-your-folder /home/your_username/mounts/nird"
```

(For this step you might need to use a slightly different @login-tos.nird ..., basically just whatever path you use to ssh to nird)


That's it. Now you can cd into the folder where you mounted nird (in this case /home/your_username/nird) and open files with whatever you have installed locally. 

The advantage of doing this is that it's a bit easier to install stuff locally sometimes (due to sudo rights etc). The disadvantage is, it won't be backed up and won't be available from anywhere other than your local machine.

One problem I haven't been able to solve yet is that sshfs-ing into your folder on nird means that you can't access anything which is "higher up" in the directory structure, e.g. other projects. One work around for that as suggested by Sara is to just set-up a second mount if you need anything from a differet projects folder. 

Finally: 
4.) Unmounting nird: 
```bash
umount /home/your_username/mounts/nird
```
I've made both the mounting and unmounting command an alias in my bashrc file. 

Good luck! :) 

---------------------------------------------------

## Make your python code work both locally and on nird:
To make the paths to your files correct both if a script is run on nird and on your local computer, you may include the following:

```python
import socket
hostname = socket.gethostname()
if 'nird' in hostname:
cmip_folder='wherever/it/is/on/nird'
else: #this is the mount
cmip_folder = 'wherever/you/keep/the/mount'
```
---------------------------------------------------
