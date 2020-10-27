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

#### 1 | On permet n'importe quelle violation du guide si elle augmente la lisibilité 
Le but principal de la recommandation est d'améliorer la lisibilité et de ce fait l'organisation et la qualité générale du code. Il est impossible de couvrir tous les cas spécifiques d'un guide général et le programmeur doit être flexible. Le lecteur est invité à faire montre de jugement. Si une pratique est inutile, inapplicable, voire contre-productive au regard des contraintes d'un projet ou des objectifs corporatifs, soyons assez intelligents pour y déroger.

# Conventions de nomenclature
## Conventions générales de nomenclature

#### 2 | Le nom des classes doit être en minuscules avec le premier caractère en majuscule, ainsi que le début de chaque nouveau mot
 ```Ligne, SystemeAudio, PointDeControle ```   
> Cette façon d'écrire est communément appelée UpperCamelCase. C'est une pratique courante de la communauté des développeurs de tous langages.

#### 3 | Le nom des variables, fonctions et paramètres est en minuscule. Chaque mot est séparé d'un tiret-bas _
```ma_variable, matrice_lue, une_fonction()```  
> D'autres langages commet C++ préfèrent le style lowerCamelCase pour les noms de variables et fonctions. Néanmoins en python c'est cette pratique qui est plus courante. À noter qu'il est possible d'utiliser le lowerCamelCase si c'est le style qui prédomine dans un fichier ou librairie déjà rédigé (le but est toujours d'augmenter la lisibilité).

#### 4 | Le nom des constantes est tout en majuscules, les mots séparés de tirets bas
```python
PI
I_WILL_NEVER_CHANGE
NOMBRE_AVOGADRO
```

#### 5 | Le nom des fonctions commence par un verbe suivi de mots séparés par des tirets_bas
```get_name(), obtenir_instance(), lire_nom(), calculer_largeur_totale()```  
> Attention aux verbes/mots peu évocateurs ou flous.

#### 13 | Les noms doivent être tous en anglais ou tous en français
Même si l'anglais est la langue préférée des développeurs, la langue française reste un bon choix. Cependant, nous ne recommandons pas les programmes bilingues.

#### 14 | Les variables qui ont une longue portée peuvent avoir des noms longs. Ceux avec une portée réduite peuvent avoir des noms courts
Les variables employées pour un stockage de données temporaires ou pour l'utilisation des indices doivent avoir un nom court. Un programmeur lisant une telle variable devrait être capable de supposer que sa valeur n'est pas employée au delà de ces lignes de code. Les variables temporaires pour des entiers sont i, j, k, m, n (mais jamais l, qui pourrait être confondu avec le chiffre un) et pour des caractères c et d.

## Conventions générales de nomenclature

#### 17 | Le terme « calculer » (« compute » en anglais) peut être employé dans des méthodes où quelque chose est calculé
```python
ensemble_valeurs.calculer_moyenne()
matrice.calculer_inverse()
```
> Donne au lecteur un indice immédiat que cette opération consomme potentiellement du temps, et si employée souvent, il pourrait utiliser le cache du résultat. L'emploi conséquent du terme améliore la lisibilité.

#### 18 | Le terme « trouver » (« find » en anglais) devrait être employé dans des méthodes où on effectue une recherche

```python
sommet.trouver_sommet_voisin()
matrice.trouver_petit_element()
noeud.trouver_court_chemin(noeud_destination)
```
> Fournit au lecteur un indice immédiat qu'il s'agit d'une méthode de recherche avec un minimum de calcul. L'emploi conséquent du terme améliore la lisibilité.


#### 21 | La forme plurielle devrait être employée pour les noms représentant une collection d'objets
```python
sommets = []
nouveaux_elements = []
mots_francais = {}
```
> Améliore la lisibilité puisqu'à partir du nom, l'utilisateur a une indication immédiate sur le type de la variable et les opérations qui peuvent être exécutées sur ses éléments.

#### 22 | Le préfixe « n » devrait être employé pour des variables représentant un nombre d'objets
```n_points, n_lignes```
> La notation est empruntée au monde des mathématiques où il existe une convention établie pour indiquer un nombre d'objets.

23 | Le préfixe *no* (ou le suffixe *No* en anglais) devrait être utilisé pour les variables représentant un numéro d'entité.
 ```python
 employee_no
 no_employe
 ```
