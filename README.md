# Polarisation politique sur les réseaux 
## Analyse des discours politiques sur X (Twitter) et du contexte macroéconomique


## I. Introduction, contextualisation et problématique

Au cours des dernières années, les réseaux sociaux sont devenus des acteurs centraux du débat politique contemporain. Parmi eux, **X (anciennement Twitter)** occupe une place particulière en raison de son usage intensif par les responsables politiques, les journalistes, les militants et les citoyens pour commenter l’actualité en temps réel. Cette centralité explique pourquoi la plateforme a fait l’objet de **restrictions ou d’interdictions temporaires dans plusieurs pays**, notamment lors de périodes de fortes tensions sociales, économiques ou politiques.

Des pays comme l’Iran, la Turquie, l’Inde ou encore certains États africains ont, à différentes reprises, limité l’accès à Twitter lors de manifestations de masse, d’élections contestées ou de crises institutionnelles. Ces décisions reposent sur l’idée que la plateforme peut contribuer à **l’amplification de la polarisation politique**, à la diffusion rapide de discours extrêmes et à l’escalade des conflits sociaux. En effet, X se caractérise par une circulation rapide de messages politiques souvent peu modérés, favorisant la viralité des contenus les plus clivants.

L’algorithme de recommandation de X joue un rôle déterminant dans ces dynamiques. En mettant en avant les contenus générant de fortes réactions émotionnelles — colère, indignation, provocation — la plateforme favorise la création de **chambres d’écho**, dans lesquelles les utilisateurs sont principalement exposés à des opinions similaires aux leurs. Ces mécanismes sont renforcés par des **biais cognitifs**, tels que le biais de confirmation, qui incitent certains individus à adopter des positions de plus en plus radicales ou provocatrices afin d’accroître leur visibilité ou leur influence politique.

Depuis le rachat de Twitter par Elon Musk en 2022, ces phénomènes ont suscité un débat renouvelé. Les changements dans les politiques de modération et la promotion d’une liberté d’expression plus large ont alimenté les inquiétudes concernant une possible **hausse des discours extrêmes, complotistes ou haineux**. Toutefois, attribuer l’augmentation de la polarisation uniquement aux choix algorithmiques ou institutionnels de la plateforme serait réducteur.

Cette évolution s’inscrit également dans un **contexte macroéconomique et géopolitique dégradé**. La pandémie de COVID-19, la guerre en Ukraine, les perturbations des chaînes d’approvisionnement mondiales, ainsi que le retour d’une inflation élevée ont profondément affecté les conditions de vie des populations. Par exemple, l’inflation annuelle a dépassé **8 % aux États-Unis et dans plusieurs pays européens en 2022**, tandis que les inquiétudes liées au pouvoir d’achat et à l’emploi se sont accrues dans un contexte de ralentissement économique. Ces tensions économiques peuvent renforcer la défiance envers les institutions et favoriser l’adhésion à des discours politiques plus radicaux.

Ainsi, la problématique centrale de ce projet est la suivante :

**Dans quelle mesure la polarisation politique observée sur X est-elle liée à la dégradation des conditions macroéconomiques, en particulier l’inflation et le chômage ?**


## II. Données utilisées

### 1. Données issues des réseaux sociaux - Tweets politiques collectés à partir de X (Twitter) 
- Données textuelles : contenu des tweets
- Métadonnées temporelles : date de publication
  
Les données utilisées ne sont pas collectées directement via l’API officielle de X, dont l’accès est devenu payant et restrictif ces dernières années. Elles proviennent d’un jeu de données secondaire accessible publiquement sur le site nnnnnn , regroupant des tweets collectés antérieurement. Ce choix méthodologique permet de garantir l’accès aux données tout en respectant les contraintes techniques et institutionnelles actuelles de la plateforme

### 2. Données macroéconomiques 
- Inflation (indice des prix à la consommation – CPI)
- Taux de chômage
  
  Ces données proviennent de la base FRED (Federal Reserve Economic Data), cette combinaison permet d’analyser le lien entre conditions macroéconomiques et polarisation politique sur les réseaux sociaux.


## III. Packages utilisés

- **`tidyverse`** : pour la manipulation, nettoyage et transformation des données
- **`tidytext`** : analyse textuelle et analyse de sentiment
- **`ggplot2`** : visualisation des résultats
- **`quantmod`** : importation des données macroéconomiques depuis FRED
- **`lubridate`** : gestion des dates
- **`rmarkdown`** : génération des slides et du rapport HTML

## IV. Outils

Le projet est réalisé sous **R**, en mobilisant des méthodes de collecte de données, d’analyse textuelle, de statistiques descriptives et de visualisation.  
Ce travail s’inscrit dans une démarche exploratoire visant à mieux comprendre les interactions entre dynamiques économiques et comportements politiques sur les plateformes numériques.

