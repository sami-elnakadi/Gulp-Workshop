# Gulp-Workshop

Gulp est un "Automatiseur de tâches", un task runner comme disent nos amis anglophones, c'est à dire qu'il est capable de lancer des bouts de scripts à votre place tout seul comme un grand.
Ces tâches dépendent de votre bon vouloir et peuvent être très variées :
<ul>
    <li>des opérations simples telles que minifier ou concaténer du CSS ou du JavaScript,</li>
    <li>la création ou la suppression de dossiers ou de fichiers (possibilité de créer un projet à partir de zéro),</li>
    <li>l'optimisation, la compression d'images,</li>
    <li>la création de serveur local permettant de tester sur de multiples périphériques en même temps,</li>
    <li>la simulation de navigateurs fantômes conçus pour parcourir et tester les régressions d'affichage d'une page,</li>
    <li>etc.</li>
 </ul>

Pour vous représenter le nombre d'actions réalisables par Gulp, sachez que les quelques 2000 plugins recensés représentent tout autant de tâches exécutables au sein de votre projet.

Les pré-requis de Gulp
Pour accomplir vos premiers exploits avec Gulp, vous n'aurez besoin que de :
   <ul>
    <li>node.js</li>
    <li>ne pas être trop allergique à la ligne de commande</li>
</ul>
## Installer Gulp

Dès que Node.js est installé, ouvrez un terminal de commande n'importe où, et tapez:

sudo npm install gulp -g


Gulp à présent installé, il lui faudra une combinaison de deux fichiers à la racine d'un projet pour être totalement fonctionnel :
<ul>
    <li>package.json : contient la liste des plugins gulp (ou autres) nécessaires à vos tâches</li>
    <li>gulpfile.js : contient la liste des tâches à réaliser</li>
 </ul>

## Structure du projet
Notre projet sera constitué ainsi :
<ul>
    <li>src : dossier de travail, où sont contenus les fichiers .less de développement</li>
    <li> dist : dossier de production, où seront créés les fichiers produits par Gulp (ce dossier sera généré, il n'est pas utile qu'il soit présent au départ du projet)</li>
</ul>
Visuellement, cela pourrait ressembler à cette structure assez classique :

<img src="https://www.alsacreations.com/xmedia/doc/original/structure.png" alt="structure">




## Le fichier package.json
Il est possible de créer un fichier package.json vierge à partir de zéro, à l'aide de l'instruction suivante (placez votre terminal de commande dans votre dossier de projet) :

npm init

npm vous demandera alors plein d'informations (nom du projet, licence, etc.), le plus simple est généralement de valider point par point en confirmant avec la touche Entrée.
L'étape suivante est alors de déclarer et d'installer un par un chaque plugin qui sera nécessaire pour votre projet, en commençant par exemple par Gulp lui-même :

npm install gulp --save-dev

... et ainsi de suite pour chaque plugin.
Sinon, une manière plus simple est tout simplement de récupérer un package.json existant et de copier-coller son contenu au sein du votre, et de lancer l'instruction suivante pour tout installer dans votre dossier de projet :

npm install

Pour info, npm install a pour mission d'installer tous les plugins listés dans le fichier package.json

Voilà, vous avez fait le gros du boulot. Il ne reste plus qu'à donner les instruction pour la bonne exécution de ces plugins, via le fichier gulpfile.js.

## Le fichier gulpfile.js

Le fichier gulpfile.js s'occupe de gérer les tâches à réaliser, leurs options, leurs sources et destination. Bref, c'est le chef d'orchestre (après vous).
