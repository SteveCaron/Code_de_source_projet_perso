# Projet Code de Source: Traitement des données météorologique du réseau infoclimat

## Description

Ce projet a pour but d'extraire des données météorologiques mesurées par les différentes stations du réseau infoclimat(STATIC), de les transformer et de les stocker dans une base de données BigQuery. 

## Prérequis

* Python 3.7
* Un projet sur Google Cloud Platform
* Une clef API infoclimat lié à votre adresse ip https://www.infoclimat.fr/opendata/

## installation

* Cloner le projet
* Creer un environnement virtuel

    ```bash
    # Linux
    python -m venv .venv
    # Windows
    py -m venv .venv
    ```
* Activer l'environnement virtuel

    ````bash
    # Linux
    .venv/bin/activate
    # Windows (batch/cmd)
    .venv/Scripts/activate.bat
    # Windows (powershell)
    .venv/Scripts/Activate.ps1
    ````

* Installer les dépendances

    ``` bash
    pip.install -r requirement.txt
    ```

* Creer un projet GCP. Dans ce projet creer un bucket et un dataproc.

## Execution

* Lancer le fichier extract_liste_station.py qui va creer le fichier : liste_station.csv

* Creer un bucket dans le projet GCP et y déposer le fichier CSV

* Depuis le dataproc lancer le script suivant : load_liste_station_BigQuery.ipynb

* En local, lancer le script : extract_meteo_infoclimat.ipynb

* Depuis le dataproc lancer les script suivants:
    
    - transform_meteo_infoclimat_load_BigQuery.ipynb
    - transform_meteo_normale_load_BigQuery.ipynb



