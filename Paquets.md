# TP 3 - Gestion des paquets

## Exercice 1. Commandes de base

### Commencez par mettre à jour votre système avec les commandes vues dans le cours.
Pour mettre à jour le système on utilise la commande:
<code>sudo apt full-upgrade</code></br>

### 1. Quels sont les 5 derniers paquets installés sur votre machine ?
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
<code>nano .bashrc</code>
créer un alias:</br>
<code>alias maj='sudo apt full-upgrade'</code>
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


