# Instructions

## Configuration du CPU
- Avant de monter une machine Ubuntu dans VirtualBox, il est important de s'assurer que le CPU de votre machine permette la virtualisation.
- Ces paramètres s'ajustent via les BIOS de votre poste. Chaque machine varie, mais généralement, vous allez retrouver ces paramètres dans ceux du CPU.
- Nous reviendrons plus tard dans la configuration VirtualBox pour s'assurer que la virtualisation est activéedans VirtualBox, avec des mesures de contournement, si nécessaire.

## Téléchargement et installation d'Ubuntu
- Aller sur https://ubuntu.com/download/desktop télécharger une image d'Ubuntu

## Installation de VirtualBox
- Aller sur https://www.virtualbox.org/wiki/Downloads et installer la version selon l'OS de votre poste
## Création d'une VM
- Créer une VM Ubuntu en donnant au minimum > 50-80 GB d'espace, 16 GB de RAM et 4 cores
- Assurez-vous d'activer la virtualisation via la commande PowerShell suivante en spécifiant le nom de votre VM: 
```
VBoxManage modifyvm <NOM DE VOTRE VM> --nested-hw-virt on           
```
- Le site suivant (https://www.how2shout.com/how-to/vboxmanage-command-not-found-in-windows-cmd-or-powershell.html) peut vous aider à configurer votre PATH avec VirtualBox
- Au besoin, ajouter à votre VM un package d'extension VirtualBox (même page qu'en haut), cela vous permettra plus tard d'activer le copier-coller entre les machines.
- Démarrer votre VM et laisser là compléter sa configuration, elle va redémarrer par la suite

## Configurer son environnement
La VM Ubuntu nécessite l'installation de packages afin de faciliter votre travail:
- Git
- Wireshark (installer plus tard via CAPEv2, mais j'ai rencontré des enjeux lors de l'installation, ma préférence est de l'installer séparement)
- VSCode
- Net tools
- Bzip2
```
# Packages
sudo apt install git wireshark bzip2 acpidump

# Vscode
sudo snap install --classic code
````

## Fichier ISO
Une fois importé, s'assurer au minimum de lui donner les droits en faisant: 
```
sudo chmod 777 <NOM_IMAGE>.iso
```
