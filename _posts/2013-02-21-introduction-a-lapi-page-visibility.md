---
id: 216
title: 'Introduction à l&rsquo;API Page Visibility'
date: 2013-02-21T07:42:48+01:00
author: charlesen
layout: post
guid: https://charlesen.fr/?p=216
permalink: /introduction-a-lapi-page-visibility/
image: /wp-content/uploads/2013/02/images_w3c.jpg
categories:
  - tutoriel
tags:
  - html
  - javascript
  - page visibility
  - w3C
  - web server
---
###<img loading="lazy" class=" size-full wp-image-214" style="display: block; margin-left: auto; margin-right: auto;" title="W3C Consortium" alt="W3C Consortium" src="https://charlesen.fr/wp-content/uploads/2013/02/images_w3c.jpg" width="315" height="48" srcset="https://charlesen.fr/wp-content/uploads/2013/02/images_w3c.jpg 315w, https://charlesen.fr/wp-content/uploads/2013/02/images_w3c-300x46.jpg 300w" sizes="(max-width: 315px) 100vw, 315px" /> 

### Introduction

<div>
</div></p> 

La spécification **Page visibility** définit un moyen pour les développeurs de &nbsp;déterminer la visibilité actuelle d&rsquo;un document (page) web et d&rsquo;être averti des changements de visibilité. Le développement traditionnel d&rsquo;une page web consiste à considérer comme visible toutes les pages web, ce qui peut se traduire par l&rsquo;utilisation d&rsquo;une quantité importante de ressources à la fois côté client et côté serveur.

<!--more-->

Un exemple intéressant est celui de facebook qui met à jour son fil d&rsquo;actualité lorsque vous êtes connecté à votre interface. Ce principe se retrouve également sur twitter et surement beaucoup d&rsquo;autres applications web.</p> 

La conception de pages Web avec la connaissance de l&rsquo;état de visibilité d&rsquo;une page permet non seulement d&rsquo;**améliorer l&rsquo;expérience utilisateur**, mais également les **performances de l&rsquo;application** concernée.</p> </p> 

<div>
</div>

<div>
</div></p> 

### 

### 

### 

### 

### 

### 

### 

### Types d&rsquo;applications

<div>
</div>

Prenons l&rsquo;exemple d&rsquo;un client de messagerie sur le web, un webmail, qui peut vérifier la présence ou non de nouveaux messages stockés sur un serveur distant et ce **toutes les secondes** lorsque votre page est dans l&rsquo;état **« visible »**. Par contre, si la page est dans un état **« hidden »** (caché), la vérification des messages ne se fera qu&rsquo;une fois toutes les minutes.</p> 

