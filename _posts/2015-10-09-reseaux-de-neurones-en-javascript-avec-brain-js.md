---
id: 324
title: Réseaux de neurones en Javascript avec Brain.js
date: 2015-10-09T13:36:17+02:00
author: charlesen
layout: post
guid: https://charlesen.fr/?p=324
permalink: /reseaux-de-neurones-en-javascript-avec-brain-js/
image: /wp-content/uploads/2015/10/images_reseauxneurones.png
categories:
  - tutoriel
tags:
  - applications
  - apprentissage
  - artificielle
  - automatique
  - brain
  - brain.js
  - brainsjs
  - détection
  - intelligence
  - javascript
  - networks
  - neural
  - neurones
  - réseaux
---
Pour beaucoup de gens, faire de l'informatique se limite souvent à bidouiller son système d'exploitation (installer Windows 11 ! oui, oui c'est vrai), changer sa carte graphique, télécharger des fichiers mp3 ou encore jouer en réseau. Mais l'informatique, née de la recherche mathématiques, est beaucoup plus que ça, bien qu'elle soit aujourd'hui à la portée (il faut entendre accessible) de tous. Tant mieux d'ailleurs. Mais il est bien de se rappeler qu'au commencement de l'Informatique, il y a les mathématiques. La mécanique n'a pas disparu, elle est simplement enfouit dans les entrailles des processeurs de nos ordinateurs actuels. Son esprit, celui des mathématiques, aussi invisible soit-il, est bien présent. Là, au coeur de l'informatique.

Selon Wikipédia, et je l'approuve :

<p style="text-align: center;">
  <strong><em>« Un réseau de neurones (artificiel) est un modèle de calcul dont la conception est très schématiquement inspirée du fonctionnement des neurones biologiques. »</em></strong>
</p>

En clair, la branche appelée réseaux de neurones s'inspire du fonctionnement du cerveau pour élaborer des modèles algorithmiques (Tiens je me demande si la première définition n'était pas plus simple finalement).

Un algorithme simple se contente de résoudre (si possible) un problème particulier (transvaser des objets, suite de finobacci,...), tandis qu'un réseau de neurones s'adapte, se développe, reflechit et s'améliore à force d'apprentissage. Un peu comme notre cerveau, bien qu'un réseau de neurone ne prétend pas davantage imiter celui-ci, qu'une l'aile d'avion copie celle d'un oiseau.

<hr id="system-readmore" style="width: 921.688px; word-spacing: 0px;" />

