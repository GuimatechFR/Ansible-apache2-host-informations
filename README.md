# Apache Server Ansible Playbook

Ce dépôt contient un playbook Ansible conçu pour installer le serveur web Apache (Apache2) sur des systèmes Linux et déployer une page web affichant les informations du serveur.

## Fonctionnalités

- **Installation d'Apache**: Automatise le processus d'installation du serveur web Apache (Apache2).
- **Déploiement de la page d'informations**: Utilise un modèle Jinja2 pour créer et déployer une page HTML personnalisée qui présente les informations du serveur.

## Prérequis

Pour exécuter ce playbook, vous devez avoir :

- Ansible installé sur votre machine de contrôle.
- Un ou plusieurs hôtes cibles configurés dans votre inventaire Ansible sur lesquels Apache sera installé.
- Les hôtes cibles doivent être des systèmes basés sur Debian ou Ubuntu, car ce playbook utilise le module `apt`.

## Structure du dépôt

- `playbook.yml` : Le playbook Ansible qui effectue les tâches.
- `info.html.j2` : Le modèle Jinja2 qui doit être créé pour générer la page d'informations du serveur.

## Utilisation

1. Clonez ce dépôt sur votre machine de contrôle.
2. Ajoutez vos hôtes cibles à votre inventaire Ansible.
3. Personnalisez le modèle `info.html.j2` si nécessaire.
4. Exécutez le playbook avec la commande suivante :

   ```bash
   ansible-playbook -i <chemin_vers_votre_inventaire> playbook.yml<
   ```
Après l'exécution du playbook, ouvrez un navigateur et accédez à l'adresse IP de votre hôte cible pour voir la page des informations du serveur.

## Rôles et Handlers

    Installer Apache2 : Cette tâche s'occupe de l'installation du serveur web Apache2.
    Déployer la page d'informations du serveur : Cette tâche déploie la page HTML générée à partir du modèle Jinja2.
    Démarrer Apache : Un handler pour démarrer le service Apache une fois installé.