On peut prendre également l&rsquo;exemple d&rsquo;un jeu en ligne qui peut être mis en pause lorsque l&rsquo;utilisateur n&rsquo;a plus visible sur la page (changement d&rsquo;onglet, ordinateur en veille, &#8230;) .

En outre, cette interface peut être utilisée par les annonceurs pour ne pas facturer des annonces qui ne seraient pas visibles pour les utilisateurs.</p> 

<span style="font-family: 'book antiqua', palatino; font-size: 16px; line-height: 24px;">On voit bien avec ces exemples l&rsquo;intérêt d&rsquo;utiliser cet API. On gagne en <strong>performance </strong>(côté serveur) tout en conservant une bonne<strong> expérience utilisateur</strong>.</span></p> 

<span style="font-family: 'book antiqua', palatino; font-size: 16px; line-height: 24px;"><br /></span></p> 

### Utilisation de l&rsquo;API

<div>
</div></p> 

Revenons à notre webmail. Voici comment on implémenterait l&rsquo;interface Page Visibility</p> 

<table class="html4strict" style="border-collapse: collapse; width: 100%;">
  <tr>
    <td colspan="2" style="background: #dddddd; color: #054b6e; padding: 2px 0px; text-align: center; font: bold italic 12px Verdana, Geneva, Arial, Helvetica, sans-serif;">
      Exemple d&rsquo;utilisation de l&rsquo;API Page Visibility
    </td>
  </tr>
  
  <tr class="li1">
    <td style="width: 1px; background: #f0f0f0; vertical-align: top; color: #676f73; border-right: 1px dotted #dddddd; font-size: 12px; text-align: right;">
      <pre style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;">1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38 39 </pre>
    </td>
    
    <td style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;">
      <pre style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;"><span style="vertical-align: top;"><span style="color: #00bbdd;">&lt;!DOCTYPE html&gt;</span></span> <span style="vertical-align: top;"><span style="color: #009900;">&lt;<a href="http://december.com/html/4/element/html.html"><span style="color: #000000; font-weight: bold;">html</span></a>&gt;</span></span> <span style="vertical-align: top;"> <span style="color: #009900;">&lt;<a href="http://december.com/html/4/element/head.html"><span style="color: #000000; font-weight: bold;">head</span></a>&gt;</span></span> <span style="vertical-align: top;">  <span style="color: #009900;">&lt;<a href="http://december.com/html/4/element/script.html"><span style="color: #000000; font-weight: bold;">script</span></a>&gt;</span></span> <span style="vertical-align: top;">   var timer = 0;</span> <span style="vertical-align: top;">   var PERIOD_VISIBLE = 1000; // 1 secondes</span> <span style="vertical-align: top;">   var PERIOD_NOT_VISIBLE = 60000; // 60 secondes</span> <span style="vertical-align: top;">&nbsp;</span> <span style="vertical-align: top;">   function onLoad () {</span> <span style="vertical-align: top;">       timer = setInterval (checkEmail, isVisible() ? PERIOD_NOT_VISIBLE : PERIOD_VISIBLE);</span> <span style="vertical-align: top;">       if (document.addEventListener) document.addEventListener ("visibilitychange", visibilityChanged);</span> <span style="vertical-align: top;">   }</span> <span style="vertical-align: top;">&nbsp;</span> <span style="vertical-align: top;">   function visibilityChanged () {</span> <span style="vertical-align: top;">       clearTimeout (timer);</span> <span style="vertical-align: top;">       timer = setInterval (checkEmail, isVisible() ? PERIOD_NOT_VISIBLE: PERIOD_VISIBLE);</span> <span style="vertical-align: top;">   }</span> <span style="vertical-align: top;">&nbsp;</span> <span style="vertical-align: top;">   // Retourne un booléen</span> <span style="vertical-align: top;">   function isVisible() {</span> <span style="vertical-align: top;">     if (typeof document.hidden !== "undefined") {</span> <span style="vertical-align: top;">          return document.hidden; </span> <span style="vertical-align: top;">     } else if (typeof document.mozHidden !== "undefined") {</span> <span style="vertical-align: top;">          return document.mozHidden;</span> <span style="vertical-align: top;">     }  else if (typeof document.msHidden !== "undefined") {</span> <span style="vertical-align: top;">          return document.msHidden;</span> <span style="vertical-align: top;">     } else if (typeof document.webkitHidden !== "undefined") {</span> <span style="vertical-align: top;">          return document.webkitHidden;</span> <span style="vertical-align: top;">     }</span> <span style="vertical-align: top;">   }</span> <span style="vertical-align: top;">&nbsp;</span> <span style="vertical-align: top;">   checkEmail fonction () { </span> <span style="vertical-align: top;">       // Vérification des mails en Ajax+PHP par exemple</span> <span style="vertical-align: top;">   }</span> <span style="vertical-align: top;">  <span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><a href="http://december.com/html/4/element/script.html"><span style="color: #000000; font-weight: bold;">script</span></a>&gt;</span></span> <span style="vertical-align: top;"> <span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><a href="http://december.com/html/4/element/head.html"><span style="color: #000000; font-weight: bold;">head</span></a>&gt;</span></span> <span style="vertical-align: top;"> <span style="color: #009900;">&lt;<a href="http://december.com/html/4/element/body.html"><span style="color: #000000; font-weight: bold;">body</span></a> <span style="color: #000066;">onload</span><span style="color: #66cc66;">=</span><span style="color: #ff0000;">"onLoad()"</span>&gt;</span></span> <span style="vertical-align: top;"> <span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><a href="http://december.com/html/4/element/body.html"><span style="color: #000000; font-weight: bold;">body</span></a>&gt;</span></span> <span style="vertical-align: top;"><span style="color: #009900;">&lt;<span style="color: #66cc66;">/</span><a href="http://december.com/html/4/element/html.html"><span style="color: #000000; font-weight: bold;">html</span></a>&gt;</span></span></pre>
    </td>
  </tr>
</table></p> 

### 

### 

<div>
</div>

<div>
</div>

### Références

<div>
</div>

<li style="text-align: left;">
  <span style="font-size: 12pt;">Site du W3C :&nbsp;</span><a href="http://www.w3.org/TR/page-visibility/" style="font-family: 'book antiqua', palatino; font-size: 12pt;">http://www.w3.org/TR/page-visibility/</a>
</li>
<li style="text-align: left;">
  <span style="font-size: 16px; font-family: 'book antiqua', palatino;">Documentation pour Google chrome : &nbsp;</span><a href="https://developers.google.com/chrome/whitepapers/pagevisibility" style="font-family: 'book antiqua', palatino; font-size: 12pt;">https://developers.google.com/chrome/whitepapers/pagevisibility</a>
</li>

<ul style="text-align: left;">
  <li>
    <span style="font-size: 16px; font-family: 'book antiqua', palatino;">Documentation pour Firefox :&nbsp;</span>
  </li>
</ul>

[https://developer.mozilla.org/en-US/docs/DOM/Using\_the\_Page\_Visibility\_API](https://developer.mozilla.org/en-US/docs/DOM/Using_the_Page_Visibility_API)

<ul style="text-align: left;">
  <li>
    <span style="font-size: 16px; font-family: 'book antiqua', palatino;">Librairie Visibility.js : </span><a href="https://charlesen.fr/wp-content/uploads/2013/02/https%3A__github.com_ai_visibility.js" style="font-family: 'book antiqua', palatino; font-size: 12pt;">https://github.com/ai/visibility.js</a>
  </li>
</ul>

<li style="text-align: left;">
  <span style="font-size: 16px; font-family: 'book antiqua', palatino;"><br /></span>
</li>

<span style="font-size: 16px; line-height: 24px;"><br /></span>

  *