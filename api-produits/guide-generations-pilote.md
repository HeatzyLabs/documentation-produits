---
title: Guides des générations du Pilote
nav_order: 6
---

## Distinguer les différentes générations de Heatzy Pilote

Pour éviter la confusion lors de création d'outils web et domotique, ce document a pour but de détailler les différences et les points communs entre chaque module Heatzy Pilote et Acova Elec'Pro.  
Tous ces modules partagent une base commune et sont compatibles avec l'app Heatzy (V8.x) ainsi que les Open API Heatzy.  
Néanmoins, certaines générations de modules disposent de fonctions qui leur sont propres.  
Ci-dessous, une liste exhaustive de toutes les générations de Heatzy Pilote et leurs fonctions associées.

### Pilote 1ʳᵉ génération

Il s'agit de la première itération de modules Heatzy, produits en 2016, jusqu'en 2018. Ces modules disposent de moins de fonctions que les générations suivantes.

**Data points**

| Data point | Description                                     |
| :--------- | :---------------------------------------------- |
| mode       | Mode de chauffe (confort, éco, hors-gel, arrêt) |

\*_pour plus de détails sur les data points, voir la [documentation API](https://heatzylabs.github.io/documentation-produits/api-https/)_

**Particularités**  
La programmation présente dans l'app est entièrement gérée par le serveur. Il n'y a donc pas de data point dédié à la programmation.

### Pilote de 2ᵈᵉ et 3ᵉ génération

Ces deux générations sont communément appelées "Pilote v2" par la communauté Heatzy.  
Ces modules apportent beaucoup de nouvelles fonctions par rapport à la première génération :  
 \- Stockage de la programmation et de la date dans la mémoire du produit  
 \- Ajout des dérogations mode vacances et mode boost  
 \- Ajout de la fonctionnalité de verrouillage produit

**Data points**

| Data point   | Description                                           |
| :----------- | :---------------------------------------------------- |
| mode         | Mode de chauffe (confort, éco, hors-gel, arrêt)       |
| pX_dataY     | Données de programmation                              |
| derog_mode   | Activation des dérogations (mode vacance, mode boost) |
| derog_time   | Temps restant à une dérogation                        |
| lock_switch  | Verrouillage du produit                               |
| time_week    | Jour actif                                            |
| time_hour    | Heure de la journée                                   |
| timer_switch | Activation de la programmation                        |

\*pour plus de détails sur les data points, voir la [documentation API](https://documenter.getpostman.com/view/10809108/SzYXYfP6)\*

**Particularités**  
La programmation est enregistrée dans la puce du produit. Le produit enregistre également la date et l'heure. Cette mise à jour permet d'obtenir un suivi de la programmation plus stable.  
Les pilotes de 3eme génération sont identiques a la seconde. Ils disposent cependant d'une architecture SoC.

### Pilote de 4ᵉ génération

Il s'agit de la dernière génération de pilote. Ce module a été produit en 2022 et apporte surtout des avancées techniques. Ses API sont très similaires aux précédentes générations.  
Il est facile à différencier grâce à son témoin de connexion de couleur verte (et non bleue).

**Data points**

| Data point   | Description                                           |
| :----------- | :---------------------------------------------------- |
| mode         | Mode de chauffe (confort, éco, hors-gel, arret)       |
| pX_dataY     | Données de programmation                              |
| derog_mode   | Activation des dérogations (mode vacance, mode boost) |
| derog_time   | Temps restant à une dérogation                        |
| lock_switch  | Verrouillage du produit                               |
| time_week    | Jour actif                                            |
| time_hour    | Heure de la journée                                   |
| timer_switch | Activation de la programmation                        |

\*pour plus de détails sur les data points, voir la [documentation API](./api-pilote.md)\*

**Particularités**  
La puce Wifi du module a été mise à jour pour faciliter l'appairage et permettre une plus grande compatibilité avec les récentes normes Wifi. L'appairage se fait maintenant via Bluetooth.  
Les modules de 4eme génération permettent en plus de passer les radiateurs en mode confort-1 et confort-2.

### Liste complète de tous les modules "Pilote"

Pour connaitre la génération d'un module Heatzy Pilote ou Acova Elec' Pro, il suffit de le connecter à internet puis de passer par les [open API](https://documenter.getpostman.com/view/10809108/SzYXYfP6) pour obtenir les informations relatives au produit. "Product_name" et "Product_key" permettent d'identifier les différentes générations de module.

Les API des générations 2 et 3 sont 100% identiques  
Les API des générations 4 possèdent exactement les mêmes data points que les générations 2 et 3\. À la seule différence que les modes confort-1 et confort-2 sont supportés.

| Module    | Date | Product Name  | Product Key                      | Generation | Remarque                                                                                                                                                                                                        |
| :-------- | :--- | :------------ | :------------------------------- | :--------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Pilote    | 2016 | Heatzy        | 9420ae048da545c88fc6274d204dd25f | 1          | Pas de mode boost, vacances, verrouillage. La programmation est enregistrée sur les serveurs Heatzy. Pas entièrement compatible avec la fonction groupe (mise à jour 7.0)                                       |
| Pilote    | 2018 | Pilote2       | 51d16c22a5f74280bc3cfe9ebcdc6402 | 2          | Mode boost, vacances et verrouillage. La programmation est enregistrée dans le produit.                                                                                                                         |
| Elec’ Pro | 2018 | Elec_Pro      | 4fc968a21e7243b390e9ede6f1c6465d | 2          | Idem.                                                                                                                                                                                                           |
| Pilote    | 2019 | Pilote_Soc    | b9a67b6ce24b437d9794103fd317e627 | 3          | Idem.                                                                                                                                                                                                           |
| Elec’ Pro | 2019 | Elec_Pro_Soc  | b8c6657b66c34148b4dee64d615cefc7 | 3          | Idem.                                                                                                                                                                                                           |
| Pilote    | 2022 | Pilote_Soc_C3 | 46409c7f29d4411c85a3a46e5ee3703e | 4          | Mise à jour de la puce Wifi. Appairage via Bluetooth. Le témoin de connexion est vert pour mieux faire la différence avant l’appairage. Ajout des modes confort-1 et confort-2. Plus grande compatibilité Wifi. |
| Elec’ Pro | 2023 | Elec_Pro_Ble  | 9dacde7ef459421eaf8dc4bea9385634 | 4          | Idem.                                                                                                                                                                                                           |
