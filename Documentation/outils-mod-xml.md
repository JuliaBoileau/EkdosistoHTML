
:::info
Tous les outils proposés sont *open source*.
:::

## TEI Boilerplate

### Fonctionnement

Charger son document XML-TEI automatiquement converti en HTML, baliser le contenu et personnaliser le rendu grâce à un ajout CSS. 

### Avantages

- Mise en ligne rapide de projets légers
- Conversion HTML automatique 
- Exige très peu de programmation
- Compatible avec plusieurs navigateurs : Firefox, Chrome, Safari, et Internet Explorer

### Limitations

- Fonctionnalités limitées
- Non favorable à l'édition critique - aucune option de versionnage ou de visualisation parallèle (colonne unique) 
- Personnalisation limitée

### Demo
[Demo des fonctionnalités](https://dcl.ils.indiana.edu/teibp/content/demo.xml)

## Versioning Machine 5.0

### Fonctionnement

Charger les dossiers XML-TEI (en local ou en ligne), visualiser les versions, appliquer une feuille html.xslt (recommandé), intégrer les annotations et métadonnées, personnaliser le rendu grâce à une feuille CSS, possibilité d'ajout JavaScript au besoin, exporter les résultats pour partage web statique. 

### Avantages

- Comparaison de nombreuses versions et mise en évidence des différences pour analyse
- Flexibilité d'affichage des versions comparatives ajoutées à l'écran
- Personnalisation avancée de la visualisation
- Inclusion d’images et de facsimiles
- Communauté d'utilisateurs active

### Limitations

- Fonctionnalités limitées : axé davantage sur la comparaison que sur le balisage et l'annotation
- Manipulation manuelle des versions comparatives ajoutées à l'écran - désavantageuse si en grand nombre 
- Pérennité potentiellement compromise par les améliorations portées aux versions de l'outil
- Fonctionne uniquement sur mac OS ou PC

### Demo

[The Pearl](http://v-machine.org/samples/pearl.html)

## TEI Publisher

### Fonctionnement

Application [eXist-db](http://exist-db.org/exist/apps/homepage/index.html). Charger son document, appliquer un modèle d'ODD, ajuster et personnaliser le modèle selon les exigences du texte, ajuster le rendu grâce à une feuille de style CSS, publier en multiformat, si désiré, puis générer une application web grâce au module intégré.

### Avantages

- *Single source publishing*
- Plusieurs modèles personnalisables
- Exige peu de programmation : édition de l'ODD possible au format texte (code) ou grâce à l'interface visuelle *code free* pour les non-initiés
- Capacité de balisage étendue : variations textuelles, interventions éditoriales, appareils critiques, commentaires, etc.
- Génération de contenus dynamiques : table des matières, index, etc.
- Inclusion d'images et de facsimilés
- Adapté à plusieurs outils de lecture

*Tutoriels disponibles sur la chaîne Youtube [e-editiones](https://www.youtube.com/@e-editiones8339)*

### Limitations

- Exige certaines compétences techniques pour un balisage précis (XML-TEI et XPath)

### Demo 
[Van Gogh](https://teipublisher.com/exist/apps/vangogh/let001a.xml?view=page&odd=vangogh&panels=0.2) | [When the Wall Came Down](https://teipublisher.com/exist/apps/dodis-facets/53168.xml?view=body&odd=dodis)

## MaX

### Fonctionnement

MaX est un Moteur d'Affichage XML. Il est basé sur le système de base de données XML native BaseX et sur les technologie RESTXQ et XSLT.

Il propose en standard des solutions de fabrication de pages respectants les principes du responsive design. Il fournit un moteur de recherche XQuery configurable et adaptable aux sources XML manipulées ainsi qu'un pager pour l'affichage des ressources longues.

Il embarque [OpenSeadragon](https://openseadragon.github.io) pour les images.

### Avantages

- *Single source publishing*
- Supporte tous les standards XML
- Capacité de balisage étendue : variations textuelles, interventions éditoriales, appareils critiques, commentaires, etc.
- Inclusion de multimédias variés
- Adapté à plusieurs outils de lecture

### Limitations

- Initialisation plus lourde, vu les technologies employées
- Exige certaines compétences techniques : balisage xml-TEI, RESTXQ et XSLT, BaseX, XQuery, développement web, etc.
- Documentation limitée
- Outil développé pour être installé uniquement sur les systèmes d’exploitation Linux et mac OS

### Demo
[Édition critique de Ciceron](https://www.unicaen.fr/puc/sources/ciceron/FR_livre1.xml/fr_livre1_1/lat_livre1_1)