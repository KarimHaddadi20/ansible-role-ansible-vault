# ansible-vault

Role Ansible pour la gestion des secrets avec Ansible Vault (Exercice 35).  
Derniere mise a jour : parties 4 et 5 (affichage securise, fichier .credentials).

## Description

- Verification de la connectivite
- Creation d'un utilisateur et groupe applicatifs (mot de passe chiffre avec Vault)
- Deploiement d'un fichier de configuration et d'un fichier `.credentials` avec permissions restrictives
- Affichage securise des variables (masquage de la cle API)

## Prérequis

- `passlib` sur le controleur Ansible (pour `password_hash`)
- Fichier `vars/main.yml` chiffre avec `ansible-vault encrypt`
- Variable `mot_de_passe_utilisateur` chiffree dans `defaults/main.yml` avec `ansible-vault encrypt_string`

## Variables

Voir `defaults/main.yml` (variables non sensibles) et `vars/main.yml` (variables sensibles, a chiffrer).

## Utilisation

```yaml
- hosts: all
  become: true
  roles:
    - ansible-vault
```

Lancer avec : `ansible-playbook playbook.yaml --ask-vault-pass`

## Licence

MIT
