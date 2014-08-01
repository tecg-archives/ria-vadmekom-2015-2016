# HEPL : Rich Internet Applications

> Coding guidelines

* * *

**Note:** the school where the course is given, the [HEPL](http://www.provincedeliege.be/hauteecole) from Liège, Belgium, is a french-speaking school. From this point, the instruction will be in french. Sorry.

* * *

Dans le cadre du cours de RIA, nous allons être amené à produire pas mal de code, principalement du code JavaScript.

Vous avez sûrement déjà entendu parler de convention de codage : il s'agit de documents qui régissent la façon d'écrire du code au sein d'une entreprise/équipe/projet. Vous pouvez par exemple consulter les [conventions très complètes](https://github.com/styleguide) au sein des équipe chez GitHub.

Tôt ou tard, vous serez confrontés à ce genre de conventions, alors autant s'y habituer de suite.

Les conventions qui suivent sont celles du cours de RIA, à suivre scrupuleusement.
Tout code rendu dans le cadre de travaux se *doit* de suivre ces conventions et le non-respect de celles-ci influencera la cote du travail. Vous êtes prévenus. :)

* * *

## Principes généraux

* Tous les fichiers sont encodés en UTF-8, sans BOM.
* Indentation en espaces. 1 niveau d'indentation = 4 espaces.
* Les commentaires sont importants, mais il faut commenter intelligement : un commentaire inutile prend de la place pour rien.
* On nomme les variables en **anglais**, et, si possible, mais facultativement, les commentaires aussi.
* Les *TODO* sont conseillés, mais il faut les détailler : rien ne dit que c’est vous qui repasserez dessus.
* Tout projet de code doit être stocké sur un gestionnaire de version comme *Git*, via la plateforme [GitHub](http://github.com).
* Corriger un fichier qui ne respecte pas les conventions n'est **jamais** une perte de temps.

### KISS: Keep it simple, stupid!

*La simplicité est la sophistication suprême* : un code simple est plus lisible et plus facile à maintenir.

### DRY: Don't repeat yourself

Si la même portion de code se retrouve deux fois ou plus dans un script, on en fait une fonction. Si la même portion de code se retrouve deux fois ou plus dans une classe, on en fait une méthode.

### YAGNI: You aren't gonna need it

Rien ne sert de coder une méthode qui n'a pas d'implémentation ou d'utilité immédiate.

### Don't be shy, ask!

Il n'y a pas de honte à demander de l'aide, surtout avant d'attaquer une nouvelle fonctionnalité.  
Il ne devrait jamais y avoir une portion de code qui ne soit pas couverte par au moins deux personnes.

* * *

## Fichiers HTML

* Indentation stricte.
* Respect de la syntaxe XML :
	* pas de balises d'ouverture sans balise de fermeture,
	* balises et attributs en minuscules,
	* les attributs booléens doivent avoir une valeur.
* Le contenu d'un élément block doit être à la ligne, celui d'un élément inline peut être au choix à la ligne ou non. (exception acceptable pour la balise `<p>`).
* À l'exception notable d'*html5shiv* pour IE, les balises `<script>` sont déclarées en fin de `<body>`.

* * *

## Fichiers CSS et dérivés

* Indentation stricte.
* Préférer les propriétés raccourcies (`font`, `background`, `margin`…).
* Quand on utilise des propriétés `-vendor-prefix`, on n'oublie pas de mettre la propriété finale de la spec à la fin.
* Pas de hack, sauf si *vraiment* pas le choix. Préférer les *commentaires conditionnels* de HTML pour rajouter des feuilles de styles spécifiques ou des classes sur l'élément `<html>`.
* En *Less*, *Sass* ou *Stylus* :
	* On utilise des variables explicites, et si elles sont globales, on les définit en tête de module ou dans un fichier séparé pour les *superglobales*.
	* Nommage des variables en **camelCase**.

* * *

## Fichiers JavaScript et dérivés

* JavaScript est un langage peu rigoureux, il faut l'être à sa place.
* `"use strict"` est obligatoire.
* Encapsulation de tout le code, aucune empreinte globale, et, si nécéssaire, créer un **namespace**.
* Indentation stricte.
* Chaînes de caractère en double quotes (`"string"`).
* Ouverture de bloc sur la même ligne, fermeture sur une nouvelle ligne.

**Exemple :**

	var test = function( param ) {
		// some code
	};
	
* Toutes les variables d'un bloc sont déclarées au début de celui-ci.
* Puisque JavaScript est un langage à *typage faible*, on ne *transtype* pas une variable, et il est conseillé d'utiliser la **notation hongroise** pour les variables, en préfixant le nom d'une variable par son type :
	* sVariable (`string`)
	* iVariable (`number`)
	* bVariable (`boolean`)
	* aVariable (`array`)
	* oVariable (`object`)
	* fVariable (`function`)
	* gVariable (`Google API Object`)
	* $Variable (`jQuery Object`)
	* mVariable (`mixed`)
* Les variables sont nommées en **camelCase**, les classes en **PascalCase**.
* Si on veut stocker des données dans le code HTML (avec parcimonie et sagesse), on utilise les attributs `data-`.
* Attention à ne pas laisser des appels à la `console` dans les fichiers en production.
* Les scripts doivent être validés par *JSHint* avant mise en production.

* * *
