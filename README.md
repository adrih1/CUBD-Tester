# CUB3D Tester

Ce dépôt contient un script Bash destiné à tester les maps du projet **Cub3D** (projet 42). Il permet de vérifier les fuites de mémoire et de descripteurs de fichiers en utilisant **Valgrind** pour chaque map présente dans les dossiers de tests, divisés en maps valides (`maps/good`) et maps invalides (`maps/bad`).

## Prérequis

Avant de commencer, assurez-vous d'avoir installé :
- **Valgrind** : utilisé pour détecter les fuites de mémoire et autres erreurs.
- **Cub3D** : le projet que vous souhaitez tester.

## Installation

1. **Clonez ce dépôt** directement dans le dossier `cub3d` de votre utilisateur.
 ```bash
 git clone https://github.com/votre-utilisateur/cub3d-tester.git cub3d/cub3d-tester
  ```

 2. Rendez le script exécutable :
 ```bash
  cd cub3d/cub3d-tester  
  chmod +x tester.sh
  ```

## Utilisation
Lancez le script à partir du dossier cub3d-tester :

```bash
  ./tester.sh
```

Le script exécutera alors les tests pour toutes les maps présentes dans maps/bad, et vous demandera ensuite d’appuyer sur Entrée pour lancer les tests pour maps/good.

## Détails du test

Pour chaque fichier .cub, le script :
1. Exécute Valgrind pour détecter les fuites de mémoire et les descripteurs de fichiers non fermés.
2. Affiche un message de succès ou d'erreur selon les résultats :
     Succès : Pas de fuites de mémoire ni de descripteurs de fichiers ouverts.
     Erreur : Indique si des descripteurs de fichiers restent ouverts ou si des fuites de mémoire sont détectées.

Le script fournit un résumé à la fin de chaque série de tests.
