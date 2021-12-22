---
id: 319
title: Google lance le projet AMP (Accelerated Mobile Pages)
date: 2015-10-08T09:32:23+02:00
author: charlesen
layout: post
guid: https://charlesen.fr/?p=319
permalink: /google-lance-le-projet-amp/
image: /wp-content/uploads/2015/10/images_blog_google-amp.png
categories:
  - news
tags:
  - accelerated
  - amp
  - google
  - mobile
  - pages
  - project
  - publisher
---
Les mobiles (smartphone, tablettes,&#8230;) font aujourd&rsquo;hui partie de notre quotidien. Il ne se passe pas une seconde (j&rsquo;exagère peut être un peu) sans que nous nous retrouvions à pianoter sur notre téléphone mobile ou tablette à la recherche d&rsquo;articles de presse sur internet, du dernier film sorti au cinéma, du score du dernier classico (**_Ici c&rsquo;est PARIS !_**) ou encore des dernières news sur Facebook, Google+, Twitter, &#8230; Bref, nous consommons énormement de contenus sur internet via nos appareils mobiles et ça les éditeurs de site d&rsquo;informations l&rsquo;ont bien compris&#8230;tout comme GOOGLE (enfin, [Alphabet](index.php?option=com_content&view=article&id=151:google-et-sanofi-s-attaquent-ensemble-au-diabete&catid=36&Itemid=55)) d&rsquo;ailleurs.

<!--more-->

Le hic, c&rsquo;est qu&rsquo;il n&rsquo;est pas toujours évident de consulter ces contenus en lignes en raison de fortes latences du côté des technologies mobiles (Edge, 3G+ ou 4G+ pour les plus chanceux). Et dans une société comme la notre où l&rsquo;on veut TOUT dans la seconde même, de nombreux utilisateurs se découragent très peu de temps après avoir cliqué sur un lien.

_**Chaque fois qu&rsquo;une page met du temps à se charger, les sites d&rsquo;informations perdent des mobinautes et surtout l&rsquo;opportunité de faire des bénéfices via la publicité et les contenus sponsorisés.**_

C&rsquo;est pour résoudre tous ces problèmes (ou presque) que Google a lancé le projet AMP, en partenariat avec de célèbres éditeurs de contenus en ligne (BBC, Buzzfeed, Mashable, The Economist, Les Echos,&#8230;) et des entreprises du domaine des nouvelles technologies (Google, Adobe, LinkedIn, Twitter, WordPress,&#8230;)

Objectif affiché : permettre un chargement instantané de contenus multimédias (vidéos, animations, publicités,&#8230;) sur tout type d&rsquo;appareil mobile (smartphone, tablette,&#8230;).

Le projet utilise un framework appelé <a href="https://github.com/ampproject/amphtml" target="_blank" rel="noopener">AMP HTML</a>, qui permettra  une meilleur gestion du cache et des performances des navigateurs. Il suffira pour intégrer le framework d&rsquo;insérer un petit fichier Javascript disponible à l&rsquo;adresse [https://cdn.ampproject.org/v0.js](https://charlesen.fr/wp-content/uploads/2015/10/https%3A__cdn.ampproject.org_v0.js), sans oublier d&rsquo;insérer les bonnes métadonnées (viewport, canonical,&#8230;)

<div class="highlight highlight-text-html-basic" style="margin-bottom: 16px; color: #333333; font-family: 'Helvetica Neue', Helvetica, 'Segoe UI', Arial, freesans, sans-serif; font-size: 16px; line-height: 25.6px;">
  <pre style="overflow: auto; font-family: Consolas, 'Liberation Mono', Menlo, Courier, monospace; font-size: 13.6px; margin-top: 0px; margin-bottom: 0px; line-height: 1.45; padding: 16px; background-color: #f7f7f7;">&lt;!doctype html&gt; &lt;<span class="pl-ent" style="color: #63a35c;">html</span> ⚡&gt; &lt;<span class="pl-ent" style="color: #63a35c;">head</span>&gt;   &lt;<span class="pl-ent" style="color: #63a35c;">meta</span> <span class="pl-e" style="color: #795da3;">charset</span>=<span class="pl-s" style="color: #183691;"><span class="pl-pds">"</span>utf-8<span class="pl-pds">"</span></span>&gt;   &lt;<span class="pl-ent" style="color: #63a35c;">link</span> <span class="pl-e" style="color: #795da3;">rel</span>=<span class="pl-s" style="color: #183691;"><span class="pl-pds">"</span>canonical<span class="pl-pds">"</span></span> <span class="pl-e" style="color: #795da3;">href</span>=<span class="pl-s" style="color: #183691;"><span class="pl-pds">"</span>hello-world.html<span class="pl-pds">"</span></span> &gt;   &lt;<span class="pl-ent" style="color: #63a35c;">meta</span> <span class="pl-e" style="color: #795da3;">name</span>=<span class="pl-s" style="color: #183691;"><span class="pl-pds">"</span>viewport<span class="pl-pds">"</span></span> <span class="pl-e" style="color: #795da3;">content</span>=<span class="pl-s" style="color: #183691;"><span class="pl-pds">"</span>width=device-width,initial-scale=1,minimum-scale=1,maximum-scale=1,user-scalable=no,minimal-ui<span class="pl-pds">"</span></span>&gt; <span class="pl-s1">  &lt;<span class="pl-ent" style="color: #63a35c;">script</span> <span class="pl-e" style="color: #795da3;">src</span>=<span class="pl-s" style="color: #183691;"><span class="pl-pds">"</span>https://cdn.ampproject.org/v0.js<span class="pl-pds">"</span></span> <span class="pl-e" style="color: #795da3;">async</span>&gt;&lt;/<span class="pl-ent" style="color: #63a35c;">script</span>&gt;</span> <span class="pl-s1">  &lt;<span class="pl-ent" style="color: #63a35c;">style</span>&gt;<span class="pl-ent" style="color: #63a35c;">body</span> {<span class="pl-c1" style="color: #0086b3;"><span class="pl-c1">opacity</span></span>: <span class="pl-c1" style="color: #0086b3;"></span>}&lt;/<span class="pl-ent" style="color: #63a35c;">style</span>&gt;</span>&lt;<span class="pl-ent" style="color: #63a35c;">noscript</span>&gt;<span class="pl-s1">&lt;<span class="pl-ent" style="color: #63a35c;">style</span>&gt;<span class="pl-ent" style="color: #63a35c;">body</span> {<span class="pl-c1" style="color: #0086b3;"><span class="pl-c1">opacity</span></span>: <span class="pl-c1" style="color: #0086b3;">1</span>}&lt;/<span class="pl-ent" style="color: #63a35c;">style</span>&gt;</span>&lt;/<span class="pl-ent" style="color: #63a35c;">noscript</span>&gt; &lt;/<span class="pl-ent" style="color: #63a35c;">head</span>&gt; &lt;<span class="pl-ent" style="color: #63a35c;">body</span>&gt;Hello World!&lt;/<span class="pl-ent" style="color: #63a35c;">body</span>&gt; &lt;/<span class="pl-ent" style="color: #63a35c;">html</span>&gt;</pre>
</div>

Ce bout de code permet d&rsquo;inclure :

  * La libraire Javascript de l&rsquo;AMP
  * Le validateur AMP qui permettra (certainement) à Google de distinguer les pages conformes aux spécificationx du projet (ceci pourrait, dans l&rsquo;avenir, jouer dans le référencement)
  * Des <a href="http://www.html5rocks.com/en/tutorials/webcomponents/customelements/" target="_blank" rel="noopener">composants HTML</a> beaucoup plus spécifiques aux contenus (autres que de simples balises **_div_** qui peuvent dire tout et n&rsquo;importe quoi)

&nbsp;

### Plus d&rsquo;informations

  * Introducing the Accelerated Mobile Pages Project, for a faster, open mobile web : <http://googlepolicyeurope.blogspot.fr/2015/10/introducing-accelerated-mobile-pages.html>
  * Site internet du projet AMP : <https://www.ampproject.org/>
  * AMP HTML : <https://github.com/ampproject/amphtml>