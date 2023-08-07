
> Tous les outils proposés sont *open source*.

## TEI Boilerplate

### Fonctionnement

Charger son document XML-TEI automatiquement converti en HTML, baliser le contenu et personnaliser le rendu grâce à une feuille de style CSS. 

### Avantages

- Idéal pour la mise en ligne rapide et légère de projets simples (publications non critiques) 
- Exige très peu de programmation
- Compatible avec plusieurs navigateurs : Firefox, Chrome, Safari, et Internet Explorer

### Limitations

- Fonctionnalités et personnalisation limitées
- Non favorable à l'édition critique - aucune option de versionnage ou de visualisation parallèle (colonne unique) 

### Demo
[Demo des fonctionnalités](https://dcl.ils.indiana.edu/teibp/content/demo.xml)

## Versioning Machine 5.0

### Fonctionnement

Après une rapide inscription sur la plateforme de [v-machine.org](http://v-machine.org), un fichier .zip à télécharger fournit tous les documents nécessaires à l'installation de l'outil sur un poste local. 

Une fois l'outil installé, les documents TEI xml de l'édition prévue doivent d'abord être balisés selon les exigences de la plateforme, décrites dans la documentation. Sans surprise, c'est dans ces documents que doivent être intégrés les métadonnées et l'appareil critique, incluant les témoins, les anotations, les notes et les commentaires, ainsi que tous médias pertinents - facsimilés, autres images, audio ou vidéo.  

Une feuille .xsl fournie par la plateforme peut ensuite être modifiée - au choix - et appliquée au XML afin de moduler le rendu web de l'édition. Bien que la majorité des navigateurs peuvent interpréter un fichier XML sans schéma .xsl, il est recommandé d'en fournir un, qu'il soit simple ou augmenté, afin de contrôler et d'uniformiser cette interprétation.

Une feuille CSS et un document JavaScript peuvent également être intégrés au document XML afin de modifier respectivement le rendu graphique et les fonctionnalités du rendu web produit. 

Une fois le rendu satisfaisant, cet ensemble de fichiers peut être déployé de manière indépendante grâce au module VM5. 

> Voir la [documentation](http://v-machine.org/documentation/) sur [v-machine.org](http://v-machine.org). 

### Avantages

- Comparaison de nombreuses versions et mise en évidence des différences pour analyse
- Flexibilité d'affichage des versions comparatives ajoutées à l'écran
- Personnalisation avancée de la visualisation
- Inclusion d’images et de facsimilés

### Limitations

- Fonctionnalités limitées : axé davantage sur la comparaison que sur le balisage et l'annotation
- Très peu de documentation et de ressources externes, aucun tutoriel diponible
- Fonctionne uniquement sur mac OS ou PC

### Demo
[The Pearl](http://v-machine.org/samples/pearl.html)

## TEI Publisher

### Fonctionnement

TEI Publisher est une application [eXist-db](http://exist-db.org/exist/apps/homepage/index.html). 

Après avoir chargé les documents xml-TEI d'une édition, on y applique un schéma ODD de base fourni par la plateforme (ou l'un des modèles proposés en démo), que l'on peut ajuster et personnaliser selon les exigences du texte, afin d'afficher adéquatement les dispositifs de l'édition.

Une fois le rendu éditorial satisfaisant, on génère une application web grâce au module intégré, qui fournit un segment URL personnalisé. On ajuste ce rendu web grâce à une feuille HTML automatiquement générée à partir de l'XML ; c'est l'endroit où ajouter des pages web et organiser la structure des contenus. 

L'apparence du rendu est enfin peaufinée grâce à une feuille de style CSS, et des fonctions JavaScript peuvent être ajoutées au besoin. 

Une fois le site web déployé, la consultation est ouverte au public. Il demeure possible d'effectuer des ajouts et modifications en tout temps. 

> Voir la [documentation](https://teipublisher.com/exist/apps/tei-publisher/doc/documentation.xml?odd=docbook&view=div) et les [tutoriels](https://www.youtube.com/watch?v=QuWrfAS2SWM&list=PLx8WACGMjM7mmlJXUW-SdEKw9pEBNMzfW) sur la chaîne Youtube de l'organisme [e-editiones.org](e-editiones.org)

### Avantages

- *Single source publishing*
- Plusieurs modèles personnalisables
- Exige peu de codage : édition de l'ODD possible au format texte (code) ou grâce à l'interface visuelle *code free* pour les non-initiés
- L'édition critique du texte (XML-TEI, ODD, CSS) est distincte de la programmation web (HTML, CSS, JavaScript) ; plusieurs textes édités selon différents schémas peuvent être disposés sur une même page web 
- Capacité de balisage étendue : variations textuelles, interventions éditoriales, appareils critiques, commentaires, etc.
- Génération de contenus dynamiques : table des matières, index, etc.
- Inclusion d'images et de facsimilés
- Adapté à plusieurs outils de lecture

### Limitations

- Exige certaines compétences techniques pour un balisage précis (XML-TEI et XPath)
- Exige une période d'adaptation à la plateforme et au système de fichiers en place

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