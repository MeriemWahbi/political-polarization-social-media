# Polarisation politique sur Reddit et contexte macroéconomique

## Présentation du projet
Ce projet de data analyse étudie la polarisation politique sur les réseaux sociaux, à partir des discussions publiées sur Reddit, et analyse son lien avec le contexte macroéconomique.  
Dans un contexte marqué par l’intensification des débats idéologiques et la montée des tensions politiques, les réseaux sociaux sont aujourd’hui un espace central de production et de diffusion des opinions politiques.  

L’objectif du projet est de proposer une mesure quantitative de la polarisation idéologique en ligne et d’examiner son évolution dans le temps en relation avec les chocs et dynamiques économiques.

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
