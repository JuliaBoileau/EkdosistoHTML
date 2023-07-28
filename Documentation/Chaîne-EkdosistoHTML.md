# Chaîne éditoriale - De ekdosis à HTML

1. Encodage LaTeX de l'édition critique grâce au package ekdosis (*Étape en cours*)
2. Compilation du document .tex et production d'un document TEI xml (*Tests d'échantillons  débutés*)
3. Dépôt du document TEI xml et création d'une ODD dans TEI Publisher (*Tests d'échantillons débutés - ODD de base uniquement*)
4. Génération d'une application web TEI Publisher 
5. Choix/création d'un modèle HTML, d'une feuille de style CSS et de fonctions JavaScript 
6. Déploiement du projet d'édition

## Encodage LaTeX ekdosis et compilation d'une sortie XML

### Logiciel TeX et langage LaTeX

[TeX](https://fr.wikipedia.org/wiki/TeX#:~:text=TeX%20est%20un%20système%20logiciel,%27édition%20de%20l%27époque.) est un logiciel de mise en page, alors que LaTeX est le langage de balisage construit au-dessus de TeX pour simplifier le processus de composition de documents. LaTeX comporte un ensemble de macros et de commandes qui encadrent sémantiquement le texte, et assurent sa juste interprétation sur différentes plateformes. 

Exemple de document LaTeX :

```latex
\documentclass{book} % Type de document (article, book, report, etc.)

\begin{document} % Début du contenu du document

\title{Mon document \LaTeX} % Titre du document
\author{Mon Nom} % Auteur du document
\date{\today} % Date (ici, la date actuelle)

\maketitle % Afficher le titre, l'auteur et la date

\section{Introduction} % Début de la section "Introduction"
Ceci est un exemple de document \LaTeX. % Contenu de la section

\section{Conclusion} % Début de la section "Conclusion"
Vous pouvez désormais reconnaître un balisage \LaTeX. % Contenu de la section

\end{document} % Fin du contenu du document
```

Un document LaTeX peut être codé dans un éditeur de texte ou produit à partir d'un autre format, comme Markdown ou TEI xml. En ce qui nous concerne, le codage LaTeX est favorisé grâce à sa rigueur en matière d'encodage critique. Comme nous le verrons dans la section suivante, le paquet ekdosis permet non seulement d'enrichir encore davantage le balisage LaTeX du texte, mais aussi de produire une sortie TEI xml respective lors de la compilation du fichier .tex.

> **Ressources TeX et LaTeX**
>
> - Console recommandée : [MiKTeX](https://miktex.org/download) pour Windows PC | [MacTeX](https://tug.org/mactex/mactex-download.html) pour Mac OS
> - Éditeur de texte recommandé : [TeXMaker](https://www.xm1math.net/texmaker/)
> - Plateforme suggérée : [Overleaf](https://fr.overleaf.com)
> - [Documentation](https://fr.overleaf.com/learn) LaTeX 
> - [Tutoriel vidéo](https://www.youtube.com/watch?v=ydOTMQC7np0&t=11522s) LaTeX complet, sur la [chaîne Youtube](https://www.youtube.com/@freecodecamp) de la plateforme [freeCodeCamp](https://www.freecodecamp.org)

### Paquet LaTeX ekdosis

**Description générale par Robert Alessi, ekdosis.org** : [ekdosis](http://www.ekdosis.org/fr/index.html) est une extension LuaLaTeX conçue pour les éditions critiques multilingues. Elle peut être utilisée pour mettre en page des textes avec différents étages de notes critiques dans toute direction d'écriture prise en charge par [LuaTeX](https://www.luatex.org//). Les textes peuvent être présentés sous la forme de paragraphes continus ou bien en vis-à-vis, en colonnes multiples, alignées ou non. En plus de la version destinée à l'impression, ekdosis peut convertir le fichier-source .tex en fichier conforme au format TEI xml. L'encodage en LaTeX, orienté « base de données », permet l'extraction des textes saisis par segments selon différents critères : texte principal, variantes, traductions ou encore rédactions parallèles annotées par l'éditeur.

Le paquet ekdosis nous intéresse principalement pour sa prise en charge des éditions critiques multilingues, ainsi que pour sa production d'un fichier conforme au format TEI xml. 

Pour créer un document final à partir d'un fichier .tex et du package ekdosis, on utilise un compilateur TeX. Après l'ouverture du fichier LaTeX dans le compilateur, on effectue une compilation LuaLateX pour générer une sortie PDF (par défaut) et une sortie TEI xml. **Notez que trois compilations peuvent être nécessaires à la production d'une sortie de documents complets.** Il est bon de savoir que le paquet ekdosis prend en charge l'édition multiformat, soit papier et numérique.

> **Ressources ekdosis**
> 
> - [Documentation PDF](https://ctan.mirror.rafal.ca/macros/luatex/latex/ekdosis/ekdosis.pdf)
> - Lecture suggérée : [Estelle Debouy, « Présenter une édition numérique de fragments », dans Robert Alessi, Marcello Vitali-Rosati (dir.), Les éditions critiques numériques : entre tradition et changement de paradigme (édition augmentée), Les Presses de l’Université de Montréal, Montréal, 2023, isbn : 978-2-7606-4857-9, https://www.parcoursnumeriques-pum.ca/12-editionscritiques/chapitre6.html. version 0, 27/03/2023 Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)](https://www.parcoursnumeriques-pum.ca/12-editionscritiques/chapitre6.html)

### TEI xml

La [Text Encoding Initiative (TEI)](https://tei-c.org) utilise le langage de balisage extensible (XML) pour encoder les textes de manière structurée et normalisée. 

En ce qui nous concerne, le fichier TEI xml fourni par la compilation TeX peut servir de base à une publication web. En effet, le langage XML est cousin du langage HTML, qui constitue la base structurale du web. Alors que XML encode et structure l'information, HTML en permet l'affichage web selon cette même structure. 

> **Ressources TEI xml**
> 
> - [Documentation](https://tei-c.org/release/doc/tei-p5-doc/fr/html/index.html) TEI
> - Logiciel recommandé : [Oxygen XML Editor 25.1](https://www.oxygenxml.com)

## Édition sur TEI Publisher et déploiement d'une application web

### TEI Publisher

TEI Publisher est une application [eXist-db](http://exist-db.org/exist/apps/homepage/index.html). 

#### Avantages

*single source publishing*
- Plusieurs modèles personnalisables
- Exige peu de codage : édition de l'ODD possible au format texte (code) ou grâce à l'interface visuelle *code free* pour les non-initiés
- L'édition critique du texte (XML-TEI, ODD, CSS) est distincte de la programmation web (HTML, CSS, JavaScript) ; plusieurs textes édités selon différents schémas peuvent être disposés sur une même page web 
- Capacité de balisage étendue : variations textuelles, interventions éditoriales, appareils critiques, commentaires, etc.
- Génération de contenus dynamiques : table des matières, index, etc.
- Inclusion d'images et de facsimilés
- Adapté à plusieurs outils de lecture

#### Limitations

- Exige certaines compétences techniques pour un balisage précis (XML-TEI et XPath) et un rendu satisfaisant (HTML/CSS)
- Exige une période d'adaptation à la plateforme et au système de fichiers en place

> **Ressources TEI Publisher**
> 
> - Exemple : [Van Gogh Letters](https://teipublisher.com/exist/apps/vangogh/index.html)
> - Version [demo](https://teipublisher.com/exist/apps/tei-publisher/index.html)
> - [Documentation](https://teipublisher.com/exist/apps/tei-publisher/doc/documentation.xml?odd=docbook&view=div) TEI Publisher
> - [Tutoriels](https://www.youtube.com/watch?v=QuWrfAS2SWM&list=PLx8WACGMjM7mmlJXUW-SdEKw9pEBNMzfW) TEI Publisher, sur la [chaîne Youtube](https://www.youtube.com/@e-editiones8339) de l'organisme [e-editiones](https://www.e-editiones.org)
> - [Tutoriels additionnels](https://www.youtube.com/@wolfgangmm) par Wolfgang Meier

### Document ODD - One Document Does it all



**Notez que la structure ODD proposée par TEI Publisher diffère de la structure standard.** 

> - [Documentation](https://teipublisher.com/exist/apps/tei-publisher/doc/documentation.xml?view=div&odd=docbook&id=behaviours-available#odd-customization-details) ODD sur la plateforme TEI Publisher
> - [Documentation](https://tei-c.org/guidelines/customization/getting-started-with-p5-odds/#:~:text=%27ODD%27%20(%20One%20Document%20Does,customization%20of%20the%20TEI%20scheme.) ODD sur le site TEI

#### XPath

XPath est un langage de requête (Query) utilisé pour naviguer dans les documents XML et en extraire des informations spécifiques en fonction de leur emplacement dans la hiérarchie du document et de leurs attributs. Ce langage peut être nécessaire pour cibler des éléments dans le modèle ODD. 

> **Ressources XPath**
> 
> - [Tutoriel](https://www.w3schools.com/xml/xpath_intro.asp) XPath, par W3School

### Application web TEI Publisher

Une fois le rendu éditorial satisfaisant, un module intégré permet de générer une application web, avec un segment URL personnalisé. Cette URL peut être déterminée ultérieurement. 

Le nouveau site web peut ainsi être 

### Développement web : HTML/CSS/JavaScript

> **Ressources HTML, CSS et JavaScript**
> 
> - Cours HTML recomandé : [HTML Essential Training](https://www.linkedin.com/learning/html-essential-training-4), par Jen Simmons (30 jours gratuits sur [LinkedIn Learning](https://www.linkedin.com/learning/)) 
> - Plateforme [Codecademy](https://www.codecademy.com/learn) + [Chaîne Youtube](https://www.youtube.com/@codecademy) - Cours variés, tutoriels, articles et *cheatsheets*
> - Plateforme [freeCodeCamp](https://www.freecodecamp.org) + [Chaîne Youtube](https://www.youtube.com/@freecodecamp) - Cours variés et tutoriels

___

## Protocole [Git](https://git-scm.com) et plateforme [GitHub](https://github.com)

> **Ressources Git et GitHub**
> 
> - [Documentation Git](https://git-scm.com/doc)
> - Tutoriel rapide (15 min.) : [Learn Git in 15 Minutes](https://www.youtube.com/watch?v=USjZcfj8yxE&list=PLAm2x6UxYwofxbHESgByJRUm0KP9KIs7h&index=23)
> - Tutoriel complet (1h) : [Git and GitHub for Beginners - Crash Course](https://www.youtube.com/watch?v=RGOj5yH7evk&list=PLAm2x6UxYwofxbHESgByJRUm0KP9KIs7h&index=26)
> - Formation [Débugue tes humanités - Séance 04 - Git](https://debugue.ecrituresnumeriques.ca/seance-04-git/presentation.html#/)
