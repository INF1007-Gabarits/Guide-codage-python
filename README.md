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


| 3 | Le nom des variables, fonctions et paramètres est en minuscule. Chaque mot est séparé d'un tiret-bas "_" |
|----|:----------------------------------------------------|
|    | ```ma_variable, matrice_lue, une_fonction()```         |
|    | D'autres langages commet C++ préfèrent le style lowerCamelCase pour les noms de variables et fonctions. Néanmoins en python c'est cette pratique qui est plus courante. À noter qu'il est possible d'utiliser le lowerCamelCase si c'est le style qui prédomine dans un fichier ou librairie déjà rédigé (le but est toujours d'augmenter la lisibilité).|

| 5 | Le nom des fonctions commence par un verbe suivi de mots séparés par des tirets_bas. |
|----|:----------------------------------------------------|
|    | ```get_name(), obtenir_instance(), lire_nom(), calculer_largeur_totale()```         |
|    | Attention aux mots peu évocateurs. |

| 13 | Les noms doivent être tous en anglais ou tous en français. |
|----|:----------------------------------------------------|
|    | 	Même si l'anglais est la langue préférée des développeurs, la langue française reste un bon choix. Cependant, nous ne recommandons pas les programmes bilingues. |

| 14 | Les variables qui ont une longue portée peuvent avoir des noms longs. Ceux avec une portée réduite peuvent avoir des noms courts. |
|----|:----------------------------------------------------|
|    | Les variables employées pour un stockage de données temporaires ou pour l'utilisation des indices doivent avoir un nom court. Un programmeur lisant une telle variable devrait être capable de supposer que sa valeur n'est pas employée au delà de ces lignes de code. Les variables temporaires pour des entiers sont i, j, k, m, n (mais jamais l, qui pourrait être confondu avec le chiffre un) et pour des caractères c et d. |

## Conventions générales de nomenclature

<table> <tr><th> 17 </th><th>
Le terme « calculer » (« compute » en anglais) peut être employé dans des méthodes où quelque chose est calculé. </th></tr>
<tr> <td>  </td>
<td>

```python
    ensemble_valeurs.calculer_moyenne(); 
    matrice.calculer_inverse();
```
</td></tr><tr><td>  </td>
<td>
Donne au lecteur un indice immédiat que cette opération consomme potentiellement du temps, et si employée souvent, il pourrait utiliser le cache du résultat. L'emploi conséquent du terme améliore la lisibilité.
</td></tr></table>

<table> <tr><th> 18 </th><th>
Le terme « trouver » (« find » en anglais) devrait être employé dans des méthodes où on effectue une recherche. </th></tr>
<tr> <td>  </td>
<td>

```python
    sommet.trouver_sommet_voisin(); 
    matrice.trouver_petit_element(); 
    noeud.trouver_court_chemin(noeud_destination); 
```
</td></tr><tr><td>  </td>
<td>
Fournit au lecteur un indice immédiat qu'il s'agit d'une méthode de recherche avec un minimum de calcul. L'emploi conséquent du terme améliore la lisibilité.
</td></tr></table>

<table> <tr><th> 21 </th><th>
La forme plurielle devrait être employée pour les noms représentant une collection d'objets. </th></tr>
<tr> <td>  </td>
<td>

```python
    sommets = []
    nouveaux_elements = []
    mots_francais = {}
```
</td></tr><tr><td>  </td>
<td>
Améliore la lisibilité puisqu'à partir du nom, l'utilisateur a une indication immédiate sur le type de la variable et les opérations qui peuvent être exécutées sur ses éléments.
</td></tr></table>

| 22 | Le préfixe « n » devrait être employé pour des variables représentant un nombre d'objets. |
|---|:----------------------------------------------------|
|    | ```n_points, n_lignes```         |
|    | La notation est empruntée au monde des mathématiques où il existe une convention établie pour indiquer un nombre d'objets.|

| 23 | Le préfixe *no* (ou le suffixe *No* en anglais) devrait être utilisé pour les variables représentant un numéro d'entité. |
|----|:----------------------------------------------------|
|    | ```employee_no, no_employe```         |
|    | La notation est empruntée au monde des mathématiques où il existe une convention établie pour indiquer un nombre d'objets.|



<table> <tr><th> 24 </th><th>
Les variables d'itération devraient être appelées i, j, k etc. (mais jamais l) </th></tr>
<tr> <td>  </td>
<td>

```python
for i in range(10):
  for j in range(10):
    ...
```
</td></tr><tr><td>  </td>
<td>
La notation est empruntée au monde des mathématiques où il existe une convention établie pour indiquer les itérateurs. Les variables nommées j, k, etc., devraient être employées pour des boucles imbriquées seulement.
</td></tr></table>

<table> <tr><th> 25 </th><th>
Le préfixe « is » en anglais ou « est » en français devrait être employé pour les méthodes et variables booléennes.) </th></tr>
<tr><td>  </td>
<td>
  
 
```python
  est_visible, est_actif, est_trouve, est_ouvert
  is_visible, is_active, is_found, is_open 
```
L'utilisation du préfixe « est » résout un problème commun du mauvais choix du nom de la variable booléenne comme 'ETAT' ou 'INDICATEUR'. L'utilisation de « estEtat » ou « estIndicateur » simplement n'est pas suffisante, le programmeur est forcé de choisir des noms plus significatifs. L'équivalent anglophone est « is ».

Il existe des alternatives au préfixe « est » qui sont appropriées dans certaines situations. Ce sont les préfixes « a » (« has »), « peut » (« can ») et « doit » (« must ») :

```python
  a_license()
  peut_evaluer()
  doit_quitter = false
 ```
</td></tr></table>


