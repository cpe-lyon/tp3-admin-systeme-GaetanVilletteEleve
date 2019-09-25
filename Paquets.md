# TP 3 - Gestion des paquets

## Exercice 1. Commandes de base

### Commencez par mettre à jour votre système avec les commandes vues dans le cours.
Pour mettre à jour le système on utilise la commande:</br>
<code>sudo apt full-upgrade</code></br>

### 1. Quels sont les 5 derniers paquets installés sur votre machine ?
On peut voir les 5 derniers paquets avec la commande:</br>
<code>grep "installed" /var/log/dpkg.log | tail -5</code></br>

### 2. Utiliser dpkg et apt pour compter le nombre de paquets installés (ne pas hésiter à consulter le manuel !). Comment explique-t-on la (petite) différence de comptage ?
<code>dkpg -l | grep "^ii" | wc -l</code></br>
^ = commence par</br>
commande retourne 514</br>
<code>apt list --installed | wc -l</code></br>
commande retourne 515</br>

### 3.Combien de paquets sont disponibles en téléchargement ?
<code>apt list | wc -l</code></br>
commande retourne 64 118</br>

### 4. Créer un alias “maj” qui met à jour le système
Allez dans le bashrc:</br>
<code>nano .bashrc</code></br>
créer un alias:</br>
<code>alias maj='sudo apt full-upgrade'</code></br>
actualiser le bash:</br>
<code>source ~/.bashrc</code>

### 5. A quoi sert le paquet fortunes ? Installez-le.
Pour installer le paquet:</br>
<code>sudo apt-get install fortunes</code></br>
Le paquet fortunes permet d'afficher des épigrammes.</br>

### 6. Quels paquets proposent de jouer au sudoku ?
Le paquet permettant de jouer au sudoku est:</br>
**gnome-sudoku** (gnome faisant reference à un paquet qui necessite une interface graphique)

### 7. Lister les derniers paquets installés explicitement avec la commande apt install
les derniers paquets installés explicitements sont donnés par la commande:</br>
<code>grep apt install /var/log/dpkg.log</code></br>

## Exercice 2
La commande en une fois:</br>
<code>which -a ls | xargs dpkg -s 2>/dev/null</code></br>
xargs permet de transformer une entrée standard en argument</br>
2> permet d'envoyer les erreurs vers /dev/null qui agit comme un broyeur.
Créer un fichier dans le dossier script:</br>
<code>cd script</code></br>
<code>touch origine-commande</code></br>
<code>nano origine-commande</code></br>
```bash
#!/bin/bash 
echo $(which -a $1 | xargs dpkg -s 2>/dev/null)
```
Ctrl+s puis Ctrl+x</br>

## Exercice 3
Ecrire une commande qui affiche “INSTALLÉ” ou “NON INSTALLÉ” selon le nom et le statut du package
spécifié dans cette commande. </br>
```bash
#!/bin/bash
(dpkg -l $1 | grep "^ii") && echo "installé" || echo "non installé"
```
</br> les doubles pipes permettent en cas d'erreurs ou d'échec de la commande1, alors la commande2 est executé.</br>

## Exercice 4
La commande permettant de lister les programmes est:</br>
<code>apt show coreutils</code></br>
Ce paquet contient les utilitaires de base pour la manipulation de fichier ou de texte et les scripts d'interpreteur de commande qui sont attendus sur tout OS.</br>
La commande **[ ]** est un synonyme de la commande test.


## Exercice 5
Après avoir installé aptitude avec la commande:</br>
<code>apt install aptitude</code></br>
J'ai recherché dans aptitude emacs avec le **/**, puis pour installer le paquet on appuie sur la touche **+** puis 2x sur **g**.</br>

## Exercice 6
### 1. Installer la version Oracle de Java (avec l’ajout des PPA)
<code>
sudo add-apt-repository ppa:linuxuprising/java
sudo apt update
sudo apt install oracle-java11-installer
</code></br>
### 2. Vérifiez qu’un nouveau fichier a été créé dans /etc/apt/sources.list.d. Que contient-il ?
linuxuprising-ubuntu-java-disco.list.save et linuxuprising-ubuntu-java-disco.list</br>

## Exercice 7









