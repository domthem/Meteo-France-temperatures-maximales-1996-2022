# Meteo-France-temperatures-maximales
Evolution des températures journalières maximales en France depuis 1996

Météo France met à disposition du public , en source ouverte , différentes données parmi lesquelles  les “Données Synop essentielles OMM” . Il s’agit  de données émises sur le réseau de l’ OMM (Organisation Météorologique Mondiale) , à la fréquence d’un message toutes les trois heures sous un format codé spécifique , appelé SYNOP , à partir des données enregistrées par des stations météorologiques terrestres . 
Météo France diffuse également ces données sous forme de fichiers mensuels au format csv , que l’on peut télécharger sur son site à l’adresse suivante Données Publiques de Météo-France - Données SYNOP essentielles OMM (meteofrance.fr)

Nous nous proposons ici d'utiliser les données de températures au sol pour visualiser les évolutions sur la période s’étendant de début 1996 - données les plus anciennes mises à disposition - à fin 2022 , en un certain nombre de stations.

Les grandes étapes de l’étude sont :

a-La sélection des stations à partir des données fournies par Météo-France : ici on se limitera aux stations de France métropolitaine . La sélection est faite en ne conservant que les stations situées à moins de 1000 km de Paris.[Notebook : meteo_1_selection_des_stations]
Finalement le nombre de stations retenues est de 40.

b-L’analyse de la qualité des données sur une première base de dimension réduite (quelques années ) : à l’issue de cette phase on décide de se limiter à la variable de température au sol et d’éliminer les stations dont les données sont très incomplètes.[Notebook : meteo_2_qualite_data]

c-La concaténation de l’ensemble des fichiers mensuels de janvier 1996 à décembre 2022 .[Notebook : meteo_3_concaténation_fichiers_synop]

d-La construction de la base de données finale : pour chaque jour et chaque station on conserve une température à savoir la valeur maximale des 8 mesures disponibles ( une toutes les trois heures) . Les autres données de la base sont les identifiants et noms des stations ainsi que leurs coordonnées géographiques (latitude , longitude et altitude) .

On dispose donc d’une température maximale par jour sur une période de 27 années en 40 points du territoire français.[Notebook : meteo_4_construction de la base]

Aucune donnée supplémentaire , en provenance d’une autre source n’est ajoutée à cette base.


e L’ analyse finale , dont les résultats sont présentés ci-dessous
  
  

     
Résultats de l'analyse de données.[Notebook : meteo_5_analyse_finale]

  

1-Variabilité et distribution des températures maximales
   
L’analyse de variance (Anova) montre un effet significatif des 5 variables testées , latitude , longitude , altitude , mois et année [meteo_tableau1] . 
  
La température maximale journalière varie avec l’année et la tendance est à l’augmentation , comme le montre la corrélation  [meteo_tableau2]

L’effet “année” est nettement inférieur aux effets “Latitude” , effet de la position en latitude de la station météo , et “Mois” , effet saisonnier de variation des températures en cours d’année, mais est tout à fait significatif.

Quelques éléments pour illustrer ce point :
En 2022 , les températures maximales mesurées en septembre  vont de 18°C , en moyenne , pour Lille-Lesquin de latitude 50.570 ,  à 25°C  pour Ajaccio de latitude 41.918 . [meteo_graphe1]

au cours de cette même année les valeurs moyennes mensuelles des températures maximales ont varié de 6 °C en janvier à 27°C en juillet pour la station de Lille-Lesquin [meteo_graphe2],[meteo_graphe3]

l’écart pour  Lille -Lesquin entre les moyennes annuelles des années 1996 et 2022  , statistiquement significatif , est de 3.8°C [meteo_graphe5]


Globalement on observe pour chaque  station un glissement au cours des années  de la distribution des températures maximales journalières vers des valeurs plus élevées .[meteo_graphe4]
On peut l'analyser à travers deux paramètres , d’une part la moyenne annuelle des températures , d’autre part le nombre de jours par année où la température maximale dépasse 30°C

Remarque : .Les conclusions statistiques sont valides pour l’ensemble des stations mais , pour alléger certains graphiques, le choix a été fait de présenter les résultats de 4 stations seulement ( Lille-Lesquin, Nantes-Bouguenais,Dijon-Longvic,Marignane).

2- Evolution des moyennes annuelles

La tendance est à l’augmentation des moyennes annuelles pour les différentes stations [meteo_graphe5] [meteo_tableau2].

L’écart entre les deux  années extrêmes de la période analysée ,1996 et 2022 , est significatif pour toutes les stations [meteo_tableau3] . Il se situe entre 1.8°C et 4.5°C avec une moyenne de 3.1°C , 2 stations sont en dessous de 2°C d’écart et 3 stations sont au dessus de 4 °C [meteo_graphe5]

Il n’y a pas d’effet de la latitude sur cet écart mais par contre un effet de la longitude , comme le montre l’ anova [meteo_tableau4] . La carte [meteo_graphe7] , avec un codage couleur fonction de la classe d’écart illustre ce point.


3-Evolution du nombre de jours à plus de 30°C

L’analyse Anova montre un effet significatif des variables latitude,longitude et année [tableau_meteo5]

Le tableau des corrélations indique une tendance à l’augmentation au cours des années[tableau_meteo6]

Les graphiques réalisés pour les 4 stations sélectionnées [meteo_graphe8] illustrent cette tendance et montrent  la singularité de l’année 2003 , année considérée à l’époque comme année de canicule , avec une surmortalité démontrée durant l’été 2003 (référence…)

La série de cartes simplifiées , avec un codage de couleur par classe de 10 jours , illustrent également cette tendance à l’augmentation avec une propagation vers le nord.
