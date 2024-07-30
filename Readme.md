# Description du projet
Ce projet a pour but de nettoyer les données en utilisant Power BI, plus spécifiquement Power Query, afin de visualiser les données pour identifier des tendances ou des anomalies. Le but final est de réaliser un tableau de bord intuitif permettant une meilleure compréhension des données.

# Nettoyage des données
Le fichier Superstore contient les données de ventes. Voici les étapes de nettoyage effectuées :

1. Élimination des doublons :

Suppression des doublons de la colonne Order_ID car elle représente la clé primaire et doit être unique.

2. Réorganisation des colonnes :

Réorganisation des colonnes pour une meilleure visibilité.

3. Suppression des colonnes inutiles :

Suppression des colonnes Field et Sub-Category1 car elles n'avaient pas de sens dans le contexte des données.

4. Conversion de type :

Changement du type de la colonne Order_Date en type Date.

5. Nettoyage des données clients :

Suppression des doublons de la colonne Customer_Name.

6. Rationalisation des données produits :

Suppression de la colonne Manufactor car elle était identique à la colonne Product_Name.
Séparation de la colonne Product_Name en deux colonnes distinctes : Manufactor et Product_Name.

7. Nettoyage des données géographiques :

Suppression des espaces dans la colonne Country.
Changement du nom de la colonne City City City en City et mise en majuscules des valeurs pour plus de clarté.

8. Nettoyage des données de livraison :

Changement du type de la colonne Days to Ship (Actual) en Whole Number et remplacement des erreurs par la moyenne de la colonne pour assurer que les jours restants de livraison soient un nombre entier.
Application du même traitement à la colonne Days to Ship (Scheduled).

9. Correction des statuts d'expédition :

Ajout d'une colonne conditionnelle pour corriger les erreurs de saisie dans la colonne Ship Status, ne gardant que les valeurs Early, On Time et Late. La colonne initiale a ensuite été supprimée.

10. Arrondissement des valeurs financières :

Arrondissement des valeurs de la colonne Profit per Order à deux chiffres après la virgule.

11. Correction des prévisions de ventes :

Remplacement des valeurs incorrectes de la colonne Sales F'cast par la moyenne de la colonne (399).

12. Nettoyage des données des ambassadeurs :

Promotion des en-têtes de la table Embassadors en première ligne.
Jointure de la table Embassadors avec la table Superstore par la colonne Region.

13. Jointures avec d'autres tables :

Jointure de la table Superstore avec la table Country_Rating en utilisant la colonne Country.
Jointure de la table Superstore avec la table Order_Codes en utilisant la colonne Order_ID.
Promotion des en-têtes des colonnes.

14. Multi-jointure avec la table des faits Superstore:

en utilisant les colonnes de jointure Sub_Category et Ship Status.

15. Gestion des espaces dans les colonnes :

Correction des colonnes Category et Region en utilisant la fonction Trim pour enlever les espaces, permettant une jointure correcte avec la table Targets.

16. Création de colonnes de relation :

Création de colonnes de relation dans chaque table utilisée pour les multi-jointures (Targets, Risk_Levels, et Superstore) afin de gérer les relations dans le modèle associé et assurer un bon filtrage des données.

17. Ajout d'une colonne de précision des ventes :

Ajout d'une colonne Sales Accuracy pour calculer la différence entre Sales et Sales F'cast.

### Visualisation des données

Après le nettoyage des données: 
nous avons créé plusieurs visualisations pour analyser et interpréter les données. 
Voici les principales visualisations réalisées :

1. Analyse des Ventes et des Bénéfices :

Nuage de Points Ventes vs Bénéfices: les ventes sur l'axe x et les bénéfices sur l'axe y pour identifier les fabriquants les plus rentables.
Ventes et Bénéfices par Catégorie & sous catégorie: Un graphique à barres empilées montrant les ventes et les bénéfices pour chaque catégorie & sous catégorie
Ventes et Bénéfices par Région : Une visualisation cartographique (heatmap) qui montre les ventes et les bénéfices dans différentes régions et pays.

2. Analyse des Clients :

Rentabilité des Clients : Un nuage de points montrant les ventes vs les bénéfices par client.
Ventes par Segment de Clients : Un graphique à secteurs  montrant la répartition des ventes par différents segments de clients.
une visualisation cartographique: qui montre la localisation de chaque client ou secteur de clients.
Meilleurs 10 Clients par Ventes : Un graphique à barres classant les top 10 clients par ventes totales.

3. Analyse du Ratio de Réduction et de Bénéfice :

Impact des Réductions sur les Bénéfices: Un nuage de points montrant la relation entre la réduction et le ratio de bénéfice.
Ratio de Bénéfice par Catégorie et Sous-Catégorie: Un graphique à barres groupées montrant le ratio de bénéfice pour chaque catégorie et sous-catégorie.

4. Analyse des Risques et des Objectifs :

Répartition des Niveaux de Risque: Un graphique à  montrant la répartition des différents niveaux de risque.
Evolution des Objectifs de Ventes: Un indicateur de jauge montrant le degré d'atteinte d'objectifs 2025 en fonction des ventes.
Ps: J'ai ajouté une info-bulle sous forme de donut pour montrer la répartition des sous catégories dans le grahique en barres de la répartition des niveaux de risques

5. Analyse Temporelle :

Ventes/bénéfices au Fil du Temps : Un graphique linéaire montrant la croissance(growth) YoY% (year over year) des ventes/bénéfices au fil du temps .
& les filtres de catégories, sous catégorie, pays & régions associés 

6. Analyse Prévisions vs Réel :

Prévisions des Ventes vs Ventes Réelles: Un graphique linéaire comparant les ventes réelles avec les ventes prévisionnelles au fil du temps.
Précision des Prévisions: Un graphique à barres montrant la différence entre les ventes prévisionnelles et les ventes réelles pour différents produits ou catégories.

7. Analyse des Expéditions :

Aperçu du Statut des Expéditions: Un graphique à secteurs montrant la répartition des statuts des expéditions (Early, On time & Late)
Tendances du nombre de commandes expédiées par mois : Un graphique linéaire montrant le nombre de commandes expédiées par mois.
Analyse des Modes d'Expédition: Un graphique à barres empilées montrant les ventes ou les bénéfices par différents modes d'expédition

# Conclusion
Ce projet a permis de transformer les données brutes du fichier Superstore en un ensemble de données nettoyées et prêtes à être visualisées dans Power BI. Les étapes de nettoyage et de transformation ont assuré l'intégrité et la cohérence des données, facilitant ainsi leur analyse et leur interprétation.

Grâce aux visualisations créées, nous avons pu identifier des tendances clés et des anomalies dans les données de ventes. Les insights obtenus de ces visualisations peuvent être utilisés pour prendre des décisions informées et stratégiques, améliorer les opérations commerciales, et optimiser les performances globales.