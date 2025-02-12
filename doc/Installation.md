## Installer le serveur

```
sudo apt update
sudo apt install inspircd
sudo ufw allow 6667/tcp
sudo ufw reload
```
## Configurer le serveur

```
cd /etc
sudo chmod +x inspircd
cd inspircd
sudo cp inspircd.conf inspircd.conf.copie
sudo jed inspircd.conf # voir ficheir dans etc
```
## Test avec client

```
sudo apt install weechat
weechat
✦ /server add exp irc.experimentations.buzz
✦ /connect exp
✦ /join #jasette
✦ allo
✦ /quit
```





























