---
id: 76
title: Un script de détection de mobiles en PHP
date: 2010-12-29T23:23:02+01:00
author: charlesen
layout: post
guid: https://charlesen.fr/?p=76
permalink: /un-script-de-detection-de-mobiles-en-php/
image: /wp-content/uploads/2010/12/images_mwi.png
categories:
  - tutoriel
tags:
  - android php
  - code php pour détecter les mobile
  - détecter agent mobile php
  - "Détecter si le visiteur vient d'un iPhone iPad iPod Android"
  - Détecter téléphone portable
  - Détection des mobiles en php
  - développement mobile
  - Ipad
  - Iphone
  - Ipod
  - smartphone
---
<span style="font-family: book antiqua,palatino; font-size: 12pt;"><img loading="lazy" class=" alignright size-full wp-image-75" style="float: right;" src="https://charlesen.fr/wp-content/uploads/2010/12/images_mwi.png" alt="Logo du Mobile Web Initiative" title="Logo du Mobile Web Initiative" width="345" height="92" srcset="https://charlesen.fr/wp-content/uploads/2010/12/images_mwi.png 345w, https://charlesen.fr/wp-content/uploads/2010/12/images_mwi-300x80.png 300w" sizes="(max-width: 345px) 100vw, 345px" />A l&rsquo;heure où les Smartphones sont de plus en plus utilisés pour naviguer sur internet, de nombreux internautes commencent à adapter leur site internet à ces nouveaux clients web. Voici un script simple qui vous permettra de facilement détecter un mobile , afin par exemple de charger une feuille de style bien spécifique à un type d&rsquo;OS: </span>

<!--more-->

 <span style="font-family: book antiqua,palatino; font-size: 12pt;"><code>&lt;span style="font-family: courier new, courier, monospace;">&lt;br />&lt;span>&lt;&lt;/span>?php&lt;br />&nbsp;&nbsp; if (stristr($_SERVER['HTTP_USER_AGENT'], "&lt;/span>&lt;span style="font-family: book antiqua,palatino; font-size: 12pt;">&lt;span style="font-family: courier new, courier, monospace;">Android&lt;/span>&lt;/span>&lt;span style="font-family: book antiqua,palatino; font-size: 12pt;">&lt;span style="font-family: courier new, courier, monospace;">") &lt;br />&nbsp;&nbsp; || strpos($_SERVER['HTTP_USER_AGENT'], "iPod") &lt;br />&nbsp;&nbsp; || strpos($_SERVER['HTTP_USER_AGENT'], "iPhone") ) &lt;br />&nbsp;&nbsp; { &lt;br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; // Mettre ici du code php optimisé pour les mobiles&lt;br />&nbsp;&nbsp; }&lt;br />&nbsp;&nbsp; else {&lt;br />&nbsp;&nbsp;&nbsp;&nbsp; // Et ici du code php classique...Pas forcement optimisé :)&lt;br />&nbsp;&nbsp; }&lt;br />?&lt;span>&gt;&lt;/span>&lt;/span>&lt;br />&lt;/span></code> </span>

<div style="position: absolute; left: -10000px; top: 0px; width: 1px; height: 1px; overflow: hidden;" class="mcePaste" id="_mcePaste">
  <span style="font-family: book antiqua,palatino; font-size: 12pt;"><span style="font-family: courier new, courier, monospace;">Android</span></span>
</div>