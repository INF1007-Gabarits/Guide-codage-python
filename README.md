# Guide de codage Python
## Généralités
Le Python [PEP8](https://www.python.org/dev/peps/pep-0008/) est notre référence de base. Néanmoins certaines règles/conventions seront un peu plus explicites ici.
Vous pouvez consulter une version en français [ICI](http://nguyen.univ-tln.fr/share/Python/pep8.pdf)


Le format de ce guide est inspiré du "Guide de codage C++" du cours INF1005c, rédigé par François-R Boyer et Michel Gagnon
Ce guide a été rédigé par Mathieu Bélanger et Simon Legault. Il est maintenu à jour par l'équipe de chargé de laboratoire du cours INF1007.

Il y a plusieurs raisons qui font la nécessité de normaliser la façon de rédiger du code :
- Augmenter la lisibilité et la compréhension du code source.
- Code prédictible et facilement modifiable.

# Disposition des recommandations
Les recommandations sont groupées par matière et chaque recommandation est numérotée pour lui faciliter l'accès pendant les mises à jour. La disposition pour les recommandations est comme suit:

| no | Brève description de la recommandation              |
|----|:----------------------------------------------------|
|    | ```­­­ Un exemple de code s'il y a lieu```         |
|    | Motivations, contexte et informations additionnelle |

## Importance des recommandations
Les directives qui se retrouvent dans ce document n'ont pas toutes la même importance. Certaines doivent être respectées, alors que d'autres sont plutôt souhaitables.

# Recommandations générales

| 1 | On permet n'importe quelle violation du guide si elle augmente la lisibilité |
|----|:----------------------------------------------------|
|    | Le but principal de la recommandation est d'améliorer la lisibilité et de ce fait l'organisation et la qualité générale du code. Il est impossible de couvrir tous les cas spécifiques d'un guide général et le programmeur doit être flexible. Le lecteur est invité à faire montre de jugement. Si une pratique est inutile, inapplicable, voire contre-productive au regard des contraintes d'un projet ou des objectifs corporatifs, soyons assez intelligents pour y déroger.|

# Conventions de nomenclature
## Conventions générales de nomenclature

| 2 | Le nom des classes doit être en minuscules avec le premier caractère en majuscule, ainsi que le début de chaque nouveau mot. |
|----|:----------------------------------------------------|
|    | ```Ligne, SystemeAudio, PointDeControle ```         |
|    | Cette façon d'écrire est communément appelée UpperCamelCase. C'est une pratique courante de la communauté des développeurs de tous langages. |


| 3 | Le nom des variables, paramètres et fonctions est en minuscule. Chaque mot est séparé d'un tiret-bas "_" |
|----|:----------------------------------------------------|
|    | ```ma_variable, matrice_lue, une_fonction()```         |
|    | D'autres langages commet C++ préfèrent le style lowerCamelCase pour les noms de variables et fonctions. Néanmoins en python c'est cette pratique qui est plus courante. À noter qu'il est possible d'utiliser le lowerCamelCase si c'est le style qui prédomine dans un fichier ou librairie déjà rédigé (le but est toujours d'augmenter la lisibilité).|

| 13 | Les noms doivent être tous en anglais ou tous en français. |
|----|:----------------------------------------------------|
|    | 	Même si l'anglais est la langue préférée des développeurs, la langue française reste un bon choix. Cependant, nous ne recommandons pas les programmes bilingues. |

| 14 | Les variables qui ont une longue portée peuvent avoir des noms longs. Ceux avec une portée réduite peuvent avoir des noms courts. |
|----|:----------------------------------------------------|
|    | Les variables employées pour un stockage de données temporaires ou pour l'utilisation des indices doivent avoir un nom court. Un programmeur lisant une telle variable devrait être capable de supposer que sa valeur n'est pas employée au delà de ces lignes de code. Les variables temporaires pour des entiers sont i, j, k, m, n (mais jamais l, qui pourrait être confondu avec le chiffre un) et pour des caractères c et d. |






























