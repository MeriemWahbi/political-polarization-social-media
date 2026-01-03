# Polarisation politique sur Reddit et contexte macroéconomique

## Présentation du projet
Depuis l’essor des réseaux sociaux, certaines plateformes sont devenues de véritables chambres d’écho pour les sujets politiques. Les utilisateurs y sont souvent exposés à des contenus qui confortent leurs opinions, tandis que les algorithmes amplifient ces tendances, renforçant la polarisation idéologique et parfois la radicalisation.

Ce projet vise à quantifier la polarisation politique sur Reddit et à analyser ses liens avec des indicateurs macroéconomiques tels que l’inflation et le chômage. Nous classons les publications et commentaires selon les axes politiques gauche, centre et droite, afin d’étudier comment les discussions évoluent dans différents contextes économiques.

Grâce à des méthodes de traitement automatique du langage (NLP) et d’analyse statistique, le projet explore si les périodes de tension économique coïncident avec une augmentation de la polarisation et identifie les mécanismes qui influencent les débats en ligne.


## Données
La base principale est constituée de posts et commentaires issus de Reddit, collectés via l’API officielle et des outils de scraping adaptés. Reddit a été choisi en raison de la nature textuelle et argumentative de ses échanges, qui en fait un terrain pertinent pour l’analyse des discours politiques.  

Les discussions sont sélectionnées à partir de mots-clés liés aux crises économiques, aux débats idéologiques et aux enjeux sociopolitiques contemporains, ce qui permet d’identifier de manière endogène les communautés (subreddits) où ces débats émergent.

## Méthodologie
Un dictionnaire idéologique a été construit pour classer les expressions et termes employés dans les discussions en trois catégories : gauche, centre et droite.  
À partir de ce dictionnaire, un indicateur synthétique de polarisation est calculé, mesurant la dispersion relative des discours idéologiques dans le temps. Cela permet de suivre l’intensité et la structure de la polarisation politique sur une base mensuelle.  

Les données issues de Reddit sont ensuite mises en relation avec des indicateurs macroéconomiques, notamment l’inflation et le chômage, provenant de bases officielles. L’objectif est d’explorer l’existence de corrélations entre périodes de tensions économiques et évolution de la polarisation idéologique en ligne.

## Outils
Le projet est réalisé sous **R**, en mobilisant des méthodes de collecte de données, d’analyse textuelle, de statistiques descriptives et de visualisation.  
Ce travail s’inscrit dans une démarche exploratoire visant à mieux comprendre les interactions entre dynamiques économiques et comportements politiques sur les plateformes numériques.
