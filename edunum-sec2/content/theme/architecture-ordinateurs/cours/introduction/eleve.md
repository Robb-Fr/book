# Introduction

Dans ce chapitre, nous aborderons la question de l'**architecture des ordinateurs**, c'est à dire les multiples couches physiques qui rendent possibles des opérations numériques aussi complexes que celles qu'effectuent à chaque instant nos smartphones. 

Comme vous avez pu le voir dans le chapitre lié à la **représentation de l'information** tout ce qui apparaît sur votre écran n'est qu'une suite de 0 et de 1. Pour comprendre comment ces **nombres binaires** sont traités par l'ordinateur, il faut avoir en tête que les ordinateurs sont construits en plusieurs **couches** successives, comme un mille feuille, dont chacune possède ses propres règles. 

```{figure} media/abstractionlight.png
---
height: 400px
width: 250px
---
Les différents niveaux d'abstraction de l'informatique, en partant des électrons, jusqu'aux "programmes", que l'on appelle aussi aujourd'hui "applications". 
```
Dans ce chapitre nous nous concentrerons sur les couches de **bas niveau**, et tenterons de remonter progressivement jusqu'aux **couches logicielles**. 


## De quoi sont faits les nombres binaires ? 

Les ordinateurs ne comprennent que les nombres binaires. La lettre "A", par exemple, est pour ces derniers une suite de 0 et de 1. Même chose pour une image, une vidéo, une chanson, et ainsi de suite. Mais alors comment ces 0 et ces 1 sont-ils stockés et manipulés physiquement ? De quelle matière sont-ils faits ? Un indice : que mettez-vous dans votre smartphone pour le faire fonctionner ? De l'essence ? Du gaz ? De l'énergie solaire ? 

De l'électricité.

```{figure} media/iphonecpu.jpeg
---
height: 350px
width: 500px
---
Vos photos, vos vidéos, vos messages, tout ce que vous consultez sur votre téléphone portable, sont traitées par un processeur similaire au modèle A9 de Apple, commercialisé dans les iPhone SE. 
```

```{figure} media/datacenter.jpeg
---
height: 350px
width: 500px
---
Vos likes, vos partages, vos vidéos transmises via des applications telles que Whatsapp, Instagram, Tik Tok, Snapchat, Youtube, sont stockées dans des centres de données aux quatre coins de la planète. 
```

## Électricité et nombres binaires

Les nombres binaires, au niveau le plus élémentaire, sont donc de l'électricité. Mais pourquoi avoir choisi des 0 et des 1 comme alphabet ? Quel rapport avec l'électricité ? 

En informatique, si nous avons choisi d'utiliser un code binaire ça n'est pas par hasard. Ce sont les deux signaux les plus élémentaires que l'on puisse transmettre avec l'électricité. Soit le courant passe, soit il ne passe pas. Ouvert ou fermé, allumé ou éteint, 1 ou 0. 

```{panels}
:column: col-lg
Pourquoi pas un code ternaire ? 
^^^
On aurait pu choisir un code possédant plus que deux signaux différents. Si on choisissait, par exemple, trois signaux, on pourrait les coder par l'électricité en mesurant un courant faible, un courant moyen, un courant fort. Le problème est qu'on augmenterait ainsi les possibilités de se tromper dans la mesure, et d'interpréter un courant moyen pour un courant fort, ou inversément. Puisque l'électricité permet une vitesse de transmission par signal très grande, il est plus performant de garder deux positions clairement distinctes que l'on peut transmettre très vite, plutôt que trois positions avec un risque de confusion plus élevé. 
```

## Le transistor

