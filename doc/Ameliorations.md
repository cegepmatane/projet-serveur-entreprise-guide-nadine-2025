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

## Configurer le mot du jour
https://docs.inspircd.org/3/configuration/

```
cd /etc/inspircd
sudo ls
sudo cat inspircd.motd
sudo cat inspircd.conf | grep motd
# test avec le client pour voir le motd
sudo jed inspircd.motd
sudo service inspircd restart
# test avec le client pour voir le motd
```


### Test avec client

```
# sudo apt install weechat
weechat
✦ /server add buzz irc.experimentations.buzz/6667
✦ /connect buzz
✦ /quit
```

## Installer le jeu de loup-garou

```
wget https://github.com/lykoss/lykos/archive/refs/tags/stable-201905.zip
unzip stable-201905.zip 
mv lykos-stable-201905 lykos
cd lykos
sudo apt update
sudo apt-cache search pip | grep python
sudo apt install python3-pip
python3 -m pip install -r requirements.txt
```
Après l'installation, on le configure pour notre serveur irc spécifique.
```
cp botconfig.py.example botconfig.py
sudo jed botconfig.py
python3 wolfbot.py &
```
On change les valeurs suivantes dans le jed

HOST = "irc.experimentations.buzz"
PORT = 6667
NICK = "maitre_de_jeu"
USERNAME = ""  # For authentication; can be left bla$
PASS = "testtest" # can be None if authenticating wi$
SASL_AUTHENTICATION = False
USE_SSL = False
SSL_VERIFY = False
CHANNEL = "#loupgarou"

### Test avec client

```
weechat
✦ /connect buzz
✦ /join #loupgarou
✦ !join
✦ /part
✦ /quit
```

