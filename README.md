# CUB3D Tester

This repository contains a Bash script designed to test the maps of the Cub3D project (42 project). It checks for memory leaks and file descriptor leaks by using Valgrind on each map present in the test folders, divided into valid maps (maps/good) and invalid maps (maps/bad).

## Installation

1. Clone this repository directly into the cub3d folder of your user.
 ```bash
 git clone https://github.com/votre-utilisateur/cub3d-tester.git cub3d/cub3d-tester
  ```

 2. Make the script executable :
 ```bash
  cd cub3d/cub3d-tester  
  chmod +x tester.sh
  ```

## How to run
Run the script from the cub3d-tester folder :

```bash
  ./tester.sh
```
## Separate tests

You can also call ./tester + 'good or bad' to run only a specific part of the test:

```bash
./tester.sh good
```
```bash
./tester.sh bad
```


The script will then run tests for all maps in the maps/bad folder, and will prompt you to press Enter to start tests for the maps in maps/good.

## Test Details

Pour chaque fichier .cub, le script :
1. Exécute Valgrind pour détecter les fuites de mémoire et les descripteurs de fichiers non fermés.
2. Affiche un message de succès ou d'erreur selon les résultats :
     Succès : Pas de fuites de mémoire ni de descripteurs de fichiers ouverts.
     Erreur : Indique si des descripteurs de fichiers restent ouverts ou si des fuites de mémoire sont détectées.

Le script fournit un résumé à la fin de chaque série de tests.
