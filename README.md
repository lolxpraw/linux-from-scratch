# linux-from-scratch
An introduce to guide everyone want to use Linux from Sractch from zero to hero lol
## 1. Load up ISO and SSH
- Download link: https://www.gentoo.org/downloads/amd64/
- Guide: https://www.linuxfromscratch.org/lfs/view/stable/
- I recommend you should download LiveGUI USB Image for easy boot.
After installation and booting, you can see the UI and Plasma KDE in Gentoo. What I want you to do is remove it, press Ctrl + ALT + F1 and type command "Clear". The result in the picture:
<img width="1605" height="914" alt="image" src="https://github.com/user-attachments/assets/9d81dcda-b4dc-41cd-86d6-29ec9051f0b3" />

- Next, you want to make a pesudo password for root with command "sudo passwd root". Type your password and we can go.
- Turn on your SSHD, which is installed on the file .iso. All you want to do switch for user using commnand "su -" and turn on SSHD "rc-service"
- Note: An SSH daemon (sshd) is a background program running on a server that continuously listens for incoming secure remote connections.
<img width="1310" height="143" alt="image" src="https://github.com/user-attachments/assets/20b23735-365c-45bc-a15c-5018bd30d026" />

- Find IPv4 and we switch to host machine to easy to copy, paste any command from LFS book
<img width="1247" height="856" alt="image" src="https://github.com/user-attachments/assets/d62bc143-edb3-4c56-9640-6df0cfc8b355" />

- I use Gentoo on VMware, for convenient I use SSH in PowerShell (Windows). Use command "ssh root@<IP address>"
<img width="729" height="63" alt="image" src="https://github.com/user-attachments/assets/440cadd7-e529-40d7-9d6d-ec0ff106b74f" />

## 2. Partititon disks and Filesystem (Chapter 2)
- First things you want to do is check your disk. Using command "lsblk"
- Choose your disk. Command "cfdisk /dev/sda" (2.4 in guide book)
- In this image, I divided this partition into 3 parts: first part is 1GB EFI System partition, second part is the Linux swap and last one is the Linux System operation
<img width="856" height="241" alt="image" src="https://github.com/user-attachments/assets/e6f229c0-9b0c-4421-8777-9d208a605b21" />

- Filesystem (2.5 in guide book)
<img width="858" height="312" alt="image" src="https://github.com/user-attachments/assets/d8b3aacc-afd4-4a30-a993-b02e17a118af" />

- Settings the $LFS Variable and the Umask: (2.6)
  + The enviroment variable LFS will be used several time. You should ensure that this variable is always defined throughout the LFS build process. Command "export LFS=/mnt/lfs". Check that LFS is set by using "echo $LFS"
   <img width="635" height="59" alt="image" src="https://github.com/user-attachments/assets/55991c36-27a7-4946-b26b-082a281dc791" />
   
  + Set the file mode creation mask (umask) to 022 in case the host distro uses a different default:
    <img width="623" height="55" alt="image" src="https://github.com/user-attachments/assets/9a91e031-4ecc-41f8-becb-91966bcba169" />
    
  * Note: $LFS variable points to the root directory where you install the LFS system, umask determines the default permissions when creating new files or directories.


- Mounting the new partition:
  + Now the file systems is mounted at the directory specified by the LFS enviroment variable.
  + Create the mount point and mount the LFS file system with these command on this picture:
  <img width="707" height="92" alt="image" src="https://github.com/user-attachments/assets/d959691f-6173-42fc-b5b3-106d25b4668e" />

 
- Set the owner and permission mode of the $LFS directory:

  <img width="452" height="153" alt="image" src="https://github.com/user-attachments/assets/3a85f235-a752-48ff-8fe5-92deb471785a" />

