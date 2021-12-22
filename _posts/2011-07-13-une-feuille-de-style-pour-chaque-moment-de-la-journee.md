---
id: 201
title: Une feuille de style pour chaque moment de la journée
date: 2011-07-13T18:27:40+02:00
author: charlesen
layout: post
guid: https://charlesen.fr/?p=201
permalink: /une-feuille-de-style-pour-chaque-moment-de-la-journee/
categories:
  - tutoriel
---
Le style de votre page qui s&rsquo;adapte en fonction du moment de la journée (Matin, Après-midi, Soir)

ça fait rêvé hein ?

Voici comment faire ça simplement et en Javascript, comme ça tout le monde est content, pas de PHP, de Java ou de Ruby&#8230;juste un script côté client :

<!--more-->

 

<table class="javascript" style="border-collapse: collapse; width: 100%;">
  <tr class="li1">
    <td style="width: 1px; background: #f0f0f0; vertical-align: top; color: #676f73; border-right: 1px dotted #dddddd; font-size: 12px; text-align: right;">
      <pre style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;">1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 </pre>
    </td>
    
    <td style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;">
      <pre style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;"><span style="vertical-align: top;"><span style="color: #339933;">&lt;</span>script type<span style="color: #339933;">=</span><span style="color: #3366cc;">"text/JavaScript"</span><span style="color: #339933;">&gt;</span></span> <span style="vertical-align: top;"><span style="color: #339933;">&lt;!--</span></span> <span style="vertical-align: top;"><span style="color: #003366; font-weight: bold;">function</span> getStylesheet<span style="color: #009900;">(</span><span style="color: #009900;">)</span> <span style="color: #009900;">{</span></span> <span style="vertical-align: top;">      <span style="color: #003366; font-weight: bold;">var</span> currentTime <span style="color: #339933;">=</span> <span style="color: #003366; font-weight: bold;">new</span> Date<span style="color: #009900;">(</span><span style="color: #009900;">)</span>.<span style="color: #660066;">getHours</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span></span> <span style="vertical-align: top;">      <span style="color: #000066; font-weight: bold;">if</span> <span style="color: #009900;">(</span><span style="color: #cc0000;"></span> <span style="color: #339933;">&lt;=</span> currentTime<span style="color: #339933;">&&</span>currentTime <span style="color: #339933;">&lt;</span> <span style="color: #cc0000;">5</span><span style="color: #009900;">)</span> <span style="color: #009900;">{</span></span> <span style="vertical-align: top;">       document.<span style="color: #000066; font-weight: bold;">write</span><span style="color: #009900;">(</span><span style="color: #3366cc;">"&lt;link rel='stylesheet' href='night.css' type='text/css'&gt;"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span></span> <span style="vertical-align: top;">      <span style="color: #009900;">}</span></span> <span style="vertical-align: top;">      <span style="color: #000066; font-weight: bold;">if</span> <span style="color: #009900;">(</span><span style="color: #cc0000;">5</span> <span style="color: #339933;">&lt;=</span> currentTime<span style="color: #339933;">&&</span>currentTime <span style="color: #339933;">&lt;</span> <span style="color: #cc0000;">11</span><span style="color: #009900;">)</span> <span style="color: #009900;">{</span></span> <span style="vertical-align: top;">       document.<span style="color: #000066; font-weight: bold;">write</span><span style="color: #009900;">(</span><span style="color: #3366cc;">"&lt;link rel='stylesheet' href='morning.css' type='text/css'&gt;"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span></span> <span style="vertical-align: top;">      <span style="color: #009900;">}</span></span> <span style="vertical-align: top;">      <span style="color: #000066; font-weight: bold;">if</span> <span style="color: #009900;">(</span><span style="color: #cc0000;">11</span> <span style="color: #339933;">&lt;=</span> currentTime<span style="color: #339933;">&&</span>currentTime <span style="color: #339933;">&lt;</span> <span style="color: #cc0000;">16</span><span style="color: #009900;">)</span> <span style="color: #009900;">{</span></span> <span style="vertical-align: top;">       document.<span style="color: #000066; font-weight: bold;">write</span><span style="color: #009900;">(</span><span style="color: #3366cc;">"&lt;link rel='stylesheet' href='day.css' type='text/css'&gt;"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span></span> <span style="vertical-align: top;">      <span style="color: #009900;">}</span></span> <span style="vertical-align: top;">      <span style="color: #000066; font-weight: bold;">if</span> <span style="color: #009900;">(</span><span style="color: #cc0000;">16</span> <span style="color: #339933;">&lt;=</span> currentTime<span style="color: #339933;">&&</span>currentTime <span style="color: #339933;">&lt;</span> <span style="color: #cc0000;">22</span><span style="color: #009900;">)</span> <span style="color: #009900;">{</span></span> <span style="vertical-align: top;">       document.<span style="color: #000066; font-weight: bold;">write</span><span style="color: #009900;">(</span><span style="color: #3366cc;">"&lt;link rel='stylesheet' href='evening.css' type='text/css'&gt;"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span></span> <span style="vertical-align: top;">      <span style="color: #009900;">}</span></span> <span style="vertical-align: top;">      <span style="color: #000066; font-weight: bold;">if</span> <span style="color: #009900;">(</span><span style="color: #cc0000;">22</span> <span style="color: #339933;">&lt;=</span> currentTime<span style="color: #339933;">&&</span>currentTime <span style="color: #339933;">&lt;=</span> <span style="color: #cc0000;">24</span><span style="color: #009900;">)</span> <span style="color: #009900;">{</span></span> <span style="vertical-align: top;">       document.<span style="color: #000066; font-weight: bold;">write</span><span style="color: #009900;">(</span><span style="color: #3366cc;">"&lt;link rel='stylesheet' href='night.css' type='text/css'&gt;"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span></span> <span style="vertical-align: top;">      <span style="color: #009900;">}</span></span> <span style="vertical-align: top;"><span style="color: #009900;">}</span></span> <span style="vertical-align: top;">&nbsp;</span> <span style="vertical-align: top;">getStylesheet<span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span></span> <span style="vertical-align: top;"><span style="color: #339933;">--&gt;</span></span> <span style="vertical-align: top;"><span style="color: #339933;">&lt;/</span>script<span style="color: #339933;">&gt;</span></span> <span style="vertical-align: top;">&nbsp;</span> <span style="vertical-align: top;"><span style="color: #339933;">&lt;</span>noscript<span style="color: #339933;">&gt;&lt;</span>link href<span style="color: #339933;">=</span><span style="color: #3366cc;">"main.css"</span> rel<span style="color: #339933;">=</span><span style="color: #3366cc;">"stylesheet"</span> type<span style="color: #339933;">=</span><span style="color: #3366cc;">"text/css"</span><span style="color: #339933;">&gt;&lt;/</span>noscript<span style="color: #339933;">&gt;</span></span></pre>
    </td>
  </tr>
</table>

 

### Explications:

&nbsp;&#8211; La variable **currentTime**, comme son nom l&rsquo;indique, récupère l&rsquo;heure (H) courant. Par la suite des tests sont fait pour savoir quelle heure il fait ou du moins dans quel intervalle d&rsquo;heures on est. Une feuille de style est chargée en fonction de ça.

&nbsp;&#8211; La fonction Javascript **write** permet simplement de renvoyer la contenu quelle possède en paramètre&#8230;Une peu comme la fonction **echo** en PHP ou encore la méthode **println** en Java. Dans notre cas, la fonction renvoi simplement la feuille de style. Veillez donc à créer les différents fichiers CSS

**night.css, morning.css, day.css**,&nbsp; **evening.css** et .

 

<p style="text-align: left;">
  Source : <a title="Voir le site..." href="http://css-tricks.com/snippets/javascript/different-stylesheet-pending-the-time-of-day/">css-tricks.com</a>
</p>