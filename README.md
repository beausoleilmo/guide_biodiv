## Guide d'identification de biodiversité du Québec

Projet permettant de prendre des données d'observations de biodiversité acquises par la science citoyenne et en faire un guide d'identification.


### Utilisation 

#### Préparation de l'environnement 

Faites une copie de ce projet (cloner). 

#### Installation de dépendances 

Pour faire des analyses spatiales, il faut installer des librairies de base. En particulier, la plus importante est [GDAL](https://gdal.org/en/stable/). 

##### macOS
```bash
brew install pkg-config gdal
```

##### Ubuntu : 
```bash
sudo apt-get update
sudo apt-get install libgdal-dev libgeos-dev libproj-dev
```

##### Windows : 
- Installer [RTools](https://cran.r-project.org/bin/windows/Rtools/) 


Une fois le projet cloné et ouvert dans votre IDE de choix, installez le progiciel `renv`. 
Le progiciel `sf` doit être installé à partir de la `source` (pour bien lier les bibliothèques spatiales installées dans l'état) avec les commandes suivantes.

```r
# install.packages("renv") # Installation au besoin
library(renv)

# Installation de sf avec les dépendances 
renv::install("sf", repos = "https://cran.rstudio.com/", type = 'source')

```

Ensuite, vous pouvez préparer l'environnement avec le reste des progiciels utilisés.

```r
# Installer les libraires nécessaires pour le projet 
renv::restore() # Permet de restaurer la session avec les mêmes versions
```

#### Données 

Les données préparées sont disponibles dans le projet et prêtes à être utilisées. Des scripts d'accompagnement permettent de voir comment les données ont été préparées (voir `scripts/partie_1/Prearation_*.R`).

