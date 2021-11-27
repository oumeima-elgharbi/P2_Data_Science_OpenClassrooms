# Projet 2 : Analysez des données de systèmes éducatifs

Auteur : Oumeima EL GHARBI
Date : novembre 2021
Formation Data Scientist OpenClassrooms (diplôme RNCP de niveau 7 - Master).

## Présentation des livrables
Lien de référencement du projet : https://openclassrooms.com/fr/paths/164-data-scientist#path-tabs

Ce projet contient trois livrables : un notebook de nettoyage, un notebook d'exploration des données et un support PowerPoint pour la soutenance du projet devant le jury.

## Contexte :
L'entreprise "academy" cherche à s'étendre à l'international. Dans ce premier projet, vous ferez des recommandations stratégiques à partir de données de systèmes éducatifs.

## Outils : Jupyter Notebook, librairies Pandas, Matplotlib, Seaborn

## Avant de lire les notebooks Jupyter : 
Récupérer le DataSet : il faut aller sur ce lien : https://datacatalog.worldbank.org/search/dataset/0038480
Télécharger l'archive intitulée "Edstats_csv.zip" contenant les 5 fichiers csv dont nous nous servons pour notre étude.
Puis placer ces 5 fichiers csv dans un dossier nommé "csv".

- "EdStatsCountry"
- "EdStatsCountry-Series.csv" à renommer => "EdStatsCountry_Series"
- "EdStatsData"
- "EdStatsFootNote"
- "EdStatsSeries"

## Lancer le notebook de nettoyage "P2_01_nettoyage" en premier.
Ce premier notebook sert à explorer les données brutes.
Traitement des données à l'aide de DataFrames de la librairie Pandas

Nous avons initialement 241 "country code" référençant des pays et des régions du monde. Nous allons d'abord effectuer un premier filtre en ne conservant que les 75 pays riches ('high income').

Ensuite, nous allons effectuer un deuxième filtre en choisissans parmi les 4000 indicateurs disponibles 30 indicateurs donnant des informations sur la population de ces pays riches, le taux d'utilisation d'internet et le niveau d'éducation.

Nous filtrons ensuite par taille de population. Nous retirons tous les pays ayant moins de 10 millions d'habitants : nous ne conservons que 15 pays riches de plus de 10 millions d'habitants.

Ensuite, nous effectuons trions ces 15 pays par :
- nombre d'habitants de 15 à 64 ans,
- taux d'utilisation d'internet, 
- nombre total d'étudiants inscrits dans l'enseignement secondaire (lycée), 
- nombre total d'étudiants inscrits dans l'enseignement tertaire (post-BAC), 
- le taux de poursuite d'études après le secondaire (pourcentage d'étudiants qui continuent les études après le BAC),
- la projection (prédiction) du pourcentage de jeunes de 20 à 39 ans diplômés post-BAC.

Nous attribuons une note (de 1 à 15) à chaque pays en fonction de ces 6 variables.
Par exemple : le pays qui a le plus grand nombre d'habitants aura 15, le second 14, ... et le dernier 1.

A l'isssue de cette attributions de score, nous ne gardons que 7 pays (ceux qui ont eu un score supérieur ou égal à celui de la France qui nous sert de référence). 
Le score total est sur 90 car il y a 15 pays et 6 indicateurs.

## Lancer le notebook d'exploration et d'analayse "P2_02_exporation".

Nous présentons dans ce second notebook des graphiques pour visualiser le classement des 7 pays pré-sélectionnés en fonction des autres par indicateur.

- Affichage de diagrammes à bâtons (barplot) et de digrammes en boîtes (boxplot).
- Fusion des 6 DataFrames en un DataFrame final pour afficher la matrice de corrélation.
- Affichage et interprétation de la matrice de corrélation.
- Pour les trois pays ayant eu le meilleur classement : deux graphiques supplémentaires.
Le premier graphique présente le taux d'utilisation d'internet en fonction des années (sur tout l'historique disponible dans le DataSet) : graphique de type lineplot pour suivre l'évolution de ces trois pays sur plus de 20 ans.
Le deuxième graphique présente le nombre d'étudiants inscrits dans l'enseignement supérieur en fonction des années (lineplot).
