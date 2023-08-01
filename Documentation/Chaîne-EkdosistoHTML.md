# Chaîne éditoriale - De ekdosis à HTML

1. Encodage LaTeX de l'édition critique grâce au package ekdosis - *Étape en cours*
2. Compilation du document .tex et production d'un document TEI xml - *Tests d'échantillons  débutés (imperfections)*
3. Dépôt du document TEI xml et création d'une ODD dans TEI Publisher - *Tests d'échantillons débutés (ODD de base uniquement)*
4. Génération d'une application web grâce au module TEI Publisher 
5. Choix/création d'un modèle HTML, d'une feuille de style CSS et de fonctions JavaScript 
6. Déploiement du projet d'édition

## Encodage LaTeX ekdosis et compilation d'une sortie TEI xml

### Logiciel TeX et langage LaTeX

[TeX](https://fr.wikipedia.org/wiki/TeX#:~:text=TeX%20est%20un%20système%20logiciel,%27édition%20de%20l%27époque.) est un logiciel de mise en page, alors que LaTeX est le langage de balisage construit au-dessus de TeX pour simplifier le processus de composition de documents. LaTeX comporte un ensemble de macros et de commandes qui encadrent sémantiquement le texte, et assurent sa juste interprétation sur différentes plateformes.

Exemple de document LaTeX :

```latex
\documentclass{book} % Type de document (article, book, report, etc.)

\begin{document} % Début du contenu du document

\title{Titre du document \LaTeX} % Titre du document
\author{Nom de l'auteur} % Auteur du document
\date{\today} % Date (ici, la date actuelle)

\maketitle % Affiche le titre, l'auteur et la date

\section{Introduction} % Début de la section "Introduction"
Ceci est un exemple de document \LaTeX. % Contenu de la section

\section{Conclusion} % Début de la section "Conclusion"
Vous pouvez désormais reconnaître un balisage \LaTeX. % Contenu de la section

\end{document} % Fin du contenu du document
```

Un document LaTeX peut être codé dans un éditeur de texte ou produit à partir d'un autre format, comme Markdown ou TEI xml. En ce qui nous concerne, le codage initial en LaTeX est favorisé pour sa rigueur en matière d'encodage critique. Comme nous le verrons dans la section suivante, le paquet ekdosis permet non seulement d'enrichir encore davantage le balisage LaTeX d'une édition, mais aussi d'en compiler une sortie TEI xml complète à partir du fichier TeX. 

> **Ressources TeX et LaTeX**
>
> - Console recommandée : [MiKTeX](https://miktex.org/download) pour Windows PC | [MacTeX](https://tug.org/mactex/mactex-download.html) pour Mac OS
> - Éditeur de texte recommandé : [TeXMaker](https://www.xm1math.net/texmaker/)
> - Plateforme suggérée : [Overleaf](https://fr.overleaf.com)
> - [Documentation](https://fr.overleaf.com/learn) LaTeX 
> - [Tutoriel vidéo](https://www.youtube.com/watch?v=ydOTMQC7np0&t=11522s) LaTeX complet, sur la [chaîne Youtube](https://www.youtube.com/@freecodecamp) de la plateforme [freeCodeCamp](https://www.freecodecamp.org)

### Paquet LaTeX ekdosis

**Description générale par Robert Alessi, ekdosis.org** : 

"[ekdosis](http://www.ekdosis.org/fr/index.html) est une extension LuaLaTeX conçue pour les éditions critiques multilingues. Elle peut être utilisée pour mettre en page des textes avec différents étages de notes critiques dans toute direction d'écriture prise en charge par [LuaTeX](https://www.luatex.org//). Les textes peuvent être présentés sous la forme de paragraphes continus ou bien en vis-à-vis, en colonnes multiples, alignées ou non. En plus de la version destinée à l'impression, ekdosis peut convertir le fichier-source .tex en fichier conforme au format TEI xml. L'encodage en LaTeX, orienté « base de données », permet l'extraction des textes saisis par segments selon différents critères : texte principal, variantes, traductions ou encore rédactions parallèles annotées par l'éditeur."

Pour créer un document final à partir d'un fichier .tex et du package ekdosis, on utilise un compilateur TeX. Après l'ouverture du fichier LaTeX dans le compilateur, on effectue une compilation LuaLateX pour générer une sortie PDF (par défaut) et une sortie TEI xml. **Notez que trois compilations peuvent être nécessaires à la production d'une sortie de documents complète.** Il est bon de savoir que le paquet ekdosis prend en charge l'édition multiformat, à la fois papier et numérique.

> **Ressources ekdosis**
> 
> - [Documentation PDF](https://ctan.mirror.rafal.ca/macros/luatex/latex/ekdosis/ekdosis.pdf) des spécificités LaTeX ekdosis
> - Lecture suggérée : [Estelle Debouy, « Présenter une édition numérique de fragments », dans Robert Alessi, Marcello Vitali-Rosati (dir.), Les éditions critiques numériques : entre tradition et changement de paradigme (édition augmentée), Les Presses de l’Université de Montréal, Montréal, 2023, isbn : 978-2-7606-4857-9, https://www.parcoursnumeriques-pum.ca/12-editionscritiques/chapitre6.html. version 0, 27/03/2023 Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)](https://www.parcoursnumeriques-pum.ca/12-editionscritiques/chapitre6.html)

### TEI xml

La [Text Encoding Initiative (TEI)](https://tei-c.org) utilise le langage de balisage extensible (XML) pour encoder les textes de manière structurée et normalisée.

En ce qui nous concerne, le fichier TEI xml fourni par la compilation TeX peut servir de base à une publication web. En effet, le langage XML est cousin du langage HTML, qui constitue la base structurale du web. Alors que XML encode et structure l'information, HTML en permet l'affichage web respectif.

> **Ressources TEI xml**
> 
> - [Documentation](https://tei-c.org/release/doc/tei-p5-doc/fr/html/index.html) TEI
> - Logiciel recommandé : [Oxygen XML Editor 25.1](https://www.oxygenxml.com)

## Édition sur TEI Publisher et déploiement d'une application web

### TEI Publisher

TEI Publisher est une application [eXist-db](http://exist-db.org/exist/apps/homepage/index.html). Il est recommandé de suivre les instructions d'installation directement sur le site.

#### Avantages

- Permet le *single source publishing* en multiformat
- Offre plusieurs modèles d'ODD et de rendus web personnalisables
- Exige peu de codage ; l'édition de l'ODD est possible au format texte (code) ou grâce à l'interface visuelle *code free* pour les non-initiés
- Permet une édition critique sémantique du texte (XML-TEI, ODD, CSS) distincte de l'affichage et des fonctions web (HTML, CSS, JavaScript)
- Offre une capacité de balisage étendue (variations textuelles, interventions éditoriales, appareils critiques, commentaires, notes, etc.) et l'inclusion d'images et de facsimilés
- Permet la génération de contenus dynamiques : table des matières, index, etc.
- Produit un rendu adapté à plusieurs outils de lecture

#### Limitations

- Exige certaines compétences techniques pour un balisage précis (XML-TEI et XPath) et un rendu satisfaisant (HTML/CSS)
- Exige une période d'adaptation à la plateforme et au système de fichiers en place

> **Ressources TEI Publisher**
> 
> - Exemple : [Van Gogh Letters](https://teipublisher.com/exist/apps/vangogh/index.html)
> - [Version d'essai](https://teipublisher.com/exist/apps/tei-publisher/index.html)
> - [Documentation](https://teipublisher.com/exist/apps/tei-publisher/doc/documentation.xml?odd=docbook&view=div) TEI Publisher
> - **[Tutoriels](https://www.youtube.com/watch?v=QuWrfAS2SWM&list=PLx8WACGMjM7mmlJXUW-SdEKw9pEBNMzfW) TEI Publisher, sur la [chaîne Youtube](https://www.youtube.com/@e-editiones8339) de l'organisme [e-editiones](https://www.e-editiones.org)**
> - [Tutoriels additionnels](https://www.youtube.com/@wolfgangmm) par Wolfgang Meier

### Document ODD - One Document Does it all

Un Document Type Definition (DTD) est un fichier distinct employé comme schéma structurant d'un document XML.

Contrairement à la DTD, une ODD est un document externe aux contraintes du standard XML, spécifique aux schémas Relax NG (web). Elle offre une plus grande flexibilité et extensibilité dans la documentation de structures de schémas complexes, en plus de permettre différents formats de sortie.

Sur TEI Publisher, l'ODD permet d'encoder les éléments structurants de l'édition, tels que la disposition des colones, l'affichage de l'appareil critique, etc., ou encore, d'appliquer des emphases ou des couleurs sémantiquements significatives au texte. 

Bien qu'une ODD soit d'ordinaire plus complexe à composer, le modèle et l'interface visuelle proposée par TEI Publisher facilitent grandement sa prise en charge.

> - [Documentation](https://teipublisher.com/exist/apps/tei-publisher/doc/documentation.xml?view=div&odd=docbook&id=behaviours-available#odd-customization-details) ODD sur la plateforme TEI Publisher
> - [Documentation](https://tei-c.org/guidelines/customization/getting-started-with-p5-odds/) ODD sur le site du consortium TEI

#### XPath

XPath est un langage de requête (Query) utilisé pour naviguer dans les documents XML et en extraire des informations spécifiques en fonction de leur emplacement dans la hiérarchie du document et de leurs attributs.

Bien que non obligatoire, ce langage peut être très utile pour cibler des éléments dans le modèle ODD. Par exemple, on pourrait cibler les éléments `<div lang="he">`, soit les divisions au contenu hébreu, afin d'aligner le texte qu'ils contiennent à droite. Le chemin XPath serait le suivant :

```XML
//div[@lang='hebreu']
```

> **Ressources XPath**
> 
> - [Tutoriel](https://www.w3schools.com/xml/xpath_intro.asp) XPath, par W3School

### Application web TEI Publisher et déploiement

Une fois le rendu éditorial satisfaisant, un module intégré permet de générer une application web et un segment URL personnalisé. Cette URL peut être déterminée ultérieurement.

Le lancement de l'application web donne accès à la personnalisation des composantes et de l'affichage web.

Une fois le rendu web satisfaisant, le site web peut être déposé sur un poste local ou sur un serveur privé, comme celui de l'Université de Montréal, et être déployé en quelques clics.

### Développement web (HTML/CSS/JavaScript)

Le lancement du module web permet de lier au projet des fichiers de développement web ; ceux-ci peuvent être sélectionnés parmi les démos proposés, ou construits à partir d'un modèle de base. 

Il est important de se rappeler que les fichiers de développement web (HTML/CSS/JavaScript) ne devraient pas intervenir directement sur le texte de la publication, préalablement édité grâce à l'ODD, mais bien sur la structure du site qui accueille ce texte.

#### Hypertext Markup Language (HTML)

HTML est le squelette de toute publication web. Il encode et structure sémantiquement l'entièreté des contenus d'un site.

Dans le `head`, on trouve les métadonnées : 
- charte de code utilisée (standard `<meta charset="UTF-8"/>`)
- titre d'onglet (`<title>`)
- feuilles de style CSS ou de fonctions JavaScript (`<link rel="stylesheet" href="styles.css"/>`), etc.

Dans le `body`, on trouve tous les contenus visibles : 
- menu et pages (`<nav>`)
- titres et intertitres (`<h1>, <h2>, ..., <h6>`)
- corps de texte (`<p>`)
- listes (ordonnées ou non `ol` / `ul` et items `li`)
- liens (`<a href="site.com">`)
- boutons (`<button>`), etc.

Voici un exemple de document HTML complet, comportant une seule page statique : 

```HTML 
<!DOCTYPE html> 
<html> 
<head> 
    <meta charset="UTF-8"/>
    <title>Titre méta</title>
</head>
<body> 
    <h1>Titre du contenu visible</h1>
    <p lang="fr">Ceci est un paragraphe./p>
    <p lang="he">.פסקה של טקסט בעברית</p>
</body>
</html>
```

Notez que le document HTML fourni par le module TEI Publisher affiche des noms d'éléments particuliers à la plateforme, mais une connaissance de base en HTML standard permet de manipuler les composantes et d'obtenir la structure souhaitée selon les mêmes principes. 

#### Cascading Style Sheet (CSS) 

CSS est le langage graphique du web ; il permet d'afficher les contenus codés en HTML selon les charactéristiques visuelles souhaitées, qu'il s'agisse d'alignement, de couleur, de typographie ou de forme.

Les règles inscrites dans un fichier .css doivent se référer aux éléments, classes ou attributs préalablement codés au document HTML du projet.

Voici une règle CSS qui se réfère à la balise de titre `<h1>` du document HTMl, qui prescrit au contenu un affichage en police de texte Tahoma, aligné au centre et de couleur vert forêt :

```CSS
h1 {
    font-family: tahoma;
    color: forestgreen;
    text-align: center;
}
```

#### JavaScript 

JavaScript permet l'ajout optionnel de fonctions supplémentaires bénéfiques aux utilisateurs, comme des contrôles de navigation, des fonctions de recherche ou encore la mise en évidence (stabilo, signet) de certains passages, par exemple.

> **Ressources HTML, CSS et JavaScript**
> 
> - Cours HTML recomandé : [HTML Essential Training](https://www.linkedin.com/learning/html-essential-training-4), par Jen Simmons (30 jours gratuits sur [LinkedIn Learning](https://www.linkedin.com/learning/)) 
> - Plateforme [Codecademy](https://www.codecademy.com/learn) + [Chaîne Youtube](https://www.youtube.com/@codecademy) - Cours variés, tutoriels, articles et *cheatsheets*
> - Plateforme [freeCodeCamp](https://www.freecodecamp.org) + [Chaîne Youtube](https://www.youtube.com/@freecodecamp) - Cours variés et tutoriels

## Protocole [Git](https://git-scm.com) et plateforme [GitHub](https://github.com)

Le protocole Git est un système de versionnage qui permet de suivre l'évolution d'un projet en détail à travers le temps, en plus de faciliter la collaboration et la fusion des contributions.

La plateforme GitHub sert de point d'ancrage à cette collaboration, en permettant de voir la branche principale d'un projet (*master*), les problèmes soulevés et les versions en cours.

> **Ressources Git et GitHub**
> 
> - [Documentation Git](https://git-scm.com/doc)
> - Tutoriel rapide (15 min.) : [Learn Git in 15 Minutes](https://www.youtube.com/watch?v=USjZcfj8yxE&list=PLAm2x6UxYwofxbHESgByJRUm0KP9KIs7h&index=23)
> - Tutoriel complet (1h) : [Git and GitHub for Beginners - Crash Course](https://www.youtube.com/watch?v=RGOj5yH7evk&list=PLAm2x6UxYwofxbHESgByJRUm0KP9KIs7h&index=26)
> - Formation [Débugue tes humanités - Séance 04 - Git](https://debugue.ecrituresnumeriques.ca/seance-04-git/presentation.html#/)
