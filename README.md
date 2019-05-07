# What is this documentation
This document contains a cheat guide for installing and administrating ubuntu server. 
Editing this document requires using markdown

markdown documentation
https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet

#Div tools
###How to get IP on the server
- route -n (vise internal IP og dns)
- nmcli dev show <IFACE> (vise internal IP og dns)
- curl ipinfo.io/ip (vis external IP)
	
###Display disks
- sudo parted -l
- sudo fdisk /dev/sda     -> etterfulgt av -> p
https://www.maketecheasier.com/create-file-systems-partitions-terminal-linux/ 

#############################################################################################
# System update
	Sudo apt-get update
	Sudo apt-get upgrade
	Sudo apt-get dist-upgrade


# Installer SSH
	Sudo apt-get update
	Sudo apt-get install openssh-server
	Ifconfig
# Installer og konfigurer cockpit

### Installasjon
	sudo apt-get install cockpit

### Settup for remote tilgang med Cockpit
	1, Åpne routeren
	2, Gå til "Advanced"
	3, Gå til "NAT"
	4, Skriv in port som skal forwardes (standard er 9090 for cockpit)
	Alternativt kan man endre display port til feks 40500 for økt sikerhet


# Disk settup
https://www.cyberciti.biz/tips/fdisk-unable-to-create-partition-greater-2tb.html 

###Alternativ måte
Merg disks using LVM and raid:
https://askubuntu.com/questions/7002/how-to-set-up-multiple-hard-drives-as-one-volume/7841#7841


# Installer dropbox
	https://www.digitalocean.com/community/tutorials/how-to-install-dropbox-client-as-a-service-on-ubuntu-14-04

## Dropbox Kommandoer
Tips: Det er flere triks man kan bruke ved bruk av Dropbox kommandoene. De enkleste er bruk av "TAB" for fullføring av kommando/navn, og kjør kommandoene nevnt under i terminalen ved bruk av CD til dropbox lokasjonen.

| Command        | Description           | Example  |
| ------------- |:-------------:| -----:|
| Dropbox Start     | Start dropbox service | N/A |
| Dropbox stop    | Stop dropbox service     |   N/A |
| Dropbox exclude add | selective sync, exlude folders too sync     |    dropbox exclude add backup\ av\ desktop/|
| dropbox exclude remove     | Selective sync, include folders that previously was excluded |dropbox exclude remove backup\ av\ desktop/ |
| dropbox ls    | list foldres and files in the selected directory     |   N/A |
| dropbox autostart | Settings regarding autostart (yes/no)     |   dropbox autostart y|
| dropbox status | Provide status on dropbox syncronization     |  N/A|

# Samba network share
For å lage en delt disk er følgende rutiner

#### 1. Install Samba
	sudo apt-get update
	sudo apt-get install samba
	
#### 2. Set a password for your user in Samba
	sudo smbpasswd -a "user_name"
	
#### 3. Create a directory to be shared
	mkdir /home/<user_name>/<folder_name>
	
#### 4. sudo nano /etc/samba/smb.conf
	Once "smb.conf" has loaded, add this to the very end of the file:

	[myshare]
	path = /path/to/share
	writeable = yes
	browseable = yes
	guest ok = yes
	public = yes
	force user = ServerUsernameGoesHere
	
#### 5. Restart the samba
sudo service smbd restart

#### 7. Once Samba has restarted, use this command to check your smb.conf for any syntax errors
	testparm
#### 8. Provide access to the folder structure
	Sudo chmod -R 777 /path/to/share/folder

#### 8. To access your network share
	Open windows explorer, then type in the following: \\IP-ADDRESS\SHARE-NAME
	
##NB! 
Det kan hende det må opprette en bruker både i SAMBA og på server.
Dette kan gjøres på følgende måte
#### 1. Create samba user
	sudo smbpasswd -a <user_name>
#### 2. Create local user on the server
	1, Åpne terminal og kjør "sudo nano /etc/adduser.conf"
	2, Finn feltet (ofte i bånd)
	"NAME_REGEX=”^[a-z][-a-z0-9]*$’" , og endre dette til -> #NAME_REGEX=”^[a-z][-a-z0-9].*$’
	3, Åpne terminal og skriv “sudo useradd navn.navn”
	4, Kjør dermed “ Sudo mkhomedir_helper navn.navn

# Installing SABnzb,couch potato and sickbeard on server
## SABnzbd
Her er link til framgangsmåte https://www.htpcbeginner.com/install-sabnzbd-on-ubuntu-server-easy-atomic-method/ 


# General commands
####Delete folders with content
	sudo rm -rf foldername/
