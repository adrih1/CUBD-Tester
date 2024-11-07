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
⚠️ Do not launch ./tester.sh from VS Code's terminal, it will cause an opened fd error. Only use official computer's terminal.

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

For each .cub file, the script:
1. Runs Valgrind to detect memory leaks and open file descriptors.
2. Displays a success or error message based on the results:
    Success: No memory leaks or open file descriptors.
    Error: Indicates if any file descriptors remain open or if memory leaks are detected.

The script provides a summary at the end of each test series.
