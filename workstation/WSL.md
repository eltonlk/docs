# Windows + WSL2

## Pré-Requisitos

Em "Ativar e Remover Recusos" deve ativar as opções e reiniciar:

- Hyper-V 
- Subsistema do Windows para Linux (Microsoft Subsystem for Linux)
- Plataforma de Máquina Virtual (Virtual Machine Platform)

## Atualizar o Kernel do Linux

Baixar e instalar o [https://docs.microsoft.com/pt-br/windows/wsl/install-win10#step-4---download-the-linux-kernel-update-package](pacote de atualização do kernel do Linux).

[https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi](Pacote de atualização do kernel do Linux do WSL2 para computadores x64)

## Definir o WSL 2 como a sua versão padrão

Abra o PowerShell e execute este comando para definir o WSL 2 como a versão padrão ao instalar uma nova distribuição do Linux:

    wsl --set-default-version 2

## Instalar a distribuição do Linux de sua escolha

Abra a Microsoft Store e escolha sua distribuição do Linux favorita. Ex: Ubuntu, OpenSUSE...

Clique em obter, em instalar e depois em iniciar.

Na primeira vez que você iniciar uma distribuição do Linux recém-instalada, você precisará criar uma conta de usuário e uma senha para sua nova distribuição do Linux.

## Instalar o Terminal do Windows (Opcional)

Abra a Microsoft Store e faça uma busca por Windows Terminal.

Clique em obter, em instalar e depois em iniciar. Já vai aparecer na &#709; a distribuição linux instalada.

## Definir a distribuição do linux como padrão do terminal (Opcional)

Clique na &#709; e em seguida em Configurações.

Na chave "defaultProfile" substitua a valor pelo o guid do profile (Terminal ou distribuição linux) desejado.

## Instalar Fontes Powerline para o terminal (Opcional)

Procure por Windows PowerShell e clique na opção de executar como administrador.

Execute os seguintes comandos:

    Set-ExecutionPolicy Bypass
    cd c:\
    mkdir tmp -Force
    cd tmp
    wget https://github.com/powerline/fonts/archive/master.zip -outfile "fonts-master.zip"
    Expand-Archive -Path fonts-master.zip -DestinationPath C:\tmp\
    cd fonts-master
    ./install.ps1
    cd ..
    rm fonts-master*
    Set-ExecutionPolicy Default

## Definir para o Windows Terminal usar uma Fonte Powerline

Definir nas configurações do windows ternimal para usuar a fonte "Roboto Mono for Powerline".

Pode definir diretamente em cada profile adicionando

    "fontFace" : "Roboto Mono for Powerline"

Ou pode ser definido para todos os profiles

    "defaults": {
        ...
        "fontFace" : "Roboto Mono for Powerline"
        ...
    }
    
## Definir para o Windows Terminal iniciar na pasta do usuário

Profiles do Windows PowerShell e cmd

    "startingDirectory" : "%USERPROFILE%"
    
Profile da distribuição linux, deve substituir NOME_DA_DISTO e USERNAME

    "startingDirectory": "//wsl$/NOME_DA_DISTO/home/USERNAME/"