Le projet est entièrement automatisé grâce au script principal (run_project.R) qui exécute l’ensemble du pipeline d’analyse : nettoyage des données issues de X, calcul de l’indice de polarisation, importation des données macroéconomiques et génération des visualisations et des slides HTML.
Une tâche planifiée via le package cronR permet d’exécuter ce script automatiquement à une fréquence mensuelle, garantissant ainsi la mise à jour régulière des résultats lorsque de nouvelles données deviennent disponibles.

## V. Méthodologie

La méthodologie adoptée dans ce projet repose sur une approche empirique en plusieurs étapes, combinant analyse textuelle des données issues des réseaux sociaux et intégration d’indicateurs macroéconomiques.

Dans un premier temps, les tweets politiques sont nettoyés et prétraités afin de garantir la qualité du corpus. Cette étape inclut la suppression des observations manquantes, la standardisation des textes (conversion en minuscules) et la gestion des dates de publication. Les données sont ensuite agrégées à une fréquence mensuelle, permettant une mise en cohérence avec les données macroéconomiques.
Dans un second temps, une analyse de sentiment est appliquée aux tweets afin de capter la tonalité émotionnelle des discours politiques. À partir de cette analyse, un indice de polarisation est construit, mesurant l’intensité et la conflictualité du discours politique. Un indice élevé reflète une prédominance de sentiments négatifs, souvent associée à des positions idéologiques plus extrêmes, tandis qu’un indice plus faible correspond à des périodes de discours plus modérés.
Les indicateurs de polarisation sont ensuite fusionnés avec les données macroéconomiques, en particulier l’inflation et le taux de chômage, issues de la base FRED. Cette combinaison permet d’étudier l’évolution conjointe de la polarisation politique et des conditions économiques.
Enfin, l’analyse repose sur une approche descriptive et économétrique, mobilisant des régressions linéaires simples afin d’explorer les relations statistiques entre la polarisation politique et les variables macroéconomiques, sans prétention causale stricte. L’ensemble du processus est automatisé afin de garantir la reproductibilité et la cohérence des résultats.


### Nettoyage et préparation des données

Les tweets sont d’abord nettoyés afin de garantir la qualité de l’analyse :
- suppression des observations manquantes
- standardisation des textes (minuscules)
- conversion des dates
- filtrage des contenus non exploitables

Cette étape permet d’obtenir un corpus textuel cohérent, prêt pour l’analyse de sentiment et la construction des indicateurs.


### Construction de l’indice de polarisation

Un **indice de polarisation** est construit à partir de l’analyse de sentiment des tweets. Cet indice mesure l’intensité conflictuelle du discours politique en comparant la part de sentiments négatifs et positifs dans les messages publiés.

Un indice élevé reflète un discours plus polarisé et conflictuel, souvent associé à des positions idéologiques extrêmes, tandis qu’un indice plus faible correspond à des périodes de discours plus modérés.


### Agrégation temporelle et fusion avec les données macroéconomiques

Les indicateurs de polarisation sont agrégés à une fréquence mensuelle afin de correspondre à la périodicité des données macroéconomiques. Les séries de polarisation sont ensuite fusionnées avec les données d’inflation et de chômage, permettant une analyse conjointe de l’évolution des discours politiques et du contexte économique.


### Analyse économétrique

Une analyse descriptive est complétée par des régressions linéaires simples visant à étudier la relation entre la polarisation politique et les variables macroéconomiques. L’objectif est d’évaluer si les périodes de tensions économiques sont associées à une intensification des discours polarisés sur la plateforme.


### Automatisation du projet

Le script `run_project.R` permet d’exécuter l’ensemble du pipeline :
- nettoyage des tweets
- calcul de l’indice de polarisation
- importation des données macroéconomiques
- fusion des données
- génération automatique des slides HTML

Cette automatisation garantit la **reproductibilité** complète du projet.

### Limites

- Données issues d’une seule plateforme
- Approche basée sur l’analyse de sentiment, qui simplifie la complexité idéologique
- Absence d’identification causale stricte

## VI. Conclusion et usages

Ce projet met en évidence le rôle central des réseaux sociaux dans la structuration du débat politique contemporain et suggère un lien entre la dégradation des conditions macroéconomiques et l’intensification de la polarisation politique. Il constitue une base solide pour des analyses futures intégrant des méthodes de NLP plus avancées ou une comparaison entre plusieurs plateformes.


### Auteurs

**Meriem Wahbi**  **Manal Rebbah**
Master M1 – Analyse et Politiques Économiques
