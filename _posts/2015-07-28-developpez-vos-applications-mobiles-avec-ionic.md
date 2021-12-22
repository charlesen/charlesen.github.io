---
id: 239
title: Développez vos applications mobiles avec Ionic
date: 2015-07-28T09:01:00+02:00
author: charlesen
layout: post
guid: https://charlesen.fr/?p=239
permalink: /developpez-vos-applications-mobiles-avec-ionic/
image: /wp-content/uploads/2015/07/images_cordova-ng-ionic.png
categories:
  - tutoriel
---
<img loading="lazy" class=" size-full wp-image-234" src="https://charlesen.fr/wp-content/uploads/2015/07/images_cordova-ng-ionic.png" alt="" style="display: block; margin-left: auto; margin-right: auto;" width="636" height="231" srcset="https://charlesen.fr/wp-content/uploads/2015/07/images_cordova-ng-ionic.png 636w, https://charlesen.fr/wp-content/uploads/2015/07/images_cordova-ng-ionic-300x109.png 300w" sizes="(max-width: 636px) 100vw, 636px" />

Ionic est un Framework de développement d&rsquo;applications mobiles _**« hybrides »**_. Une applications _**« hybride »**_ contrairement à une application dite _**« Native »**_ est développée à l&rsquo;aide des technologies classiques du web, puis à partir d&rsquo;une WebView peut interagir avec des fonctions du mobile. De nombreux Framework comme [Cordova](https://cordova.apache.org) facilite cette interaction. Les applications hybrides ont de nombreux avantages par rapport aux applications natives pures, en particulier en ce qui concerne les plateformes ciblées (Android, iOS, Windows Phone), la vitesse de développement et l&rsquo;utilisation d&rsquo;outils tiers (développement modulaire).

<!--more-->

On pourrait voir Ionic comme la partie User Interface (UI) du processus de développement, un peu comme le Framework [Bootstrap](http://getbootstrap.com), mais avec en plus la mise à disposition de patterns propres aux mobiles appelés Composants (Components : liste, onglet, menu,&#8230;). Utilise le Framework <a href="https://angularjs.org" target="_blank">AngularJS</a> pour permettre l&rsquo;animation des composants visuels.

Contrairement à d&rsquo;autres Framework UI pour les mobiles, Ionic propose tout un panel de composants très proches du design des principales plateformes mobiles (Android et iOS), ce qui augmente encore plus l&rsquo;impression d&rsquo;être devant une application native une fois celle-ci développée.

Ionic s&rsquo;occupant essentiellement de la partie Interface graphique, il a besoin d&rsquo;un Framework qui va s&rsquo;occuper de l&rsquo;interaction avec les fonctions du mobile comme [Cordova](https://cordova.apache.org) ou encore <a href="http://phonegap.com" target="_blank">PhoneGap</a>.

### Installation

#### Pré-requis

Pour une installation sous Windows, la première chose à faire est d&rsquo;installer [Git](http://git-scm.com/download/win) et [NodeJS](http://nodejs.org/), des exécutables sont disponible sur les différents sites. Pour les utilisateurs de Mac ou de Linux la procédure peut se faire en ligne de commande (Voir les sites). On pourra ensuite exécuter des fonctions Git et NodeJS depuis la console Windows (cmd) ou Bash pour Linux ou Mac.

#### Installation de Cordova

<pre class="brush:bash">$ sudo npm install -g cordova </pre>

(Pas besoin de préciser _**« sudo »**_ dans le cadre de Windows)

&nbsp;

#### Installation des SDK pour Android et iOS

##### Android SDK

Installez le SDK en visitant : http://developer.android.com/sdk/. Il existe différentes versions en fonction de votre système d&rsquo;exploitation. Un exécutable existe pour Windows.

Il faut ensuite mettre à jour les variables d&rsquo;environnement du système pour pouvoir utiliser Cordova en ligne de commande.

Sous Mac ou Linux, il faut modifier le fichier **~/.bash_profile** en ajoutant la ligne suivante :

<pre class="brush:bash">export PATH=${PATH}:/Chemin/Vers-SDK/sdk/platform-tools:/Development/adt-bundle/sdk/tools </pre>

Puis executer la commande suivante pour que la modification sois prise en compte immédiatement

<pre class="brush:bash">$ source ~/.bash_profile</pre>

Sous Windows, il faut :

  * Faites un clic-droit sur Ordinateur, puis Propriétés.
  * Cliquer Paramètres systèmes avancés.
  * Choisir Variables d&rsquo;environnement.
  * Choisir la variable the PATH et cliquer sur éditer.
  * Ajouter le chemin vers le SDK au path actuel : ;C:\Chemin\Vers-SDK\sdk\platform-tools;C:\Chemin\Vers-SDK\sdk\tools.
  * Valider

Pour plus d&rsquo;information sur la procédure d&rsquo;installation,&nbsp;<a href="http://cordova.apache.org/docs/en/3.4.0/guide_platforms_android_index.md.html#Android%20Platform%20Guide" target="_blank">visitez le site</a>&nbsp;d&rsquo;Apache Cordova.

##### iOS

Si vous ne disposez encore de Xcode, vous pouvez le télécharger depuis l&rsquo;<a href="https://itunes.apple.com/us/app/xcode/id497799835?mt=12" target="_blank">AppStore</a> ou l&rsquo;<a href="https://developer.apple.com/downloads/index.action" target="_blank">Apple Developer</a>&nbsp;.

Il faut ensuite actver un certain nombre d&rsquo;outils de lignes commande qui permettront à Cordova de fonctionner. Pour ce faire, depuis Xcode, faites :

**Préférences** &#8211; **Téléchargements**, Depuis le panneau de **Composants**, appuyez sur le bouton Installer.

Pour plus d&rsquo;information sur la procédure d&rsquo;installation, <a href="https://cordova.apache.org/docs/en/3.4.0/guide_platforms_ios_index.md.html#iOS%20Platform%20Guide" target="_blank">visitez le site</a> d&rsquo;Apache Cordova.

#### Installation d&rsquo;Ionic

Ionic possède son propre gestionnaire de commande en ligne, qui nous permettra par exemple de créer un nouveau projet, le déployer,&#8230;&nbsp;

Lancez la commande suivante pour installer Ionic :

<pre>$ [sudo] npm install -g ionic #Les crochets indiquent que "sudo" n'est pas toujours obligatoire</pre>

#### Création d&rsquo;un nouveau projet

<pre>$ ionic start todo blank</pre>

Nous venons de créer un dossier portant le nom « todo » et possédant l&rsquo;arborescence suivante :

<pre>$ cd todo && ls ├── bower.json     // dépendances bower ├── config.xml     // configuration cordova ├── gulpfile.js    // tâches gulp ├── hooks          // actions cordova ├── ionic.project  // configuration ionic ├── package.json   // dépendances node ├── platforms      // Les livrables pour iOS/Android se mettront ici ├── plugins        // Plugins cordova/ionic ├── scss           // code scss code, qui se générera du contenu dans www/css/ └── www            // Coeur de l'application - code JS et librairies, CSS, images, etc. </pre>

#### configuration des plateformes

Il nous faut maintenant ajouter iOS et Android comme plateformes à supporter dans notre projet

<pre>$ ionic platform add ios $ ionic platform add android </pre>

Il ne reste plus qu&rsquo;à compiler notre projet pour l&rsquo;une au l&rsquo;autre des plateforme, puis à tester depuis votre apparails (L&rsquo;émulateur peut être parfois long à démarrer):

<pre>$ ionic build ios $ ionic emulate ios </pre>

&nbsp;

### Développez votre application

Maintenant que vous avez configuré Cordova et Ionic, on peut à présent se concentrer sur le développement à proprement parlé.

Dans le dossier www, et si &nbsp;ce n&rsquo;est pas déjà fait, créez un fichier **index.html** contenant les lignes suivantes

<div class="highlight" style="color: #333333; font-family: 'Helvetica Neue', Helvetica, Arial, 'Lucida Grande', sans-serif; font-size: 15px; line-height: 21.4285507202148px; background-image: initial; background-attachment: initial; background-position: initial; background-repeat: initial;">
  <pre style="font-family: Monaco, Menlo, Consolas, 'Courier New', monospace; font-size: 14px; white-space: pre-wrap; padding: 10px; margin: 0px 0px 10.5px; line-height: 1.42857; color: #333333; border-width: 0px 0px 0px 4px; border-left-style: solid; border-left-color: #d7dbe4; background: #f0f3f8;"><code class="language-html" style="font-family: Monaco, Menlo, Consolas, 'Courier New', monospace; font-size: inherit; margin-left: 3px; margin-right: 3px; padding: 0px; color: inherit; border: 0px; background-color: transparent;" data-lang="html">&lt;span class="cp" style="color: #999999; font-weight: bold;">&lt;!DOCTYPE html&gt;&lt;/span>&lt;span class="nt" style="color: #000080;">&lt;html&gt;&lt;/span>   &lt;span class="nt" style="color: #000080;">&lt;head&gt;&lt;/span>     &lt;span class="nt" style="color: #000080;">&lt;meta&lt;/span> &lt;span class="na" style="color: #008080;">charset=&lt;/span>&lt;span class="s" style="color: #dd1144;">"utf-8"&lt;/span>&lt;span class="nt" style="color: #000080;">&gt;&lt;/span>     &lt;span class="nt" style="color: #000080;">&lt;title&gt;&lt;/span>Todo&lt;span class="nt" style="color: #000080;">&lt;/title&gt;&lt;/span>     &lt;span class="nt" style="color: #000080;">&lt;meta&lt;/span> &lt;span class="na" style="color: #008080;">name=&lt;/span>&lt;span class="s" style="color: #dd1144;">"viewport"&lt;/span> &lt;span class="na" style="color: #008080;">content=&lt;/span>&lt;span class="s" style="color: #dd1144;">"initial-scale=1, maximum-scale=1, user-scalable=no, width=device-width"&lt;/span>&lt;span class="nt" style="color: #000080;">&gt;&lt;/span>     &lt;span class="nt" style="color: #000080;">&lt;link&lt;/span> &lt;span class="na" style="color: #008080;">href=&lt;/span>&lt;span class="s" style="color: #dd1144;">"lib/ionic/css/ionic.css"&lt;/span> &lt;span class="na" style="color: #008080;">rel=&lt;/span>&lt;span class="s" style="color: #dd1144;">"stylesheet"&lt;/span>&lt;span class="nt" style="color: #000080;">&gt;&lt;/span>     &lt;span class="nt" style="color: #000080;">&lt;script &lt;/span>&lt;span class="na" style="color: #008080;">src=&lt;/span>&lt;span class="s" style="color: #dd1144;">"lib/ionic/js/ionic.bundle.js"&lt;/span>&lt;span class="nt" style="color: #000080;">&gt;&lt;/script&gt;&lt;/span>     &lt;span class="c" style="color: #999988; font-style: italic;">&lt;!-- Needed for Cordova/PhoneGap (will be a 404 during development) --&gt;&lt;/span>     &lt;span class="nt" style="color: #000080;">&lt;script &lt;/span>&lt;span class="na" style="color: #008080;">src=&lt;/span>&lt;span class="s" style="color: #dd1144;">"cordova.js"&lt;/span>&lt;span class="nt" style="color: #000080;">&gt;&lt;/script&gt;&lt;/span>   &lt;span class="nt" style="color: #000080;">&lt;/head&gt;&lt;/span>   &lt;span class="nt" style="color: #000080;">&lt;body&gt;&lt;/span>   &lt;span class="nt" style="color: #000080;">&lt;/body&gt;&lt;/span>&lt;span class="nt" style="color: #000080;">&lt;/html&gt;&lt;/span></code><code class="language-html" style="font-family: Monaco, Menlo, Consolas, 'Courier New', monospace; font-size: inherit; margin-left: 3px; margin-right: 3px; padding: 0px; color: inherit; border: 0px; background-color: transparent;" data-lang="html">&lt;span class="nt" style="color: #000080;">&lt;/span></code></pre></p>
</div>

Le fichier ionic.css contient les styles spécifiques à Ionic, tandis que le fichier ionic.bundle.js contient des modules <a href="https://angularjs.org/" target="_blank">Angular</a>&nbsp;: ngAnimate (pour les animations, transitions,&#8230;) et ngSanitize (qui gère notamment l&rsquo;affichage html). Pour ajouter d&rsquo;autres modules Angular, il faudra le faire de façon manuelle depuis le dossier **lib/js/angular** par exemple.&nbsp;

Le fichier cordova.js (ou phonegap.js) doit toujours être le dernier script à appeler dans l&rsquo;entête de votre page.

#### Playground

Ionic propose sa propre plateforme de teste en ligne. Vous pourrez développer des vues et les tester directement ligne depuis&nbsp;<a href="http://play.ionic.io/" target="_blank">http://play.ionic.io/</a>[](http://play.ionic.io/app/29fb5122f07a)

<pre><span style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;">&lt;!DOCTYPE html&gt;</span><br style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;" /><span style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;">&lt;html&gt;</span><br style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;" /><span style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;"> &lt;head&gt;</span><br style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;" /><span style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;"> &lt;meta charset="utf-8"&gt;</span><br style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;" /><span style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;"> &lt;meta name="viewport" content="initial-scale=1, maximum-scale=1, user-scalable=no, width=device-width"&gt;</span><br style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;" /><span style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;"> &lt;link href="</span><a href="https://charlesen.fr/wp-content/uploads/2015/07/code.ionicframework.com_1.0.0_css_ionic.min.css" target="_blank" rel="nofollow" style="color: #6611cc; cursor: text; font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;">http://code.ionicframework.com/1.0.0/css/ionic.min.css</a><span style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;">" rel="stylesheet"&gt;</span><br style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;" /><span style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;"> &lt;script src="</span><a href="https://charlesen.fr/wp-content/uploads/2015/07/code.ionicframework.com_1.0.0_js_ionic.bundle.js" target="_blank" rel="nofollow" style="color: #6611cc; cursor: text; font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;">http://code.ionicframework.com/1.0.0/js/ionic.bundle.js</a><span style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;">"&gt;&lt;/script&gt;</span><br style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;" /><span style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;"> &lt;/head&gt;</span><br style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;" /><span style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;"> &lt;body ng-app="app"&gt;</span><br style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;" /><span style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;">     &lt;ion-pane&gt;</span><br style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;" /><span style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;">        &lt;ion-header-bar class="bar-stable"&gt;</span><br style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;" /><span style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;">           &lt;h1 class="title"&gt;Mobile-tuts!&lt;/h1&gt;</span><br style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;" /><span style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;">       &lt;/ion-header-bar&gt;</span><br style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;" /><span style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;">       &lt;ion-content class="padding"&gt;</span><br style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;" /><span style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;">          &lt;button class="button button-assertive"&gt;Je suis un bouton&lt;/button&gt;</span><br style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;" /><span style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;">       &lt;/ion-content&gt;</span><br style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;" /><span style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;">      &lt;/ion-pane&gt;</span><br style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;" /><span style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;"> &lt;/body&gt;</span><br style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;" /><span style="color: rgba(0, 0, 0, 0.8); font-family: 'Roboto Slab', 'Times New Roman', serif; font-size: 14px; line-height: 19px; white-space: pre-wrap; background-color: #fafafa;">&lt;/html&gt;</span></pre>

<img loading="lazy" class=" size-full wp-image-237" src="https://charlesen.fr/wp-content/uploads/2015/07/images_ionic-screen-1.png" alt="" style="display: block; margin-left: auto; margin-right: auto;" width="403" height="756" srcset="https://charlesen.fr/wp-content/uploads/2015/07/images_ionic-screen-1.png 403w, https://charlesen.fr/wp-content/uploads/2015/07/images_ionic-screen-1-160x300.png 160w, https://charlesen.fr/wp-content/uploads/2015/07/images_ionic-screen-1-373x700.png 373w" sizes="(max-width: 403px) 100vw, 403px" /> 

#### Initialisation de l&rsquo;application

Maintenant que nous avons démarrer notre projet, nous pouvons commencer à développer avec Angular. Créez le fichier **www/js/app.js** contenant le code d&rsquo;initialisation suivant :

<div class="highlight" style="color: #333333; font-family: 'Helvetica Neue', Helvetica, Arial, 'Lucida Grande', sans-serif; font-size: 15px; line-height: 21.4285507202148px; background-image: initial; background-attachment: initial; background-position: initial; background-repeat: initial;">
  <pre style="font-family: Monaco, Menlo, Consolas, 'Courier New', monospace; font-size: 14px; white-space: pre-wrap; padding: 10px; margin: 0px 0px 10.5px; line-height: 1.42857; color: #333333; border-width: 0px 0px 0px 4px; border-left-style: solid; border-left-color: #d7dbe4; background: #f0f3f8;"><code class="language-javascript" style="font-family: Monaco, Menlo, Consolas, 'Courier New', monospace; font-size: inherit; margin-left: 3px; margin-right: 3px; padding: 0px; color: inherit; border: 0px; background-color: transparent;" data-lang="javascript">&lt;span class="nx">angular&lt;/span>&lt;span class="p">.&lt;/span>&lt;span class="nx">module&lt;/span>&lt;span class="p">(&lt;/span>&lt;span class="s1" style="color: #dd1144;">'todo'&lt;/span>&lt;span class="p">,&lt;/span> &lt;span class="p">[&lt;/span>&lt;span class="s1" style="color: #dd1144;">'ionic'&lt;/span>&lt;span class="p">])&lt;/span></code></pre></p>
</div>

Ceux qui connaissent un peu Angular auront compris que cette ligne permet la création d&rsquo;une application Angular dont le nom est **« todo »**. On précise au passage que l&rsquo;on aura besoin du module **« ionic »**, contenu dans le fichier bundles. &nbsp;

On peut à présent rajouter le fichier **app.js** au fichier principal **index.html**.&nbsp;

<div class="highlight" style="color: #333333; font-family: 'Helvetica Neue', Helvetica, Arial, 'Lucida Grande', sans-serif; font-size: 15px; line-height: 21.4285507202148px; background-image: initial; background-attachment: initial; background-position: initial; background-repeat: initial;">
  <pre style="font-family: Monaco, Menlo, Consolas, 'Courier New', monospace; font-size: 14px; white-space: pre-wrap; padding: 10px; margin: 0px 0px 10.5px; line-height: 1.42857; color: #333333; border-width: 0px 0px 0px 4px; border-left-style: solid; border-left-color: #d7dbe4; background: #f0f3f8;"><code class="language-html" style="font-family: Monaco, Menlo, Consolas, 'Courier New', monospace; font-size: inherit; margin-left: 3px; margin-right: 3px; padding: 0px; color: inherit; border: 0px; background-color: transparent;" data-lang="html">&lt;span class="nt" style="color: #000080;">&lt;script &lt;/span>&lt;span class="na" style="color: #008080;">src=&lt;/span>&lt;span class="s" style="color: #dd1144;">"js/app.js"&lt;/span>&lt;span class="nt" style="color: #000080;">&gt;&lt;/script&gt;&lt;/span> </code></pre>
  
  <p>
    Il faut également ajouter l&rsquo;attribut ng-app à la balise body dans le fichier index.html
  </p></p>
</div>

<pre style="font-family: Monaco, Menlo, Consolas, 'Courier New', monospace; font-size: 14px; white-space: pre-wrap; padding: 10px; margin: 0px 0px 10.5px; line-height: 1.42857; color: #333333; border-width: 0px 0px 0px 4px; border-left-style: solid; border-left-color: #d7dbe4; background: #f0f3f8;"><code class="language-html" style="font-family: Monaco, Menlo, Consolas, 'Courier New', monospace; font-size: inherit; margin-left: 3px; margin-right: 3px; padding: 0px; color: inherit; border: 0px; background-color: transparent;" data-lang="html">&lt;span class="nt" style="color: #000080;">&lt;body&lt;/span> &lt;span class="na" style="color: #008080;">ng-app=&lt;/span>&lt;span class="s" style="color: #dd1144;">"todo"&lt;/span>&lt;span class="nt" style="color: #000080;">&gt;&lt;/span></code></pre>

&nbsp;

Rajoutons un peu de contenu au corps de notre application :

<div class="highlight" style="color: #333333; font-family: 'Helvetica Neue', Helvetica, Arial, 'Lucida Grande', sans-serif; font-size: 15px; line-height: 21.4285507202148px; background-image: initial; background-attachment: initial; background-position: initial; background-repeat: initial;">
  <pre style="font-family: Monaco, Menlo, Consolas, 'Courier New', monospace; font-size: 14px; white-space: pre-wrap; padding: 10px; margin: 0px 0px 10.5px; line-height: 1.42857; color: #333333; border-width: 0px 0px 0px 4px; border-left-style: solid; border-left-color: #d7dbe4; background: #f0f3f8;"><code class="language-html" style="font-family: Monaco, Menlo, Consolas, 'Courier New', monospace; font-size: inherit; margin-left: 3px; margin-right: 3px; padding: 0px; color: inherit; border: 0px; background-color: transparent;" data-lang="html">&lt;span class="nt" style="color: #000080;">&lt;body&lt;/span> &lt;span class="na" style="color: #008080;">ng-app=&lt;/span>&lt;span class="s" style="color: #dd1144;">"todo"&lt;/span>&lt;span class="nt" style="color: #000080;">&gt;&lt;/span>   &lt;span class="nt" style="color: #000080;">&lt;ion-side-menus&gt;&lt;/span>     &lt;span class="c" style="color: #999988; font-style: italic;">&lt;!-- Center content --&gt;&lt;/span>     &lt;span class="nt" style="color: #000080;">&lt;ion-side-menu-content&gt;&lt;/span>       &lt;span class="nt" style="color: #000080;">&lt;ion-header-bar&lt;/span> &lt;span class="na" style="color: #008080;">class=&lt;/span>&lt;span class="s" style="color: #dd1144;">"bar-dark"&lt;/span>&lt;span class="nt" style="color: #000080;">&gt;&lt;/span>         &lt;span class="nt" style="color: #000080;">&lt;h1&lt;/span> &lt;span class="na" style="color: #008080;">class=&lt;/span>&lt;span class="s" style="color: #dd1144;">"title"&lt;/span>&lt;span class="nt" style="color: #000080;">&gt;&lt;/span>Todo&lt;span class="nt" style="color: #000080;">&lt;/h1&gt;&lt;/span>       &lt;span class="nt" style="color: #000080;">&lt;/ion-header-bar&gt;&lt;/span>       &lt;span class="nt" style="color: #000080;">&lt;ion-content&gt;&lt;/span>       &lt;span class="nt" style="color: #000080;">&lt;/ion-content&gt;&lt;/span>     &lt;span class="nt" style="color: #000080;">&lt;/ion-side-menu-content&gt;&lt;/span>     &lt;span class="c" style="color: #999988; font-style: italic;">&lt;!-- Left menu --&gt;&lt;/span>     &lt;span class="nt" style="color: #000080;">&lt;ion-side-menu&lt;/span> &lt;span class="na" style="color: #008080;">side=&lt;/span>&lt;span class="s" style="color: #dd1144;">"left"&lt;/span>&lt;span class="nt" style="color: #000080;">&gt;&lt;/span>       &lt;span class="nt" style="color: #000080;">&lt;ion-header-bar&lt;/span> &lt;span class="na" style="color: #008080;">class=&lt;/span>&lt;span class="s" style="color: #dd1144;">"bar-dark"&lt;/span>&lt;span class="nt" style="color: #000080;">&gt;&lt;/span>         &lt;span class="nt" style="color: #000080;">&lt;h1&lt;/span> &lt;span class="na" style="color: #008080;">class=&lt;/span>&lt;span class="s" style="color: #dd1144;">"title"&lt;/span>&lt;span class="nt" style="color: #000080;">&gt;&lt;/span>Projets&lt;span class="nt" style="color: #000080;">&lt;/h1&gt;&lt;/span>       &lt;span class="nt" style="color: #000080;">&lt;/ion-header-bar&gt;&lt;/span>     &lt;span class="nt" style="color: #000080;">&lt;/ion-side-menu&gt;&lt;/span>   &lt;span class="nt" style="color: #000080;">&lt;/ion-side-menus&gt;&lt;/span>&lt;span class="nt" style="color: #000080;">&lt;/body&gt;&lt;/span></code><code class="language-html" style="font-family: Monaco, Menlo, Consolas, 'Courier New', monospace; font-size: inherit; margin-left: 3px; margin-right: 3px; padding: 0px; color: inherit; border: 0px; background-color: transparent;" data-lang="html">&lt;span class="nt" style="color: #000080;">&lt;/span></code></pre></p>
</div>

&nbsp;

Qui donne le résultat suivant depuis le Playground Ionic

### Tester votre application

Il existe 4 façons de tester votre application : depuis un navigateur web, &nbsp;depuis un navigateur mobile, depuis un emulateur Android/iOS ou comme application native depuis votre smartphone.

#### Depuis un navigateur Web et Mobile

Depuis votre terminal, lancez la commande suivante :

<pre style="font-family: Monaco, Menlo, Consolas, 'Courier New', monospace; font-size: 14px; white-space: pre-wrap; padding: 10px; margin: 0px 0px 10.5px; line-height: 1.42857; color: #333333; border-width: 0px 0px 0px 4px; border-left-style: solid; border-left-color: #d7dbe4; background: #f0f3f8;"><code class="language-bash" style="font-family: Monaco, Menlo, Consolas, 'Courier New', monospace; font-size: inherit; margin-left: 3px; margin-right: 3px; padding: 0px; color: inherit; border: 0px; background-color: transparent;" data-lang="bash">&lt;span class="nv" style="color: #008080;">$ &lt;/span>ionic serve</code></pre>

Visitez ensuite l&rsquo;adresse <http://localhost:8000>&nbsp;depuis votre navigateur pour voir les changements en temps réels. Quand vous effectuez des changements dans vos pages HTML, CSS, Javascript,..ceux-ci sont rechargées automatiquement après sauvegarde des fichiers.

<img loading="lazy" class=" size-full wp-image-238" src="https://charlesen.fr/wp-content/uploads/2015/07/images_ionic-running.png" alt="" style="display: block; margin-left: auto; margin-right: auto;" width="394" height="638" srcset="https://charlesen.fr/wp-content/uploads/2015/07/images_ionic-running.png 394w, https://charlesen.fr/wp-content/uploads/2015/07/images_ionic-running-185x300.png 185w" sizes="(max-width: 394px) 100vw, 394px" /> 

#### Depuis un simulateur

Lancez la commande suivante pour démarrer un nouvel émulateur :

<div class="highlight" style="color: #333333; font-family: 'Helvetica Neue', Helvetica, Arial, 'Lucida Grande', sans-serif; font-size: 15px; line-height: 21.4285507202148px; background-image: initial; background-attachment: initial; background-position: initial; background-repeat: initial;">
  <pre style="font-family: Monaco, Menlo, Consolas, 'Courier New', monospace; font-size: 14px; white-space: pre-wrap; padding: 10px; margin: 0px 0px 10.5px; line-height: 1.42857; color: #333333; border-width: 0px 0px 0px 4px; border-left-style: solid; border-left-color: #d7dbe4; background: #f0f3f8;"><code class="language-bash" style="font-family: Monaco, Menlo, Consolas, 'Courier New', monospace; font-size: inherit; margin-left: 3px; margin-right: 3px; padding: 0px; color: inherit; border: 0px; background-color: transparent;" data-lang="bash">&lt;span class="nv" style="color: #008080;">$ &lt;/span>ionic build ios&lt;span class="nv" style="color: #008080;">$ &lt;/span>ionic emulate ios </code></pre></p>
</div>

cd

Depuis votre smartphone

Pour tester votre application sous Android, il vous faut simplement branchez votre smartphone en USB, puis de lancer la commande suivante :

<div class="highlight" style="color: #333333; font-family: 'Helvetica Neue', Helvetica, Arial, 'Lucida Grande', sans-serif; font-size: 15px; line-height: 21.4285507202148px; background-image: initial; background-attachment: initial; background-position: initial; background-repeat: initial;">
  <pre style="font-family: Monaco, Menlo, Consolas, 'Courier New', monospace; font-size: 14px; white-space: pre-wrap; padding: 10px; margin: 0px 0px 10.5px; line-height: 1.42857; color: #333333; border-width: 0px 0px 0px 4px; border-left-style: solid; border-left-color: #d7dbe4; background: #f0f3f8;"><code class="language-bash" style="font-family: Monaco, Menlo, Consolas, 'Courier New', monospace; font-size: inherit; margin-left: 3px; margin-right: 3px; padding: 0px; color: inherit; border: 0px; background-color: transparent;" data-lang="bash">&lt;span class="nv" style="color: #008080;">$ &lt;/span>ionic run android </code></pre>
  
  <p>
    <code class="language-bash" style="font-family: Monaco, Menlo, Consolas, 'Courier New', monospace; font-size: inherit; margin-left: 3px; margin-right: 3px; padding: 0px; color: inherit; border: 0px; background-color: transparent;" data-lang="bash">&nbsp;</code>
  </p></p>
</div>

Sous iOS, c&rsquo;est un peu plus compliqué car vous devez obligatoirement disposé d&rsquo;un compte sur l&rsquo;<a href="https://developer.apple.com/" target="_blank">Apple Developer</a> et ça coute la modique (:D) somme de 99$ seulement.

Vous devriez ensuite générer un certificat depuis l&rsquo;Apple Developper que vous pourrez configurer sur XCode.