> La notation est empruntée au monde des mathématiques où il existe une convention établie pour indiquer un nombre d'objets.



#### 24 | Les variables d'itération devraient être appelées i, j, k etc. (mais jamais l) 
```python
for i in range(10):
  for j in range(10):
    ...
```
> La notation est empruntée au monde des mathématiques où il existe une convention établie pour indiquer les itérateurs. Les variables nommées j, k, etc., devraient être employées pour des boucles imbriquées seulement.

#### 25 | Le préfixe « is » en anglais ou « est » en français devrait être employé pour les méthodes et variables booléennes.)
```python
est_visible, est_actif, est_trouve, est_ouvert
is_visible, is_active, is_found, is_open 
```
> L'utilisation du préfixe « est » résout un problème commun du mauvais choix du nom de la variable booléenne comme 'ETAT' ou 'INDICATEUR'. L'utilisation de « estEtat » ou « estIndicateur » simplement n'est pas suffisante, le programmeur est forcé de choisir des noms plus significatifs. L'équivalent anglophone est « is ».

Il existe des alternatives au préfixe « est » qui sont appropriées dans certaines situations. Ce sont les préfixes « a » (« has »), « peut » (« can ») et « doit » (« must ») :

```python
a_license()
peut_evaluer()
doit_quitter = false
 ```

#### 26 |	Des noms complémentaires doivent être utilisés pour des entités (fonctions, variables, etc.) complémentaires [1].
	
En anglais : get/set, add/remove, create/destroy, start/stop, insert/delete, increment/decrement, old/new, begin/end, first/last, up/down, min/max, next/previous, open/close, show/hide, suspend/resume, etc.

En français : obtenir/modifier, ajouter/retirer, creer/detruire, demarrer/arreter, incrementer/decrementer, ancien/nouveau, debut/fin, premier/dernier, haut/bas, min/max, prochain/precedent, ouvrir/fermer, etc.

Réduit la complexité par la symétrie des noms de ces entités.


#### 27 |	Les abréviations devraient être évitées dans les noms.
	
```python
calculerMoyenne() # À ÉVITER: calc_moy()
```
> Il y a deux types de mots à considérer. Tout d'abord, les mots relativement communs, généralement énumérés dans un dictionnaire non technique, ne doivent jamais être abréviés. Évitez d'écrire :

- cmd   à la place de   commande
- calc  à la place de   calculer
- cp    à la place de   copie
- e     à la place de   exception
- init  à la place de   initialiser
- pt    à la place de   point
- etc.
> De plus, certains termes, parfois spécifiques à un domaine particulier, sont davantage connus sous leur forme abrégée ou par leur acronyme. On devrait garder ces derniers sous leur forme courte. Ne jamais écrire :

- hypertext_markup_language  à la place de   html
- central_processing_unit    à la place de   cpu
- produit_interieur_brut     à la place de   pib
- etc.


#### 29 |	La négation des noms des variables booléennes doit être évitée.
    estNonErreur = True   # À ÉVITER
    estNonTrouve = False  # À ÉVITER
> Le problème survient quand on utilise l'opérateur de négation. Il en résulte une double négation plus difficile à comprendre, par exemple !estNonErreur. Il est beaucoup plus clair d'utiliser une variable booléenne comme estErreur et d'utiliser l'expression !estErreur, ou de trouver un autre nom comme estValide, au lieu d'une variable booléenne estNonErreur.


#### 32 |	Les fonctions (méthodes retournant quelque chose) devraient être nommées d'après ce qu'elles retournent et les procédures (méthodes ne retournant rien, c'est-à-dire void) d'après ce qu'elles font.
Améliore la lisibilité. Clarifie ce que la méthode devrait faire et également ce qu'elle n'est pas supposée faire, ce qui permet d'éviter plus facilement les effets secondaires non souhaités.

# Les fichiers
## Fichiers sources

