# Séance de travail EKDOSIS - R. Alessi 

```
date: 2023-05-10
present: Robert Alessi, Marcello Vitali-Rosati, Mathilde Verstraete, Julia Boileau, Guadalupe Gonzalez Dieguez, Margot Mellet, Antoine Fauchié
```

## Ordre du jour 

0. Tour de table
1. Workflow (cf. [the susruta project](https://sushrutaproject.org/))
2. [ChrysoCollate](https://cental.uclouvain.be/chrysocollate/), par [S. Moureau](https://uclouvain.be/fr/repertoires/sebastien.moureau)
3. Les Ateliers/le pressoir
5. Bidouillage ?

## Rêve 

Gramde éditions critiques aux ateliers SP

## Worklow/Chaîne éditoriale 

- Basics 
- [Digital Latin Library](https://digitallatin.org/)

## Mss de Guadalupe 

Projet d'édition de l'oeuvre *Le bouquet de myrrhe* (Tseror ha-mor), par Isaac b. Abraham ibn Latif (ca. 1210-1280)

Divers : ce n'est pas un bouquet puisque la myrrhe est une racine.

Accès numérique: perd-on accès à la matérialité ; les mss sont en ligne + vu en bibliothèque

**Projet** : 
- Projet de développement savoir (CRSH)
- Édition (critique) diplomatique plutôt que lachmanienne (~~texte idéal~~). Tous les témoins sont disponibles en ligne.
- Besoin de travailler de façon collaborative autour du texte original. Limites de Google doc

**Contenu** : 
- traduction cabalistique mystique 
- paragraphes cryptiques : secrets cachés dans tel épisode biblique (sans explication...) = en-têtes de chapitre 
- traduction malaisée 
- texte assez bref (-> bon prototype)

**Structure** à modéliser : 
- Édition
- Traduction française 
- Commentaire de chaque chapitre 

**Modélisation** : 
- liens avec la tradition biblique dans un commentaire
    - Commentaire trop long, pas directement dans ekdosis, mais on pourrait envisager un environnement \comment qui ne serait pas imprimé sur la page mais plutôt à la fin. Il pourrait aussi être visualisé comme notes de fin : cf. le paquet [Postnotes](https://ctan.org/pkg/postnotes)
    - Idée 1 : Comm. dans un alignement ekdosis qu'on pourrait traiter autrement à la fin; e.g. traitement de tous les \comments comme \postnote -> \alignment < \hebrew \french \comment 
    - Idée 2 : Utiliser [Postnotes](https://ctan.org/pkg/postnotes) donc commentaire imaginé comme de longues footnotes 
- renvois à [Sefaria](https://www.sefaria.org/texts) dans l'édition numérique
- images liées au texte mais se trouvant dans le commentaire : ```\includegraphics{image_dans_le_même_dossier.png}``` ; mieux de considérer ces images comme objets flotants : ```\beginfigure \includegraphics{}``` 
- plusieurs balisages dans ekdosis pour l'édition numérique/papier ? 
- informations différentes selon ce qu'on veut être capables d'afficher en numérique 
- Citation structurée (bibtex) + lien vers [Sefaria](https://www.sefaria.org/) (éventuellement généré automatiquement) 
    - ekddiv -> n = ... : ekdosis est déjà comptable avec [CapTainS](http://capitains.org/)
    - possibilité de faire ses propres commandes dans ekdosis 

Un exemple d'utilisation de ces paquets: 

``` {Latex}
\usepackage{classics}
\usepackage{icite}
\newclassic{genese}{\textit{Genèse}, #1|, #1}
\newclassic{exode}{\textit{Exode}, #1|, #1}



\bible[Genèse]{3}[2]
\bible*[Genèse]{3}[2]{3}[3]

\icite[\genese{1}[4]]{genese}

Dans le titre de notre texte, on a un renvoi au sachet de myrrhe dans \icite[\genese{1}[4]]{genese}.

```


## Projets à suivre (workflow) - think low tech

- [V-Machine](http://v-machine.org/samples/) et notamment [ces examples](http://v-machine.org/vm-in-use/)
- [Van Gogh Letters](https://vangoghletters.org/vg/letters.html)
- [Sushrutaproject](https://sushrutaproject.org/)
- [Digital Latin](https://digitallatin.org/)
- [Sefaria](https://www.sefaria.org/) / citations -> attention au protocole/à l'engagement des URN 
- [paquet icite](https://ctan.org/pkg/icite) et de là, [The classics package](https://ctan.org/pkg/classics)
- Ce qu'on ne veut pas : [Mahadurot](http://www.mahadurot.com/Content/A_Introduction%20Topics/Our%20Tech.htm)


**Pour Julia**, quelques étapes à parcourir (si possible dans cet ordre) : 

- **sortie XML** : effectuer une sortie XML à partir du travail de Guadalupe (via ekdosis)
- **transformation XSLT** : essayer les feuilles de transformation XSLT de V-Machine pour obtenir une page web (rendu en direct ou transformation asynchrone vers une sortie HTML)
- **mise en forme** : appliquer une feuille de styles sur cette page pour voir ce qui est possible de faire comme mise en page


## Stylo 

Icite en md pour création d'index 
Rester dans un balisage léger puis ensuite latex 

## Chrysocollate

- v. 1.2
- v. 1.3 en préparation ; TEI en préparation

## Partenariat ? 

- Subvention développement partenariat (CRSH)
- automne 23 
- partenaire: [Perseids](https://www.perseids.org/) 
    - doctorant.e.s pour [Digital Milliet](https://digmill.perseids.org/)
- automatisation de workflows ; *e.g.* : peut-on imaginer utiliser l'API de anthologiagraeca pour produire des sorties ekdosis etc 

###### tags: `CRCEN`, `Chaire`, `Réunion`, `Séance de travail`, `edition`, `CRIHN`, `ekdosis`,`LATEX`