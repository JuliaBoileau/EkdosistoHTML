# Réunion du 14 juillet

Guadalupe Gonzalez Dieguez & Julia Boileau

## Plan de la rencontre

1. Présentation de l'outil de modélisation TEI Publisher
2. Discussion - Dispositifs de l'édition et préférences d'affichage
3. Échange rapide - Vision du site
4. *Crash course* Git et GitHub

## 1. Présentation de l'outil TEI Publisher

Outil de modélisation XML et d'édition multiformat (web, PDF, ePub) [*open source*](https://github.com/eeditiones/tei-publisher-app), soutenu par l'organisation [e-editiones.org](https://www.e-editiones.org).

### Fonctionnement

TEI Publisher est une application [eXist-db](http://exist-db.org/exist/apps/homepage/index.html). 

Après avoir chargé les documents xml-TEI d'une édition, on applique un schéma ODD de base fourni par la plateforme (ou l'un des modèles proposés en démo), que l'on peut ajuster et personnaliser selon les exigences du texte, afin d'afficher adéquatement les dispositifs de l'édition.

Une fois le rendu éditorial satisfaisant, on génère une application web grâce au module intégré, qui fournit un segment URL personnalisé. On ajuste ce rendu web grâce à une feuille HTML automatiquement générée à partir de l'XML ; c'est l'endroit où ajouter des pages web et organiser la structure des contenus. 

L'apparence du rendu est enfin peaufinée grâce à une feuille de style CSS, et des fonctions JavaScript peuvent être ajoutées au besoin. 

Une fois le site web déployé, la consultation est ouverte au public. Il demeure possible d'effectuer des ajouts et modifications en tout temps. 

> Voir la [documentation](https://teipublisher.com/exist/apps/tei-publisher/doc/documentation.xml?odd=docbook&view=div) et les [tutoriels](https://www.youtube.com/watch?v=QuWrfAS2SWM&list=PLx8WACGMjM7mmlJXUW-SdEKw9pEBNMzfW)

**Démos** : [Van Gogh Letters](https://teipublisher.com/exist/apps/vangogh/index.html) | [When the Wall Came Down](https://teipublisher.com/exist/apps/dodis-facets/53168.xml?view=body&odd=dodis) 

## 2. Discussion - Dispositifs de l'édition et préférences d'affichage

Échantillon d'un premier chapitre prévu pour la fin juillet / début août, qui contiendra tous les dispositifs requis à la création d'un prototype avancé d'ODD.

## 3. Échange rapide - Vision du site et préférences d'apparence générales

Préférence pour le modèle web [Van Gogh Letters](https://teipublisher.com/exist/apps/vangogh/index.html) en 3 colonnes : Version française | Version hébraïque | Notes

## 4. *Crash course* Git et GitHub

***git status*** : Indique l'état actuel du dossier local. Si des modifications n'ont pas été soumises au protocole Git, elles s'afficheront sous forme de liste (en rouge pour les changements/suppressions et en vert pour les ajouts).  

***git add nom-du-fichier.xml*** et ***git add .*** : Permettent d'ajouter des fichiers "sur la table" afin de les préparer à être *commit*. La commande *git add nom-du-fichier.xml* permet d'ajouter les fichiers individuellement, alors que la commande *git add .* ajoute tous les fichiers listés par *git status* d'un seul coup. 

***git commit -m "Message"*** : Permet de *commit* les fichiers selon le protocole, et d'ajouter un message afin de documenter les modifications émises. Bien que le message peut être vide, il est fortement recommandé de toujours documenter les changements amenés au projet. 

***git push*** : Permet de réfléter les changements effectués dans le dossier local vers le dossier GitHub. La simple fonction *git push* synchronise le *repo* GitHub.

***git pull*** : Permet inversement de synchroniser le dossier local depuis le dossier GitHub, si des modifications devaient avoir été faites sur le site GitHub plutôt que localement. 

> Voir aussi [Git and GitHub for Beginners - Crash Course](https://www.youtube.com/watch?v=RGOj5yH7evk&t=1962s)