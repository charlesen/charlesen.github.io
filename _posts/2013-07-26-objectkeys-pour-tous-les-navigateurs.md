---
id: 221
title: Object.keys pour tous les navigateurs
date: 2013-07-26T06:18:59+02:00
author: charlesen
layout: post
guid: https://charlesen.fr/?p=221
permalink: /objectkeys-pour-tous-les-navigateurs/
categories:
  - tutoriel
tags:
  - array
  - cross-plateform
  - hacks
  - javascript
  - objects
  - objects.keys
---
</p> 

La fonction keys de l&rsquo;élément Object permet de transformer un objet javascript en tableau, ce qui permet d&rsquo;utiliser des propriétés spécifiques au tableau comme la propriété length, non disponible pour un objet classique. &nbsp;Prenons l&rsquo;exemple suivant :&nbsp;

<table class="javascript" style="border-collapse: collapse; width: 100%;">
  <tr>
    <td colspan="2" style="background: #dddddd; color: #054b6e; padding: 2px 0px; text-align: center; font: bold italic 12px Verdana, Geneva, Arial, Helvetica, sans-serif;">
      Utilisation de la fonction Keys
    </td>
  </tr>
  
  <tr class="li1">
    <td style="width: 1px; background: #f0f0f0; vertical-align: top; color: #676f73; border-right: 1px dotted #dddddd; font-size: 12px; text-align: right;">
      <pre style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;">1 2 3 4 5 6 7 8 9 </pre>
    </td>
    
    <td style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;">
      <pre style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;"><span style="vertical-align: top;"><span style="color: #006600; font-style: italic;">// On déclare un objet contenant des données</span></span> <span style="vertical-align: top;"><span style="color: #003366; font-weight: bold;">var</span> citiesObj <span style="color: #339933;">=</span> <span style="color: #009900;">{</span> <span style="color: #3366cc;">'troyes'</span><span style="color: #339933;">:</span><span style="color: #3366cc;">'aube'</span><span style="color: #339933;">,</span> <span style="color: #3366cc;">'nancy'</span><span style="color: #339933;">:</span><span style="color: #3366cc;">'meurthe-et-moselle'</span> <span style="color: #009900;">}</span><span style="color: #339933;">;</span></span> <span style="vertical-align: top;">&nbsp;</span> <span style="vertical-align: top;"><span style="color: #006600; font-style: italic;">// On le transforme ensuite en tableau pour pouvoir le manipuler</span></span> <span style="vertical-align: top;"><span style="color: #003366; font-weight: bold;">var</span> citiesArray <span style="color: #339933;">=</span> Object.<span style="color: #660066;">keys</span><span style="color: #009900;">(</span> citiesObj <span style="color: #009900;">)</span><span style="color: #339933;">;</span></span> <span style="vertical-align: top;">&nbsp;</span> <span style="vertical-align: top;"><span style="color: #006600; font-style: italic;">// Taille du tableau</span></span> <span style="vertical-align: top;"><span style="color: #003366; font-weight: bold;">var</span> citiesLen <span style="color: #339933;">=</span> citiesArray.<span style="color: #660066;">length</span><span style="color: #339933;">;</span></span> <span style="vertical-align: top;">console.<span style="color: #660066;">log</span><span style="color: #009900;">(</span> citiesLen  <span style="color: #009900;">)</span> <span style="color: #006600; font-style: italic;">// Renvoie "2"</span></span></pre>
    </td>
  </tr>
</table>

Cependant la fonction Object.keys() n&rsquo;est pas disponible sur l&rsquo;ancien des navigateurs. Sous IE elle n&rsquo;est disponible qu&rsquo;à partir de la version 9. Voici donc un hack permettant de supporter l&rsquo;ensemble des navigateurs :</p> 

<table class="javascript" style="border-collapse: collapse; width: 100%;">
  <tr>
    <td colspan="2" style="background: #dddddd; color: #054b6e; padding: 2px 0px; text-align: center; font: bold italic 12px Verdana, Geneva, Arial, Helvetica, sans-serif;">
      Définition de la fonction Object.keys pour les anciens navigateurs
    </td>
  </tr>
  
  <tr class="li1">
    <td style="width: 1px; background: #f0f0f0; vertical-align: top; color: #676f73; border-right: 1px dotted #dddddd; font-size: 12px; text-align: right;">
      <pre style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;">1 2 3 4 5 6 7 8 9 10 </pre>
    </td>
    
    <td style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;">
      <pre style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;"><span style="vertical-align: top;"><span style="color: #006600; font-style: italic;">/**</span></span> <span style="vertical-align: top;"><span style="color: #006600; font-style: italic;">** Set Object.keys if undefined</span></span> <span style="vertical-align: top;"><span style="color: #006600; font-style: italic;">**/</span></span> <span style="vertical-align: top;"><span style="color: #000066; font-weight: bold;">if</span> <span style="color: #009900;">(</span><span style="color: #339933;">!</span>Object.<span style="color: #660066;">keys</span><span style="color: #009900;">)</span> Object.<span style="color: #660066;">keys</span> <span style="color: #339933;">=</span> <span style="color: #003366; font-weight: bold;">function</span><span style="color: #009900;">(</span>o<span style="color: #009900;">)</span> <span style="color: #009900;">{</span></span> <span style="vertical-align: top;">  <span style="color: #000066; font-weight: bold;">if</span> <span style="color: #009900;">(</span>o <span style="color: #339933;">!==</span> Object<span style="color: #009900;">(</span>o<span style="color: #009900;">)</span><span style="color: #009900;">)</span> <span style="color: #000066; font-weight: bold;">throw</span> <span style="color: #003366; font-weight: bold;">new</span> TypeError<span style="color: #009900;">(</span><span style="color: #3366cc;">'Object.keys called on a non-object'</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span></span> <span style="vertical-align: top;">  <span style="color: #003366; font-weight: bold;">var</span> k<span style="color: #339933;">=</span><span style="color: #009900;">[</span><span style="color: #009900;">]</span><span style="color: #339933;">,</span>p<span style="color: #339933;">;</span></span> <span style="vertical-align: top;">  <span style="color: #000066; font-weight: bold;">for</span> <span style="color: #009900;">(</span>p <span style="color: #000066; font-weight: bold;">in</span> o<span style="color: #009900;">)</span> <span style="color: #000066; font-weight: bold;">if</span> <span style="color: #009900;">(</span>Object.<span style="color: #660066;">prototype</span>.<span style="color: #660066;">hasOwnProperty</span>.<span style="color: #660066;">call</span><span style="color: #009900;">(</span>o<span style="color: #339933;">,</span>p<span style="color: #009900;">)</span><span style="color: #009900;">)</span> k.<span style="color: #660066;">push</span><span style="color: #009900;">(</span>p<span style="color: #009900;">)</span><span style="color: #339933;">;</span></span> <span style="vertical-align: top;">  <span style="color: #000066; font-weight: bold;">return</span> k<span style="color: #339933;">;</span></span> <span style="vertical-align: top;"><span style="color: #009900;">}</span></span> <span style="vertical-align: top;">&nbsp;</span></pre>
    </td>
  </tr>
</table>

Plus qu&rsquo;à rajouter ça dans le fichier **app.js** ou **core.js** de votre application. Vous avez le pouvoir !