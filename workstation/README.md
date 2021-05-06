# Configuração de Ambiente de Trabalho

## OS

- [Windows + WSL](WSL.md)

## Dependências

Ubuntu

```sh
sudo apt update
sudo apt upgrade
sudo apt install build-essential gnupg2 zip libmysqlclient-dev mysql-client libpq-dev postgresql-client
```

## Diversos

- [Terminal](Terminal.md)
- [Git](Git.md)
- [Editor de Texto](Editor.md)
- [Docker + Docker Compose](Docker.md)

## Google Cloud SDK

[Google Cloud SDK](https://cloud.google.com/sdk/docs/install#deb)

```sh
echo "deb [signed-by=/usr/share/keyrings/cloud.google.gpg] https://packages.cloud.google.com/apt cloud-sdk main" | sudo tee -a /etc/apt/sources.list.d/google-cloud-sdk.list
sudo apt-get install apt-transport-https ca-certificates gnupg
curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key --keyring /usr/share/keyrings/cloud.google.gpg add -
sudo apt-get update && sudo apt-get install google-cloud-sdk
gcloud -v
```

## PYENV - Python

[pyenv-installer](https://github.com/pyenv/pyenv-installer)
[pyenv](https://github.com/pyenv/pyenv)


```sh
curl https://pyenv.run | bash
```

Adicionar no .bashrc e .zlogin.

```sh
export PYENV_ROOT="$HOME/.pyenv"
export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
```

Instalar a versão desejada e definir como global

```sh
pyenv install --list
pyenv install 3.9.5
pyenv global 3.9.5
```

## RVM - Ruby

[rvm.io](https://rvm.io/)

```sh
gpg2 --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB
\curl -sSL https://get.rvm.io | bash -s stable
rvm list known
rvm install 2.6
gem install bundler
gem install git-up
gem install rails --pre
```

## NVM - Node

[creationix/nvm](https://github.com/creationix/nvm)

```sh
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash
```

Adicionar no arquivo .zlogin.

```sh
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
```

Instalar a última versão do Node.

```sh
nvm install node
```

Instalar a versão estável do Node.

```sh
nvm install --lts
```

## PHP + Composer

```sh
sudo add-apt-repository ppa:ondrej/php
sudo apt-get update
sudo apt-get install php8.0 php8.0-fpm php8.0-sqlite php8.0-mbstring php8.0-curl php8.0-xml php8.0-zip 
```

[composer](https://getcomposer.org/download/)

```sh
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('sha384', 'composer-setup.php') === '48e3236262b34d30969dca3c37281b3b4bbe3221bda826ac6a9a62d6444cdb0dcd0615698a5cbe587c3f0fe57a54d8f5') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink('composer-setup.php');"
sudo mv composer.phar /usr/local/bin/composer
```

Adicionar no arquivo .zlogin.

```sh
export PATH="$PATH:$HOME/.composer/vendor/bin"
```

## YARN

```sh
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt-get update && sudo apt-get install --no-install-recommends yarn
```

## SSH

```sh
ssh-keygen -t rsa -C "eltonlk@gmail.com"
cat ~/.ssh/id_rsa.pub
```

Copie a chave gerada e coloque onde for usar, [github](http://github.com/), [bitbucket](http://bitbucket.com/), etc.

##

```sh
sudo apt-get install zlib1g-dev libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev libffi-dev libgdbm-dev libncurses5-dev automake libtool bison libffi-dev python-software-properties libmysqlclient-dev
```
