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
sudo systemctl restart inspircd
```
Les modifications à la configuration sont 
- balise <server> : préciser le nom de domaine irc.experimentations.buzz, l'id et le network
- balise <bind> : on garde le type="clients" mais on retire la valeur de address

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





