Le **transistor** est la brique de base de construction des systèmes informatiques. Développé dans les années 1940 dans les [laboratoires Bell](https://fr.wikipedia.org/wiki/Laboratoires_Bell), aux Etats-Unis, ce composant électronique est à l'origine d'une révolution dans la taille, la fiabilité, et les performances générales des ordinateurs de l'époque. 

```{figure} media/transistor.jpeg
---
height: 350px
width: 500px
---
Différents modèles de transistor. On les reconnaît à leurs trois "pattes" aussi appelées : émetteur, base, collecteur. 
```

Le **transistor** fonctionne comme un robinet d'eau qui peut être ouvert ou fermé. Si on l'ouvre le courant passe, si on le ferme il ne passe pas. 

````{dropdown} Pour aller plus loin
Vidéo facultative qui explique en détail ce qui se passe dans les matériaux qu'on appelle "semi-conducteurs". *Note : contenu en anglais, mais en cours de traduction (elliot)*.
```{youtube} 33vbFFFn04k
```
````

```{figure} media/transistorgif.gif
---
height: 350px
width: 500px
---
En appliquant un courant qui va de la **base** à **l'émetteur** (en rose pâle), on permet au courant de circuler entre le collecteur et l'émetteur (appelés ainsi parce que l'émetteur *émet* des électrons, et le collecteur les *collecte*). Envoyer du courant dans la **base** c'est donc "ouvrir" le transistor. 
```

De par sa capacité à être ouvert ou fermé, le **transistor** fonctionne comme une brique fondamentale dans la construction de systèmes informatiques permettant de transmettre, stocker et manipuler des nombres binaires. 


`````{panels}
:column: col-lg
Des transistors presque invisibles
^^^
Chercher à se représenter la taille des transistors utilisés dans les microprocesseurs actuels n'a pas d'intérêt tellement ils sont petits. À titre d'exemple, disons simplement que le microprocesseur Apple A9 (igure 35) en possède six milliards.
````{dropdown} Zoom sur un transistor
```{youtube} Fxv3JoS1uY8
```
````
`````

## Des transistors aux portes logiques

Un **transistor** seul ne peut représenter qu'un bit d'information. Oui ou non, ouvert ou fermé, 1 ou 0. Mais si l'on rassemble plusieurs **transistors**, on peut construire des systèmes logiques qui nous permettent d'exprimer des relations logiques plus avancées, comme la conjonction, la disjonction, la négation. C'est ce qu'on appelle des **portes logiques**. 

```{figure} media/andgate.svg
---
height: 100px
width: 200px
---
Ceci est une porte logique "ET", qui exprime la conjonction. C'est à dire que les deux transistors qui la composent (A & B) doivent être "ouverts" pour que le courant passe. 
```
En connectant entre eux les **transistors** de diverses manières, on est capable de faire que le courant se déplace dans un circuit de façon maîtrisée. Ce qui nous permet, à terme, de construire des programmes qui génèrent certaines "sorties" quand on leur donne certaines "entrées". 

```{figure} media/andgatetransistor.png
---
height: 300px
width: 200px
---
Voilà le schéma de construction d'une porte logique "ET", à partir de deux transistors. Si les deux transistors sont "ouverts", le courant passe. 
```

## Des portes logiques aux tables de vérité

Les **portes logiques** sont des circuits extrêmement basiques faits de **transistors** qui permettent d'exprimer des relations logiques tels que la conjonction, la disjonction ou la négation. 

```{panels}
:column: col-lg
Rien de plus logique que la logique
^^^
Même si vous ne les appelez pas ainsi, vous utilisez tous les jours des relations logiques de conjonction, de disjonction et de négation. La conjonction c'est "l'intersection logique" de deux propositions. Si vous dites "je vais à la piscine si *il fait beau* ET *mes amies m'accompagnent*", vous utilisez la conjonction. Au contraire, si vous dites "je vais à la piscine si *il fait beau* OU *mes amis m'accompagnent*", vous utilisez la disjonction, qui est comme une sorte de "somme logique" de deux propositions. La négation est encore plus évidente, puisque la proposition "je ne vais pas à la piscine" est simplement la négation, ou l'inverse, de la proposition "je vais à la piscine". 
```

Pour simplifier la représentation de ces relations logiques, on les exprime sous la forme de tables de vérité.

| $A$ | $B$ | $Q$ |
| :-: | :-: | :-: |
| 0   | 0   | 0   |
| 1   | 0   | 0   |
| 0   | 1   | 0   |
| 1   | 1   | 1   |

Dans le tableau qui précède, si on reprend notre exemple de la piscine, on pourrait dire que A représente "il fait beau", B représente "mes amies m'accompagnent", et le résultat Q est "je vais à la piscine". 1 signifie qu'une proposition est vraie, 0 qu'elle est fausse. Le tableau ci-dessus représente donc l'opération logique ET, ou conjonction. 

```{panels}
:column: col-lg
Une application pour s'exercer
^^^
https://booleangame.com/
```

## La construction de la mémoire

Les transistors, les portes logiques et leur représentation en tables de vérités, permettent de manipuler des 0 et des 1 au niveau physique. Tant qu'un courant électrique se déplace dans nos circuits, nous sommes capables de le transformer, de le laisser passer ou de l'arrêter, dans le but d'exprimer des portes "ouvertes" ou des portes "fermées" et donc des nombres binaires.  

Mais comment faire pour stocker cette information ?

Pour comprendre comment la mémoire des ordinateurs fonctionne, il faut commencer par la classer en deux grandes catégories. La mémoire **volatile**, et la mémoire **non volatile**. La mémoire **volatile** s'efface quand la machine et éteinte. La mémoire **non volatile**, elle, persiste. Si votre smartphone s'éteint alors que vous êtes en train de retoucher une photo, ces retouches disparaissent. Elles étaient stockées sur la mémoire **volatile**. Par contre, au moment où vous avez sauvegardé ces retouches, elles s'inscrivent dans la mémoire **non volatile**. 

## Les verrous informatiques

Certains circuits sont construits pour "bloquer" une information, ce qui nous permet de la garder en mémoire, tant que le circuit est alimenté par l'électricité. On appelle ces circuits des **verrous**. Le plus élémentaire est le verrou S-R, pour "set", "reset", en anglais. 

```{logic}
:height: 150
:mode: tryout

{
  "in": [
    {"pos": [50, 30], "id": 8, "name": "R", "val": 0},
    {"pos": [50, 120], "id": 9, "name": "S", "val": 1}
  ],
  "out": [
    {"pos": [240, 40], "id": 10, "name": "Q"},
    {"pos": [240, 110], "id": 11, "name": "Q'"}
  ],
  "gates": [
    {"type": "NOR", "pos": [120, 40], "in": [0, 1], "out": 2},
    {"type": "NOR", "pos": [120, 110], "in": [4, 5], "out": 6}
  ],
  "wires": [[8, 0], [9, 5], [2, 4], [2, 10], [6, 1], [6, 11]]
}
```

Dans l'exemple ci-dessus, à partir du moment où on a "ouvert" la porte S (donc qu'on a "set", c'est à dire "établi" l'état initial), la sortie Q est 1. Si on avait une ampoule à cet endroit, elle serait allumée. Maintenant, même si on "ferme" la porte S, Q reste bloqué sur 1. On a donc créé une forme de mémoire. La seule façon "d'éteindre" la sortie Q est d'ouvrir R (donc de "reset", c'est à dire réinitialiser le système). 

Voici une vidéo qui illustre ce principe de verrou S-R. *Note : oui, elle est en anglais, mais j'ai contacté l'auteur pour ajouter des sous-titres français, et on pourrait même la regarder sans le son pour illustrer (elliot)*.

```{youtube} KM0DdEaY5sY
:start: 4:58
```




