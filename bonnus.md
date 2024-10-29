Bonus (c’est cadeau): 

Les fonctions suivantes simplifient l’utilisation de Bash. En tant utilisateur de Bash vous devez toujours trouver des moyens de simplifier vos taches d’administration. Pour utiliser ses fonction au quotidien il suffit de copier-coller les fonction dans votre fichier /home/$USER/.bashrc.

## Titre: Simplification de la commande 'cd'
Vous pouvez automatiser 'ls' après chaque 'cd'.

```
function cd() {
    builtin cd "$@" && ls
}
```
Utilisation : cd /chemin/vers/le/répertoire


## Titre: Mise à jour rapide du système
Pour les utilisateurs de Linux, créez une fonction pour mettre à jour le système rapidement.

```
function maj() {
    sudo apt-get update && sudo apt-get upgrade
}
```
 
## Titre: Extraction d'archives
Créez une fonction pour extraire divers types d'archives.
- Utilisation : extract fichier.tar.gz

```
function extract() {
  if [ -f $1 ] ; then
      case $1 in
          *.tar.bz2)   tar xjf $1     ;;
          *.tar.gz)    tar xzf $1     ;;
          *.bz2)       bunzip2 $1     ;;
          *.rar)       unrar e $1     ;;
          *.gz)        gunzip $1      ;;
          *.tar)       tar xf $1      ;;
          *.tbz2)      tar xjf $1     ;;
          *.tgz)       tar xzf $1     ;;
          *.zip)       unzip $1       ;;
          *.Z)         uncompress $1  ;;
          *.7z)        7z x $1        ;;
          *)           echo "'$1' ne peut pas être extrait via extract()" ;;
      esac
  else
      echo "'$1' n'est pas un fichier valide"
  fi
}
```



## Titre: Rechercher une commande précédente
Une fonction pour rechercher dans l'historique de la ligne de commande.

```
function h() {
    history | grep $1
}

#Utilisation : h commande_recherchée
```
 
## Titre: Monitorer l'utilisation du CPU
Une fonction pour afficher l'utilisation actuelle du CPU.

```
function cpu() {
    top -b -n1 | grep "Cpu(s)" | awk '{print $2 + $4}'
}

#Utilisation : `cpu`
```

## Titre: Afficher la mémoire utilisée
Une fonction pour afficher la quantité de mémoire utilisée.

```
function mem() {
    free -m | awk 'NR==2{printf "Mémoire utilisée: %s/%sMB (%.2f%%)\n", $3,$2,$3*100/$2 }'
}

#Utilisation : `mem`
```
## Titre: Vider le cache DNS
Pour les utilisateurs de Linux, créez une fonction pour vider le cache DNS.

```
function viderdns() {
   sudo resolvectl flush-caches
}

# Utilisation : `viderdns`
```


## Titre: Trouver des fichiers volumineux
Une fonction pour trouver les 10 plus gros fichiers dans le répertoire courant et ses sous-répertoires.

```
function grosfichiers() {
    find . -type f -exec ls -lh {} \; | awk '{ print $9 ": " $5 }' | sort -hr -k2 | head -n 10
}

#Utilisation : `grosfichiers`
```
## Titre: Générer un mot de passe aléatoire
Une fonction pour générer un mot de passe aléatoire de 16 caractères.

```
function genmdp() {
    < /dev/urandom tr -dc _A-Z-a-z-0-9 | head -c${1:-16};echo;
}

Utilisation : `genmdp`
```


## Titre: Afficher l'adresse IP publique
Une fonction pour obtenir l'adresse IP publique.

```
function myip() {
    curl ipinfo.io/ip
}

# Utilisation : `myip`
```

## Titre: Copier le contenu d'un fichier dans le presse-papiers
Une fonction pour copier le contenu d'un fichier dans le presse-papiers.

```
function cpclip() {
    cat $1 | xclip -selection clipboard
}

# Utilisation : `cpclip fichier.txt`
```
## Titre: Créer une archive tar.gz
Une fonction pour créer une archive tar.gz à partir d'un répertoire.

function tarzip() {
    tar -czvf $1.tar.gz $1
}

Utilisation : `tarzip répertoire`Titre: Shortcuts pour la navigation dans les répertoires

## Titre : Changer rapidement de répertoire
Vous pouvez ajouter des fonctions pour changer rapidement de répertoire. Par exemple, pour aller au répertoire parent.