Les réseaux de neurones ont permis de résoudre des problèmes complèxes, difficilement résolvables à partir de simples algorithmes. Citons par exemple La reconnaissance faciale (technique qui permet de retrouver une personne en fonction d'une image de son visage), largement utilisée dans la vidéo-surveillance (aéroport, site sensibles, rues,...), dans la recherche de personnes (un membre de la famille dont on aura pour seul souvenir une photo) ou encore la robotique.

Il existe de nombreux outils pour travailler avec les réseaux de neurones, mais nous nous interesserons dans cet article à une librairie Javascript appelée <a href="https://github.com/harthur/brain" target="_blank" rel="noopener"><strong>Brain.js</strong></a>.

Cette librairie nous évitera de faire des mathématiques pour mieux se concentrer sur les résultats escomptés. Si vous n'êtes pas très porté(e) sur les mathématique, pas de panique on fera pas. Brain.js simplifie énormément l'utilisation des réseaux de neurones en proposant très peu de méthodes au sein de son API. Gardons tout de même en mémoire les deux étapes à respecter à savoir : Apprentissage et Détection Automatique (Probabilités)

Le but de l'entraînement est de permettre au réseau de neurones « d’apprendre » à partir d'exemples données en entrée du système. Si l’entraînement est correctement réalisé, le réseau est capable de fournir des réponses en sortie très proches des valeurs d’origines du jeu de données d’entraînement. Mais tout l’intérêt des réseaux de neurones réside dans leur capacité à généraliser à partir du jeu de test.

Pour permettre la détection automatique d'un OU-exclusif (XOR), un exemple classique, il suffit de faire :

<pre style="color: #333333; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; font-size: 13px; margin: 0px 0px 10px; overflow: auto; padding: 0px; line-height: 1.42857; border: none; background-image: none; background-attachment: initial; background-position: initial; background-repeat: initial;"><code class="language-javascript hljs" style="font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; font-size: inherit; padding: 0.5em; color: #f8f8f2; white-space: pre-wrap; display: block; background: #23241f;">&lt;span class="hljs-keyword" style="color: #f92672;">var&lt;/span> brain = &lt;span class="hljs-built_in" style="color: #e6db74;">require&lt;/span>(&lt;span class="hljs-string" style="color: #e6db74;">'brain'&lt;/span>);&lt;span class="hljs-keyword" style="color: #f92672;">var&lt;/span> net = &lt;span class="hljs-keyword" style="color: #f92672;">new&lt;/span> brain.NeuralNetwork(); net.train([{input: [&lt;span class="hljs-number" style="color: #ae81ff;">0&lt;/span>, &lt;span class="hljs-number" style="color: #ae81ff;">0&lt;/span>], output: [&lt;span class="hljs-number" style="color: #ae81ff;">0&lt;/span>]},              {input: [&lt;span class="hljs-number" style="color: #ae81ff;">0&lt;/span>, &lt;span class="hljs-number" style="color: #ae81ff;">1&lt;/span>], output: [&lt;span class="hljs-number" style="color: #ae81ff;">1&lt;/span>]},            {input: [&lt;span class="hljs-number" style="color: #ae81ff;">1&lt;/span>, &lt;span class="hljs-number" style="color: #ae81ff;">0&lt;/span>], output: [&lt;span class="hljs-number" style="color: #ae81ff;">1&lt;/span>]},            {input: [&lt;span class="hljs-number" style="color: #ae81ff;">1&lt;/span>, &lt;span class="hljs-number" style="color: #ae81ff;">1&lt;/span>], output: [&lt;span class="hljs-number" style="color: #ae81ff;">0&lt;/span>]}]);&lt;span class="hljs-keyword" style="color: #f92672;">var&lt;/span> output = net.run([&lt;span class="hljs-number" style="color: #ae81ff;">1&lt;/span>, &lt;span class="hljs-number" style="color: #ae81ff;">0&lt;/span>]);  &lt;span class="hljs-comment" style="color: #75715e;">// [0.933]  &lt;/span> </code></pre>

Dans l'exemple ci-dessus, on commence par entrainer (apprentissage) notre Réseau en lui disant : Si tu vois O et O, alors renvoie 0, puis si tu vois 0 et 1, renvoie 1,&#8230;

A la dernière ligne, on teste ensuite le réseau en lui demandant ce que pourrait renvoyer les entrées 1 et 0. Ce qu'il répond par 0.933, soit environ 1.

On pourrait également imaginer un autre système qui permettrait par exemple de détecter automatiquement l'humeur des gens en fonctions des textes qu'ils publient sur internet par exemple. Avec implémenter un tel système avec Brain.js est d'une facilité déconcertante.

La librairie propose différentes options suffiantes pour créer un réseau simple et puissant à la fois :

<pre style="color: #333333; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; font-size: 13px; margin: 0px 0px 10px; overflow: auto; padding: 0px; line-height: 1.42857; border: none; background-image: none; background-attachment: initial; background-position: initial; background-repeat: initial;"><code class="language-javascript hljs" style="font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; font-size: inherit; padding: 0.5em; color: #f8f8f2; white-space: pre-wrap; display: block; background: #23241f;">&lt;span class="hljs-keyword" style="color: #f92672;">var&lt;/span> net = &lt;span class="hljs-keyword" style="color: #f92672;">new&lt;/span> brain.NeuralNetwork({       hiddenLayers: [&lt;span class="hljs-number" style="color: #ae81ff;">128&lt;/span>,&lt;span class="hljs-number" style="color: #ae81ff;">64&lt;/span>] }); net.train({       errorThresh: &lt;span class="hljs-number" style="color: #ae81ff;">0.005&lt;/span>,  &lt;span class="hljs-comment" style="color: #75715e;">// seul d'erreur acceptable&lt;/span>     iterations: &lt;span class="hljs-number" style="color: #ae81ff;">20000&lt;/span>,   &lt;span class="hljs-comment" style="color: #75715e;">// Nombre maximum d'iterations durant l'apprentissage &lt;/span>     log: &lt;span class="hljs-literal" style="color: #ae81ff;">true&lt;/span>,           &lt;span class="hljs-comment" style="color: #75715e;">// Affichage des logs avec console.log() &lt;/span>     logPeriod: &lt;span class="hljs-number" style="color: #ae81ff;">10&lt;/span>,       &lt;span class="hljs-comment" style="color: #75715e;">// Nombres d'itérations entre les logs &lt;/span>     learningRate: &lt;span class="hljs-number" style="color: #ae81ff;">0.3&lt;/span>    &lt;span class="hljs-comment" style="color: #75715e;">// Taux d'apprentissage &lt;/span> }); </code></pre>

N'hésitez pas à visiter le <a href="https:/github.com/harthur/brain%20Réseaux%20de%20neurones%20artificiels%20:%20https:/fr.wikipedia.org/wiki/R%C3%A9seau_de_neurones_artificiels" target="_blank" rel="noopener">site de la Librairie</a> pour plus d'informations sur les options, le projet,&#8230; Vous n'avez pas finit d'aimer l'intelligence artificielle.

### Plus d'informations

  * Site du projet Brain.js : <https://github.com/harthur/brain>
  * Réseaux de neurones artificiels : [https://fr.wikipedia.org/wiki/R%C3%A9seau\_de\_neurones_artificiels](https://fr.wikipedia.org/wiki/R%C3%A9seau_de_neurones_artificiels)