# Améliorations du serveur IRC
## Installation de Nickserv et Chanserv avec ATHEME
### Installation de Atheme
```
apt update
apt install atheme-services
sudo chmod +x /etc/atheme
cd /etc/atheme
cp /usr/share/doc/atheme-services/examples/atheme.conf.example atheme.conf
cp /etc/atheme/atheme.conf ~/atheme.conf.original
sudo jed atheme.conf
```
Effacer tous les commentaires du fichier de configuration 
(ou recuperer celui du drive dans la semaine 6 (atheme.conf.minimal)
