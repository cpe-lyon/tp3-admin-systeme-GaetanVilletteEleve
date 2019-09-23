# TP 3 - Gestion des paquets

## Exercice 1. Commandes de base

### Commencez par mettre à jour votre système avec les commandes vues dans le cours.
Pour mettre à jour le système on utilise la commande:
<code>sudo apt full-upgrade</code></br>

### 1. Quels sont les 5 derniers paquets installés sur votre machine ?
<code>grep "installed" /var/log/dpkg.log | tail -5</code></br>

### 2. Utiliser dpkg et apt pour compter le nombre de paquets installés (ne pas hésiter à consulter le manuel !). Comment explique-t-on la (petite) différence de comptage ?

### 3.Combien de paquets sont disponibles en téléchargement ?
