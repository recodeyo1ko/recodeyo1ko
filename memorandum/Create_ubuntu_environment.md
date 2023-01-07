

Sudo apt update

https://www.google.com/chrome/

google-chrome-stable_current_amd64.deb

sudo apt-get install ./google-chrome-stable_current_amd64.deb
sudo dpkg -i ./google-chrome-stable_current_amd64.deb


https://code.visualstudio.com/download

code_1.74.2-1671533413_amd64.deb


sudo apt install ./code_1.74.2-1671533413_amd64.deb

sudo dpkg -i code_1.64.2-1644445741_amd64.deb

sudo apt-get install git-all


ssh -T git@github.com
vi ~/.ssh/config
```
Host github.com
   User git
   Hostname ssh.github.com
   Port 443
   IdentityFile ~/.ssh/id_rsa
```

cd ~/.ssh
ssh-keygen -t rsa
cat ~/.ssh/id_rsa.pub

