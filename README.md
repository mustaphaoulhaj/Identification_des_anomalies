# Détection des anomalies sur le marché boursier

## Introduction
Ce projet a pour objectif de détecter les anomalies dans les données boursières des différentes entreprises. Ces anomalies peuvent signaler des fluctuations inhabituelles des prix ou des volumes de transactions, souvent dues à des événements spécifiques ou à des conditions de marché exceptionnelles.

## Source des données
Les données utilisées dans ce projet proviennent de Yahoo Finance. Nous avons collecté des informations allant d'**août 2023** à **août 2024** pour les actions et entreprises suivantes :

- **TSLA** : Tesla, Inc.
- **NKE** : Nike, Inc.
- **UPS** : United Parcel Service, Inc.
- **MC** : LVMH Moët Hennessy Louis Vuitton.

## Méthodologie
La détection des anomalies peut se concentrer sur les mouvements de prix significatifs et les volumes de transactions inhabituels. Pour ce faire, nous utiliserons la méthode du **Z-score**, qui identifie les anomalies en mesurant le nombre d'écarts-types séparant une donnée de la moyenne. Un seuil couramment utilisé pour détecter une anomalie est **un Z-score dont la valeur absolue est inférieure à 2**.

*Rappel*                                                                                                            
                                                                                                                    
Le Z-score est défini comme suit :

$$                                                                                                                  
\text{Z-score} = \frac{X - µ}{\sigma}                                                                               
$$                                                                                                                  

où :
- $X$ est la valeur du point de données (prix ou volume).
- $µ$ est la moyenne des données.
- $\sigma$ est l'écart-type des données.

Nous avons également calculé un score de risque pour évaluer le niveau de risque associé à chaque action, basé sur la fréquence et l'amplitude des anomalies détectées dans les données de prix et de volumes. Voici notre méthode de calcul :
1. Comptage des anomalies dans les données de prix et de volumes sur une période donnée.
2. Prise en compte de l'amplitude des anomalies, soit leur écart par rapport à la moyenne (en Z-score).
   
La formule pour le score de risque est alors la suivante :

$$
\text{Score de Risque} = \frac{1}{N} \sum_{i=1}^{N} |Z_i|
$$

où :
- $N$  est le nombre total d'anomalies détectées pour l'action.
- $Z_i$ est le Z-score de chaque anomalie.

## Résultats

Parmi les actions analysées, **Nike (NKE)** présente le plus grand risque, avec un score de 1,00, indiquant des anomalies fréquentes et significatives. En revanche, **Tesla (TSLA)** affiche le risque le plus faible à 0,00, signifiant l'absence d'anomalies détectables.

Les anomalies observées pour **MC** en août 2024 sont principalement dues à des retards de production, impactés par une chute générale des marchés causée par des tensions économiques et géopolitiques mondiales.

En août 2024, **Nike** a rencontré des anomalies dans ses performances en raison de l'événement des Jeux Olympiques à Paris, ce qui a significativement impacté ses résultats. En décembre 2023, pour stimuler les ventes en fin d'année, Nike a lancé des promotions, soldes et nouveaux produits, entraînant une hausse de la demande et des fluctuations dans ses performances.

Les anomalies dans les performances de **Tesla** à la fin du premier trimestre 2024 sont attribuées à une croissance plus lente, des taux d'intérêt élevés, des temps d'arrêt des usines, une concurrence accrue en Chine, et un scepticisme général envers les véhicules électriques.

Les anomalies dans les performances de **UPS** au début du quatrième trimestre sont dues à l'augmentation des dépenses liées aux coûts élevés du carburant et aux problèmes persistants dans la chaîne d'approvisionnement.

## Conclusion

Pour détecter, analyser et interpréter les anomalies sur le marché boursier, il est essentiel de comprendre leur signification. Ces anomalies peuvent révéler des opportunités ou des risques : une hausse soudaine d’une action peut signaler une opportunité d’investissement, tandis qu’une baisse inattendue peut indiquer des problèmes ou des changements dans le sentiment du marché.
