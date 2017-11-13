This File is a cheat sheet for setting up ubuntu server, packages and dependencies. 

#System update
 - Sudo apt-get update
 - Sudo apt-get upgrade
 - Sudo apt-get dist-upgrade

#Installer SSH
- Sudo apt-get update
- Sudo apt-get install openssh-server
- Ifconfig

#Installer dropbox
Se følgende lenke: https://www.digitalocean.com/community/tutorials/how-to-install-dropbox-client-as-a-service-on-ubuntu-14-04

Ekstra kommandoer for dropbox
Tips: TAB kan fullføre navnet, kommandoer kan hende de må kjøre fra dropbox folderen

Kommandoer
- dropbox start
- dropbox stop
- dropbox exclude add 
	eks: dropbox exclude add backup\ av\ desktop/ 
- dropbox exclude remove
	eks: dropbox exclude remove ikt
- Dropbox ls
- dropbox autostart y (autostart dropbox on startup)
- dropbox status