function ..() { cd ..; }

Utilisation : ..

## Titre: Extraction d'archives
Créez une fonction pour extraire divers types d'archives.

function extract() {
  if [ -f $1 ] ; then
      case $1 in
          *.tar.bz2)   tar xjf $1     ;;
          *.tar.gz)    tar xzf $1     ;;
          *.bz2)       bunzip2 $1     ;;
          *.rar)       unrar e $1     ;;
          *.gz)        gunzip $1      ;;
          *.tar)       tar xf $1      ;;
          *.tbz2)      tar xjf $1     ;;
          *.tgz)       tar xzf $1     ;;
          *.zip)       unzip $1       ;;
          *.Z)         uncompress $1  ;;
          *.7z)        7z x $1        ;;
          *)           echo "'$1' ne peut pas être extrait via extract()" ;;
      esac
  else
      echo "'$1' n'est pas un fichier valide"
  fi
}

Utilisation : extract fichier.tar.gz

## Titre: Affichage des fichiers cachés
Une fonction pour afficher les fichiers cachés.

function lh() { 
    ls -lh .[^.]* 
}

## Utilisation : lh

Titre: Créer un nouveau répertoire et y entrer
Pour créer un nouveau répertoire et y entrer en une seule commande.

function mkcd() { 
    mkdir -p "$@" && cd "$_"; 
}

Créer un Fichier nommée “monBASHRC” avec comme contenu les commandes ci-dessous.
Faites une fonction qui copie des commandes dans votre bashrc si ce n’est pas déjà fait. Apprenez à les utiliser, améliorez les et faites vos propres fonctions.

```
function ..() { cd ..; }


function cd() {
    builtin cd "$@" && ls
}

function maj() {
    sudo apt-get update && sudo apt-get upgrade
}

function extract() {
  if [ -f $1 ] ; then
      case $1 in
          *.tar.bz2)   tar xjf $1     ;;
          *.tar.gz)    tar xzf $1     ;;
          *.bz2)       bunzip2 $1     ;;
          *.rar)       unrar e $1     ;;
          *.gz)        gunzip $1      ;;
          *.tar)       tar xf $1      ;;
          *.tbz2)      tar xjf $1     ;;
          *.tgz)       tar xzf $1     ;;
          *.zip)       unzip $1       ;;
          *.Z)         uncompress $1  ;;
          *.7z)        7z x $1        ;;
          *)           echo "'$1' ne peut pas être extrait via extract()" ;;
      esac
  else
      echo "'$1' n'est pas un fichier valide"
  fi
}


function h() {
    history | grep $1
}


function cpu() {
    top -b -n1 | grep "Cpu(s)" | awk '{print $2 + $4}'
}


function mem() {
    free -m | awk 'NR==2{printf "Mémoire utilisée: %s/%sMB (%.2f%%)\n", $3,$2,$3*100/$2 }'
}


function viderdns() {
    sudo resolvectl flush-caches
}

function grosfichiers() {
    find . -type f -exec ls -lh {} \; | awk '{ print $9 ": " $5 }' | sort -hr -k2 | head -n 10
}

function genmdp() {
    < /dev/urandom tr -dc _A-Z-a-z-0-9 | head -c${1:-16};echo;
}

function myip() {
    curl ipinfo.io/ip
}

function cpclip() {
    cat $1 | xclip -selection clipboard
}

function tarzip() {
    tar -czvf $1.tar.gz $1
}


function extract() {
  if [ -f $1 ] ; then
      case $1 in
          *.tar.bz2)   tar xjf $1     ;;
          *.tar.gz)    tar xzf $1     ;;
          *.bz2)       bunzip2 $1     ;;
          *.rar)       unrar e $1     ;;
          *.gz)        gunzip $1      ;;
          *.tar)       tar xf $1      ;;
          *.tbz2)      tar xjf $1     ;;
          *.tgz)       tar xzf $1     ;;
          *.zip)       unzip $1       ;;
          *.Z)         uncompress $1  ;;
          *.7z)        7z x $1        ;;
          *)           echo "'$1' ne peut pas être extrait via extract()" ;;
      esac
  else
      echo "'$1' n'est pas un fichier valide"
  fi
}


function lh() { 
    ls -lh .[^.]* 
}

function mkcd() { 
    mkdir -p "$@" && cd "$_"; 
}
``
