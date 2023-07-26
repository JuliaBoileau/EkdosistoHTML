# Chaîne éditoriale - De ekdosis à HTML

## Paquet LaTeX ekdosis

[ekdosis](http://www.ekdosis.org/fr/index.html) est une extension LuaLaTeX conçue pour les éditions critiques multilingues. Elle peut être utilisée pour mettre en page des textes avec différents étages de notes critiques dans toute direction d'écriture prise en charge par [LuaTeX](https://www.luatex.org//). Les textes peuvent être présentés sous la forme de paragraphes continus ou bien en vis-à-vis, en colonnes multiples, alignées ou non. En plus de la version destinée à l'impression, ekdosis peut convertir le fichier-source .tex en fichier conforme au format TEI xml. L'encodage en LaTeX, orienté « base de données », permet l'extraction des textes saisis par segments selon différents critères : texte principal, variantes, traductions ou encore rédactions parallèles annotées par l'éditeur. 
~ Robert Alessi, ekdosis.org

- [Documentation PDF](https://ctan.mirror.rafal.ca/macros/luatex/latex/ekdosis/ekdosis.pdf)
- Lecture suggérée : [Estelle Debouy, « Présenter une édition numérique de fragments », dans Robert Alessi, Marcello Vitali-Rosati (dir.), Les éditions critiques numériques : entre tradition et changement de paradigme (édition augmentée), Les Presses de l’Université de Montréal, Montréal, 2023, isbn : 978-2-7606-4857-9, https://www.parcoursnumeriques-pum.ca/12-editionscritiques/chapitre6.html. version 0, 27/03/2023 Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)](https://www.parcoursnumeriques-pum.ca/12-editionscritiques/chapitre6.html)

### TeX et LaTeX

[TeX](https://fr.wikipedia.org/wiki/TeX#:~:text=TeX%20est%20un%20système%20logiciel,%27édition%20de%20l%27époque.) est un logiciel de mise en page développé par Donald Knuth dans les années 1970, et LaTeX est un ensemble de macros et de commandes construit au-dessus de TeX pour simplifier le processus de composition et rendre la création de documents plus facile et plus cohérente.

Voici un exemple LaTeX :

```latex
\documentclass{article} % Type de document (article, book, report, etc.)

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

Pour créer un document final à partir d'un fichier .tex et du package ekdosis, on utilise un compilateur TeX au format LuaLateX pour générer une sortie PDF (par défaut) et une sortie TEI-xml. Notez que trois compilations à la suite peuvent être nécessaires pour produire des sorties complètes. 

- Console recommandée : [MiKTeX](https://miktex.org/download) pour Windows PC | [MacTeX](https://tug.org/mactex/mactex-download.html) pour Mac OS
- Éditeur de texte recommandé : [TeXMaker](https://www.xm1math.net/texmaker/)
- Plateforme suggérée : [Overleaf](https://fr.overleaf.com)
- [Documentation](https://fr.overleaf.com/learn) LaTeX
- [Tutoriel vidéo](https://www.youtube.com/watch?v=ydOTMQC7np0&t=11522s) LaTeX complet, sur la [chaîne Youtube](https://www.youtube.com/@freecodecamp) de la plateforme [freeCodeCamp](https://www.freecodecamp.org)

## TEI Publisher

- Demo : [Van Gogh Letters](https://teipublisher.com/exist/apps/vangogh/index.html)
- [Documentation](https://teipublisher.com/exist/apps/tei-publisher/doc/documentation.xml?odd=docbook&view=div) TEI Publisher
- [Tutoriels](https://www.youtube.com/watch?v=QuWrfAS2SWM&list=PLx8WACGMjM7mmlJXUW-SdEKw9pEBNMzfW) TEI Publisher, sur la [chaîne Youtube](https://www.youtube.com/@e-editiones8339) de l'organisme [e-editiones](https://www.e-editiones.org)

### TEI xml

La [Text Encoding Initiative (TEI)](https://tei-c.org) utilise le langage de balisage extensible (XML) pour encoder les textes de manière structurée et normalisée. Le fichier TEI-XML fourni par la compilation TeX peut servir de base à une publication web au format cousin HTML. 

- [Documentation](https://tei-c.org/release/doc/tei-p5-doc/fr/html/index.html) TEI
- Logiciel recommandé : [Oxygen XML Editor 25.1](https://www.oxygenxml.com)

### XPath
XPath est un langage de requête (Query) utilisé pour naviguer dans les documents XML et en extraire des informations spécifiques en fonction de leur emplacement dans la hiérarchie du document et de leurs attributs. 

- [Tutoriel](https://www.w3schools.com/xml/xpath_intro.asp) XPath

### Développement web - HTML & CSS

- 

## Collaboration et protocole [Git](https://git-scm.com) 

### Plateforme [GitHub](https://github.com)

- Tutoriel rapide (15 min.) : [Learn Git in 15 Minutes](https://www.youtube.com/watch?v=USjZcfj8yxE&list=PLAm2x6UxYwofxbHESgByJRUm0KP9KIs7h&index=23)
- Tutoriel complet (1h) : [Git and GitHub for Beginners - Crash Course](https://www.youtube.com/watch?v=RGOj5yH7evk&list=PLAm2x6UxYwofxbHESgByJRUm0KP9KIs7h&index=26)
