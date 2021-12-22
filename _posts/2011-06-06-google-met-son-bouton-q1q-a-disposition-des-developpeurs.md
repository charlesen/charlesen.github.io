---
id: 179
title: Google met son bouton « +1 » à disposition des développeurs
date: 2011-06-06T11:54:37+02:00
author: charlesen
layout: post
guid: https://charlesen.fr/?p=179
permalink: /google-met-son-bouton-q1q-a-disposition-des-developpeurs/
image: /wp-content/uploads/2011/06/images_google_button.png
categories:
  - news
---
<img loading="lazy" class=" alignleft size-full wp-image-178" style="margin-right: 10px; float: left;" title="Google Button" src="https://charlesen.fr/wp-content/uploads/2011/06/images_google_button.png" alt="Google Button" width="196" height="126" />Cela avait été annoncé lors du [dernier Google I/O](http://www.mobile-tuts.com/actualite-mobile/81-retour-sur-les-annonces-du-geant-de-linternet-lors-du-google-io-2011-1ere-partie.html "Retour sur les annonces du Google I/O 2011"). Avec son bouton « +1 », Google espère améliorer davantage ses résultats de recherche. L&rsquo;algorithme prendra désormais en compte le clique sur ce bouton « +1 », qui vient un peu comme une réponse au bouton « Like » de Facebook. Ce bouton permet de recommander vos articles, vos pages dans le moteur de recherche et s&rsquo;intègre très facilement un site web.

<!--more-->

 

Il suffit pour cela d&rsquo;aller sur le [site dédié au widget](http://www.google.com/webmasters/+1/button/index.html "Voir le code d'intégration du bouton Google"), et de compléter&nbsp; (éventuellement) le formulaire, avant de générer le code ci-dessus :

 

<table class="abap" style="border-collapse: collapse; width: 100%;">
  <tr>
    <td style="background: #dddddd; color: #054b6e; padding: 2px 0px; text-align: center; font: bold italic 12px Verdana, Geneva, Arial, Helvetica, sans-serif;" colspan="2">
      Code d&rsquo;intégration du Bouton Google
    </td>
  </tr>
  
  <tr class="li1">
    <td style="width: 1px; background: #f0f0f0; vertical-align: top; color: #676f73; border-right: 1px dotted #dddddd; font-size: 12px; text-align: right;">
      <pre style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;">1 2 3 4 5 6 7 </pre>
    </td>
    
    <td style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;">
      <pre style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;"><span style="vertical-align: top;">&lt;<span style="color: #66cc66;">!--</span> Placez cette balise dans la section &lt;head&gt; ou juste avant la balise de fermeture &lt;<span style="color: #66cc66;">/</span>body&gt; <span style="color: #66cc66;">--</span>&gt;</span> <span style="vertical-align: top;">&lt;script <span style="color: #993333;">type</span><span style="color: #66cc66;">=</span><span style="color: #808080; font-style: italic;">"text/javascript" src="http://apis.google.com/js/plusone.js"&gt;</span></span> <span style="vertical-align: top;">  <span style="color: #66cc66;">{</span>lang<span style="color: #66cc66;">:</span> <span style="color: #ff0000;">'fr'</span><span style="color: #66cc66;">}</span></span> <span style="vertical-align: top;">&lt;<span style="color: #66cc66;">/</span>script&gt;</span> <span style="vertical-align: top;">&nbsp;</span> <span style="vertical-align: top;">&lt;<span style="color: #66cc66;">!--</span> Placez cette balise à l<span style="color: #ff0000;">'endroit où vous souhaitez que le bouton +1 s'</span>affiche <span style="color: #66cc66;">--</span>&gt;</span> <span style="vertical-align: top;">&lt;g<span style="color: #66cc66;">:</span>plusone&gt;&lt;<span style="color: #66cc66;">/</span>g<span style="color: #66cc66;">:</span>plusone&gt;</span></pre>
    </td>
  </tr>
</table>

 

#### Pour plus d&rsquo;informations :

  * [Documentation officielle](http://code.google.com/intl/fr/apis/+1button/ "Voir la doc officielle")