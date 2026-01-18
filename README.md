## Guide d'identification de biodiversité du Québec

Projet permettant de prendre des données d'observations de biodiversité acquises par la science citoyenne et en faire un guide d'identification.

### Utilisation 

Pour ce projet, assurez-vous d'avoir R version >= 4.4.1. 

#### Préparation de l'environnement 

Faites une copie de ce projet (cloner). 

#### Installation de dépendances 

Pour faire des analyses spatiales, il faut installer des librairies de base. En particulier, la plus importante est [GDAL](https://gdal.org/en/stable/). 

##### macOS

Installez [Homebrew](https://brew.sh), puis exécuter : 

```bash
brew install pkg-config gdal pandoc
```

##### Ubuntu : 
```bash
sudo apt-get update
sudo apt-get install libgdal-dev libgeos-dev libproj-dev pandoc
```

##### Windows : 
- Installer [RTools](https://cran.r-project.org/bin/windows/Rtools/) 


Une fois le projet cloné et ouvert dans votre IDE de choix, installez le progiciel `renv`. 
Le progiciel `sf` doit être installé à partir de la `source` (pour bien lier les bibliothèques spatiales installées dans l'état) avec les commandes suivantes.

```r
# install.packages("renv") # Installation au besoin
library(renv)

# Installation de sf avec les dépendances (important pour lier correctement les libraires GEOS, GDAL et PROJ)
renv::install(
  packages = "sf", 
  repos = "https://cran.rstudio.com/", 
  type = 'source', 
  prompt = FALSE
)


```

Ensuite, vous pouvez préparer l'environnement avec le reste des progiciels utilisés, on utilise `renv::restore()`. 
Si vous avez le message `It looks like you've called renv::restore() in a project that hasn't been activated yet but there is a renv.lock`, 
vous pouvez choisir l'option `Activate the project and use the project library`.

```r
# Installation des progiciels nécessaires pour le projet 
renv::restore() # Permet de restaurer la session avec les mêmes versions

# Choisir l'option : 'Activate the project and use the project library'
```

#### Données 

Les données préparées sont disponibles dans le projet et prêtes à être utilisées. Des scripts d'accompagnement permettent de voir comment les données ont été préparées (voir `scripts/partie_1/Prearation_*.R`).


#### Scripts d'analyses

Chaque partie a son script (très long : suit la logique du blogue Évologie : peut changer dans le futur)

