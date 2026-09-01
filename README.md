# linux-from-scratch
An introduce to guide everyone want to use Linux from Sractch from zero to hero lol
- Download link: https://www.gentoo.org/downloads/amd64/
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
