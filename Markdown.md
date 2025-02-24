# **Apprendre le Markdown**

## Emphases

Mettre en italique : *mot* ou _mot_
Mettre en gras : **mot** ou __mot__
Mélange des 2 : **_mot_**

Exposant : <sup>mot</sup>

Souslignage : [Underline]{.underline} avec classe ou <ins>mot</ins> ou ++mot++

Surlignage : [Mark]{.mark} avec classe ou ==Mot== ou <mark>mot</mark>

Barré : ~~mot~~ --> ~

Protéger un caractère : mettre \

### Exemples :

**Everyone _must_ attend the meeting at 5 o’clock today.**

I am totally awesome.*

\* for certain very small values of awesome

## Paragraphes

On fait simplement un Entrée et on met \ en fin de phrase.

### Exemples :

I have eaten\
the plums\
that were in\
the icebox

## Titres

Pour créer des titres de différentes tailles : mettre plusieurs #

### Exemples :

# After the Big Bang
A brief summary of time
## Life on earth
10 billion years
## You reading this
13.7 billion years

## Blockquotes ou blocs de citation

Mettre une phrase en blockquote : > phrase

### Exemples :

My favorite Miss Manners quotes:

> Allowing an unimportant mistake to pass without comment is a wonderful social grace.
>
> Ideological differences are no excuse for rudeness.

## Listes

Listes non ordonnées : 

- objet 
+ objet2  
* objet3

Listes ordonnées : 

1. Objet
2. Objet2

1) Objet

Listes de tâches :

- [ ] Non fait
- [x] Fait

### Exemples :

- Flour
- Cheese
- Tomatoes

Four steps to better sleep:
1. Stick to a sleep schedule
2. Create a bedtime ritual
3. Get comfortable
4. Manage stress

## Liens

URL directe: <URL>

URL derrière texte : [Texte](URL)

Lien de référence URL : [Texte][numero de reference]
Fin du texte (par convention) : 
[numero de reference]:URL

### Exemples :

You can do anything at <https://html5zombo.com>

The [University of Rwanda](http://www.ur.ac.rw) was formed in 2013

[Hurricane][1] Erika was the strongest and longest-lasting tropical cyclone in the 1997 Atlantic [hurricane][1] season.

[1]:https://w.wiki/qYn

## Images

Similiaire aux liens, commence par un !
![Texte qui apparait quand l'image n'est pas disponible](test.png)

### Exemples :

![](https://commonmark.org/help/images/favicon.png)


![][1]

[1]: https://commonmark.org/help/images/favicon.png

## Emojis

Mettre un emoji : :EMOJICODE:

### Exemples :

@octocat :+1: This PR looks great - it's ready to merge! :shipit:

## Règles Horizontales

Mettre au moins 3 : - ou * ou _

### Exemples :

___
* * *
- - - - - -

## Code

Code en ligne : `code`
Code en bloc : 

    code

ou
```
Code
```

### Exemples :

When `x = 3`, that means `x + 2 = 5`

    Jeff  15
    Sam   11
    Robin  6

A loop in JavaScript:
```
var i;
for (i=0; i<5; i++) {
  console.log(i);
}
```
## Listes imbriquées

Reprendre ce qu'on sait des listes et y rajouter des espaces :

* Objet
  * Sous Objet
* Objet2
  1. Sous Objet
  2. Sous Objet2

### Exemples :

+ World Cup 2014
  1. Germany
  2. Argentina
  3. Netherlands
+ Rugby World Cup 2015
  1. New Zealand
  2. Australia
  3. South Africa

## Tables

Simplement :

| En-tête 1                   | En-tête 2                   | En-tête 3                   |
| --------------------------- | --------------------------- | --------------------------- |
| Ligne 1, colonne 1 | Ligne 1, colonne 2 | Ligne 1, colonne 3  |
| Ligne 2, colonne 1 | Ligne 2, colonne 2 | Ligne 2, colonne 3  |
| Ligne 3, colonne 1 | Ligne 3, colonne 2 | Ligne 3, colonne 3  |

On peut aligner les différentes parties avec les ':' :

| Aligner à gauche | Centrer | Aligner à droite |
| :--------------- | :-----: | ---------------: |
| Pommes           |  Rouge  |             5000 |
| Bananes          |  Jaune  |               75 |

## Alertes (Github)

> [!NOTE]
> Useful information that users should know, even when skimming content.

> [!TIP]
> Helpful advice for doing things better or more easily.

> [!IMPORTANT]
> Key information users need to know to achieve their goal.

> [!WARNING]
> Urgent info that needs immediate user attention to avoid problems.

> [!CAUTION]
> Advises about risks or negative outcomes of certain actions.

## Ancre de page/Lien de section

Référence les titres

Les lettres sont converties en minuscules.
Les espaces sont remplacés par des traits d’union (-). Tout autre espace blanc ou caractère de ponctuation est supprimé.
Les espaces blancs de début et de fin sont supprimés.
La mise en forme du balisage est supprimée, ne laissant que le contenu (par exemple, _italics_ devient italics).
Si l’ancre générée automatiquement pour un titre est identique à une ancre antérieure dans le même document, un identifiant unique est généré en ajoutant un trait d’union et un nombre entier auto-incrémenté.

### Exemples :

Lien vers le début : [Début](#emphases)

## Notes de bas de page

Phrase[ref]

[^ref]: reference

## Commentaires

Comme en HTML
<!-- Commentaire em Markdown -->