#### 33 |	Un fichier source doit toujours comporter un entête de programme.
```Python
"""
 Programme qui détermine si une année lue du clavier est bissextile.
 \file   bissextile.py
 \author Dupont et Durant
 \date   22 janvier 2009
 Créé le 16 janvier 2008
"""
```
> L'entête se compose d'une série de commentaires qui décrivent le programme. Ces commentaires comportent toujours les informations suivantes : une brève description, le nom de fichier, le nom des auteurs, la date de mise à jour et la date de création. (L'entête en exemple suit le format Doxygen [5].)


#### 37 |	Le contenu d'un fichier ne doit pas dépasser 80 colonnes
>Ce nombre de colonnes est très commun pour les différents éditeurs, émulateurs de terminal, imprimantes et débogueurs. Ainsi, les fichiers partagés entre différents développeurs devraient respecter cette contrainte. Cela évite la perte de lisibilité qui peut se produire lorsque des retours de chariot non intentionnels se produisent sur les lignes trop longues quand un fichier passe d'un programmeur à l'autre.  

#### 38 | La césure des lignes trop longues doit être effectuée d'une manière lisible, logique et évidente [1].
La meilleure méthode *d’emballage* de longues lignes de code est d’utiliser la continuation implicite des lignes de Python, dans les parenthèses, crochets, et accolades (les délimiteurs). Si nécessaire, vous pouvez ajouter une paire supplémentaire de parenthèses autour de l’expression, mais utiliser un backslash \ est souvent plus esthétique. Soyez sûr(e) d’indenter proprement la ligne suivante. L’emplacement qui sera préféré pour un saut de ligne près d’un opérateur binaire est après
l’opérateur, pas avant. Par exemple :
```python
if width == 0 and height == 0 and \
   color == ’ red ’ and emphasis == ’ strong ’ or \
   highlight > 100:
```
On voudra aussi faciliter la lecture de combinés d'opérations comme dans ce cas:
```python
# Wrong:
# operators sit far away from their operands
income = (gross_wages +
          taxable_interest +
          (dividends - qualified_dividends) -
          ira_deduction -
          student_loan_interest)
# Correct:
# easy to match operators with operands
income = (gross_wages
          + taxable_interest
          + (dividends - qualified_dividends)
          - ira_deduction
          - student_loan_interest)
```
Parfois seuls 4 espaces sont nécessaire pour alligner les instruction avec le délémiteur ouvrant. Néanmoins il peut parfois être difficile de déterminer où le code imbriqué dans un if: débute; puisque l'alignement des instructions du if coincidera avec celui-ci. Par ex:
```python
x = 5
if (x > 3 and
    x < 10):
    print(x)
```
PEP8 nous donne 2 alternatives pour aider à la lisibilité
 - Ajouter un commentaire après la condition finale. À cause de la coloration du code par les IDE (Pycharm), cela mettra en évidence la séparation entre conditions booléennes et le code imbriqué
```python
x = 5
if (x > 3 and
    x < 10):
    # Both conditions satisfied
    print(x)
```
- Ajouter une indentation supplémentaire sur la ligne se poursuivant
```python
x = 5
if (x > 3 and
        x < 10):
    print(x)
```
D'autres exemples sont données [ICI](https://realpython.com/python-pep8/#indentation-following-line-breaks)

#### 42 |	Les énoncés d'import doivent se trouver seulement au début d'un fichier.
Pratique courante. Évite les effets non désirés causés par des énoncés d'imports « cachés » profondément dans un fichier source.

# Les déclarations
## Variables
### 46 |	Les variables devraient être initialisées lorsqu'elles sont déclarées
Cela permet d'être certain que les variables sont correctes en tout temps.
```python
x = 0;
y = 0.0;
c = '\0';
b = false;
# À ÉVITER: x, y, c
```
> Parfois, il est impossible d'initialiser une variable à sa déclaration. Dans ces cas, la variable devrait être laissée non initialisée plutôt que de l'initialiser à une valeur qui n'a pas de signification.

#### 47 |	Les variables ne doivent jamais avoir plus d'une signification.
Améliore la lisibilité en représentant chacun des concepts distinctement. Réduit également les probabilités d'erreurs causées par des effets secondaires du traitement sur l'ancienne signification de la variable.

#### 48 |	L'utilisation de variables globales doit être évitée.
Si vous avez besoin d'une variable globale, c'est fort probablement parce que votre code à un problème. L'utilisation de constantes globales est acceptée.

#### 51 |	Le test implicite de comparaison avec 0 (ou True) ne devrait être utilisé.
```python
if n_lignes != 0:  # À ÉVITER: if n_lignes
if valeur != 0.0:  # À ÉVITER: if valeur: 
```
> L'utilisation du test explicite est plus claire et donne une indication immédiate sur le type testé.
Le cas des variables booléennes est une exception à cette règle. Dans ce cas, il est tout à fait acceptable, et même préférable, de faire un test implicite, puisque le test est lui-même une expression booléenne :

```python
bool est_actif = input()
...
if est_actif:
    ...
```


#### 52 |	Les variables devraient être gardées vivantes le moins longtemps possible.

> Il est plus facile de contrôler les effets directs et les effets secondaires d'une variable si on garde les opérations sur cette dernière à l'intérieur d'une petite portée. En pratique, on essaie de limiter la portée d'une variable en la déclarant dans le bloc où elle est utilisée :
```python
# RECOMMANDÉ
...
for i in range(liste)
    ...

# À ÉVITER:
...
i = ...
...
while i < len(liste):
    ...


# RECOMMANDÉ
...
estActif = true
while estActif:
    ...
    uneVariable = 0    # Cette variable n'est pas utilisée en dehors du while
    ...
}
```


54 | Les variables de boucle devraient être initialisées immédiatement avant la boucle.

```python
estFini = false       # À ÉVITER: bool estFini = false; 
while not estFini:    # ... 
    ...               # while not estFini:
    ...               #     ... 
```


#### 56 |	L'utilisation de break et continue dans les boucles devrait être évitée
Ces énoncés devraient seulement être utilisés s'ils augmentent la lisibilité par rapport à leurs équivalents structurés. Le cas typique où on serait tenté d'utiliser ces instructions est celui où une situation exceptionnelle se produit à l'intérieur d'une boucle. Supposons par exemple qu'une méthode peut échouer :
```python
for element in liste:
    ...
    if not element.est_plaisant()
        break
    ...
```
Avant d'utiliser un break dans une telle situation, il faut d'abord se demander s'il n'est pas plus approprié de lancer une exception.

Il y a par contre un cas où le break s'impose. Il s'agit de la boucle inconditionnelle :
```python
est_termine = False
while true:
    ...
    if estTermine:
        break
    ...
}
```

## Instructions conditionnelles

#### 58 | Les expressions conditionnelles complexes doivent être évitées. Introduire plutôt des variables booléennes temporaires [1]
```python
est_fini = (no_Element < 0) or (no_element > max_Element)
bool est_entree_repetee = (noElement == dernierElement) and est_entree()

if (est_fini || est_entree_repetee)
... 

# À ÉVITER:
if ((noElement < 0) or (noElement >  maxElement)
  or noElement == dernierElement) and est_entree()
  ... 
```
> En assignant les expressions à des variables booléennes, le programme obtient de la documentation automatiquement. La condition sera plus facile à lire, à déboguer (possibilité de voir la valeur de chacun des tests individuellement) et à maintenir.


#### 61 | Des énoncés qui exécutent du traitement ne doivent pas se trouver à l'intérieur de conditions.
    sommets = assigner_sommets(liste, parametres);
    if sommets is None:
        ...

    // À ÉVITER:
    if assigner_sommets(liste, parametres) is None:
        ...
Les constructions conditionnelles contenant des énoncés qui font du traitement sont simplement très difficiles à lire.

## Divers

#### 62 | L'utilisation de nombres « magiques » dans le code doit être évitée. Les nombres autres que 0 et 1 peuvent être déclarés comme constantes nommées
    VALEUR_MAXIMALE = 15
    ...
    if valeur > VALEUR_MAXIMALE   # À ÉVITER: if (valeur > 15)
        erreur()
> Si le nombre n'a pas une signification évidente de lui-même, la lisibilité est améliorée par l'introduction d'une constante nommée.

#### 64 | Les nombres constants à virgule flottante doivent toujours être écrits avec un chiffre avant le point décimal.
	total = 0.5;     # À ÉVITER: total = .5; 
> Le système de nombres et d'expressions de python est emprunté des mathématiques et on devrait adhérer autant que possible aux conventions mathématiques. De plus, 0.5 est plus lisible que .5; il est beaucoup plus difficile de confondre 0.5 avec l'entier 5.
