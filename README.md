Population en belgique
================

<!-- Do not edit de README.md -->

## Contexte

L’office belge de statistique , Statbel, diffuse des données fiables sur
l’économie, la société et le territoires belges.

Pour en apprendre plus sur l’office belge de statistique, vous pouvez
consulter le lien suivant :
<https://statbel.fgov.be/fr/propos-de-statbel>

Nous souhaitons analyser l’évolution de la population belge entre le 1
janvier 1992 et le le 1 janvier 2019.

## Attendu

  - Se connecter et extraire des données de la base de données

  - Créer un objet spécifique à l’analyse de données de la population
    belge. Cet objet sera de type `belpop`

  - remanier les données à l’aide de fonctions génériques

  - réaliser une fonction générique pour afficher un graphique
    spécifique au objet `belpop`

  - réaliser un petit rapport qui décrit votre analyse de la population
    belge

### Utilisation de la base de données

Vous devez vous connecter et extraire les tables d’intérêts afin de
pouvoir les utiliser.

    data/popu_belge_db.sqlite

### Objet `belpop`

Vous devez créer un objet `belpop` spécifique qui va permettre de
réaliser des fontions générique pour remaniement des donnnées et faire
un graphique générique.

#### Remanier les données

Le service de statistique propose les différents tableaux de recensement
avec un forme similaire. On peut mettre en avant les problèmes suivant
auxquels vous allez devoir trouver une solution :

  - le nom des colonnes ne peut pas contenir de majuscule (utilisez les
    expressions régulières pour corriger ce problème)
  - le nom des colonnes ne peut pas contenir d’espace (utilisez les
    expressions régulières pour corriger ce problème)
  - le nom des colonnes ne peut pas contenir d’accent (utilisez les
    expressions régulière pour corriger ce problème)
  - les variables qui débutent par `Population au 01 janvier` sont des
    variables qui recensent la population belge d’une année
    particulière. Il faut une variable qui recense les dates et une
    variables qui recense la population. (utilisez la fonction gather et
    les expressions régulières pour corriger ce problème)

<!-- end list -->

``` r
read(file = "data/bel.csv") %>.%
  knitr::kable(.)
```

| Région                       | Population au 01 janvier 1999 | Population au 01 janvier 2009 | Population au 01 janvier 2019 |
| :--------------------------- | ----------------------------: | ----------------------------: | ----------------------------: |
| Région flamande              |                       5926838 |                       6208877 |                       6589069 |
| Région de Bruxelles-Capitale |                        954460 |                       1068532 |                       1208542 |
| Région wallonne              |                       3332454 |                       3475671 |                       3633795 |

#### Réaliser un graphique générique

Vous devez réaliser une fonction générique plot() en R de base ou une
fonction autoplot() en ggplot

### Raport d’analyse