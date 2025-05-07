# Git

```sh
sudo apt install git
```

## Configuração

```sh
git config --global user.name "Elton Luis Kolling"
git config --global user.email "eltonlk@gmail.com"
git config --global init.defaultBranch main
git config --global color.ui true
git config --global color.status auto
git config --global color.branch auto
git config --global color.interactive auto
git config --global color.diff auto
git config --global color.grep auto
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status
git config --global alias.unstage 'reset --hard HEAD~1'
git config --global alias.last 'log -1 HEAD'
git config --global alias.hist "log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short"
git config --global core.editor 'code --wait' | 'subl' | 'mate -w'

# No WSL
git config --global core.autocrlf input
```
