# What is this documentation
This document contains a cheat guide for installing and administrating ubuntu server. 
Editing this document requires using markdown

markdown documentation
https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet

#############################################################################################
# System update
	Sudo apt-get update
	Sudo apt-get upgrade
	Sudo apt-get dist-upgrade


# Installer SSH
	Sudo apt-get update
	Sudo apt-get install openssh-server
	Ifconfig


# Disk settup
## Merg disks using LVM and raid
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
