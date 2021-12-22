---
id: 328
title: Meilleure façon de compter des occurences en Python
date: 2015-11-21T08:44:57+01:00
author: charlesen
layout: post
guid: https://charlesen.fr/?p=328
permalink: /meilleure-facon-de-compter-des-occurences-en-python/
categories:
  - tutoriel
tags:
  - count
  - denombrer
  - dictionnaire
  - except
  - list
  - Python
  - try
---
Ce qui est en développement informatique, c&rsquo;est que pour un problème donné à résoudre, il existe des dizaines, centaines, voir milliers de résolutions possibles. Le gros du travail revient en général à produire qui soit le plus optimisé possible.

Compter en Python n&rsquo;est en soi pas un gros problème&#8230;A condition de le faire proprement. Je vous propose deux possibilités, en partant de la liste d&rsquo;élements suivante :

<span class="n" style="margin: 0px; padding: 0px; border: 0px; line-height: 18.85px; font-family: Menlo, Monaco, 'Andale Mono', 'lucida console', 'Courier New', monospace; font-size: 13px; vertical-align: baseline; white-space: pre; background-color: #fdf6e3;">colors</span><span class="o" style="margin: 0px; padding: 0px; border: 0px; line-height: 18.85px; font-family: Menlo, Monaco, 'Andale Mono', 'lucida console', 'Courier New', monospace; font-size: 13px; vertical-align: baseline; color: #586e75; white-space: pre; background-color: #fdf6e3;">=</span><span class="p" style="margin: 0px; padding: 0px; border: 0px; line-height: 18.85px; font-family: Menlo, Monaco, 'Andale Mono', 'lucida console', 'Courier New', monospace; font-size: 13px; vertical-align: baseline; color: #586e75; white-space: pre; background-color: #fdf6e3;">[</span><span class="s" style="margin: 0px; padding: 0px; border: 0px; line-height: 18.85px; font-family: Menlo, Monaco, 'Andale Mono', 'lucida console', 'Courier New', monospace; font-size: 13px; vertical-align: baseline; white-space: pre; background-color: #fdf6e3;">« brown »</span><span class="p" style="margin: 0px; padding: 0px; border: 0px; line-height: 18.85px; font-family: Menlo, Monaco, 'Andale Mono', 'lucida console', 'Courier New', monospace; font-size: 13px; vertical-align: baseline; color: #586e75; white-space: pre; background-color: #fdf6e3;">,</span><span class="s" style="margin: 0px; padding: 0px; border: 0px; line-height: 18.85px; font-family: Menlo, Monaco, 'Andale Mono', 'lucida console', 'Courier New', monospace; font-size: 13px; vertical-align: baseline; white-space: pre; background-color: #fdf6e3;">« red »</span><span class="p" style="margin: 0px; padding: 0px; border: 0px; line-height: 18.85px; font-family: Menlo, Monaco, 'Andale Mono', 'lucida console', 'Courier New', monospace; font-size: 13px; vertical-align: baseline; color: #586e75; white-space: pre; background-color: #fdf6e3;">,</span><span class="s" style="margin: 0px; padding: 0px; border: 0px; line-height: 18.85px; font-family: Menlo, Monaco, 'Andale Mono', 'lucida console', 'Courier New', monospace; font-size: 13px; vertical-align: baseline; white-space: pre; background-color: #fdf6e3;">« green »</span><span class="p" style="margin: 0px; padding: 0px; border: 0px; line-height: 18.85px; font-family: Menlo, Monaco, 'Andale Mono', 'lucida console', 'Courier New', monospace; font-size: 13px; vertical-align: baseline; color: #586e75; white-space: pre; background-color: #fdf6e3;">,</span><span class="s" style="margin: 0px; padding: 0px; border: 0px; line-height: 18.85px; font-family: Menlo, Monaco, 'Andale Mono', 'lucida console', 'Courier New', monospace; font-size: 13px; vertical-align: baseline; white-space: pre; background-color: #fdf6e3;">« yellow »</span><span class="p" style="margin: 0px; padding: 0px; border: 0px; line-height: 18.85px; font-family: Menlo, Monaco, 'Andale Mono', 'lucida console', 'Courier New', monospace; font-size: 13px; vertical-align: baseline; color: #586e75; white-space: pre; background-color: #fdf6e3;">,</span><span class="s" style="margin: 0px; padding: 0px; border: 0px; line-height: 18.85px; font-family: Menlo, Monaco, 'Andale Mono', 'lucida console', 'Courier New', monospace; font-size: 13px; vertical-align: baseline; white-space: pre; background-color: #fdf6e3;">« yellow »</span><span class="p" style="margin: 0px; padding: 0px; border: 0px; line-height: 18.85px; font-family: Menlo, Monaco, 'Andale Mono', 'lucida console', 'Courier New', monospace; font-size: 13px; vertical-align: baseline; color: #586e75; white-space: pre; background-color: #fdf6e3;">,</span><span class="s" style="margin: 0px; padding: 0px; border: 0px; line-height: 18.85px; font-family: Menlo, Monaco, 'Andale Mono', 'lucida console', 'Courier New', monospace; font-size: 13px; vertical-align: baseline; white-space: pre; background-color: #fdf6e3;">« brown »</span><span class="p" style="margin: 0px; padding: 0px; border: 0px; line-height: 18.85px; font-family: Menlo, Monaco, 'Andale Mono', 'lucida console', 'Courier New', monospace; font-size: 13px; vertical-align: baseline; color: #586e75; white-space: pre; background-color: #fdf6e3;">,</span><span class="s" style="margin: 0px; padding: 0px; border: 0px; line-height: 18.85px; font-family: Menlo, Monaco, 'Andale Mono', 'lucida console', 'Courier New', monospace; font-size: 13px; vertical-align: baseline; white-space: pre; background-color: #fdf6e3;">« brown »</span><span class="p" style="margin: 0px; padding: 0px; border: 0px; line-height: 18.85px; font-family: Menlo, Monaco, 'Andale Mono', 'lucida console', 'Courier New', monospace; font-size: 13px; vertical-align: baseline; color: #586e75; white-space: pre; background-color: #fdf6e3;">,</span><span class="s" style="margin: 0px; padding: 0px; border: 0px; line-height: 18.85px; font-family: Menlo, Monaco, 'Andale Mono', 'lucida console', 'Courier New', monospace; font-size: 13px; vertical-align: baseline; white-space: pre; background-color: #fdf6e3;">« black »</span><span class="p" style="margin: 0px; padding: 0px; border: 0px; line-height: 18.85px; font-family: Menlo, Monaco, 'Andale Mono', 'lucida console', 'Courier New', monospace; font-size: 13px; vertical-align: baseline; color: #586e75; white-space: pre; background-color: #fdf6e3;">]</span>

Le but du jeux est de compter le nombre de fois que chaque élément apparait dans la liste, afin d&rsquo;obtenir le résultat suivant :

**>>> color_counts {&lsquo;brown&rsquo;: 3, &lsquo;yellow&rsquo;: 2, &lsquo;green&rsquo;: 1, &lsquo;black&rsquo;: 1, &lsquo;red&rsquo;: 1}**

### La méthode basique

C&rsquo;est celle à laquelle on aurait tous pensé immédiatement. On boucle sur la liste, et on incrémente un dictionnaire possédant l&rsquo;objet recherché pour clé :

<pre xml:lang="python" lines="true">[code]<br />colors = ["brown", "red", "green", "yellow", "yellow", "brown", "brown", "black"]<br />color_counts = {}<br />for c in colors:<br />    if color_counts.has_key(c):<br />         color_counts[c] = color_counts[c] + 1<br />    else:<br />         color_counts[c] = 1<br />[/code]</pre>

### La méthode efficace

&nbsp;On utilise cette fois un bloque Try afin de compter si cela est possible (fonction de la variable&nbsp;**color_counts(c)**&nbsp;), sinon on lève une exception ou l&rsquo;on initialise la variable à 1

<pre xml:lang="python" lines="false">[code]<br />colors = ["brown", "red", "green", "yellow", "yellow", "brown", "brown", "black"]<br />color_counts = {}<br />for c in colors:<br />    try:<br />        color_counts[c] = color_counts[c] + 1<br />    except KeyError: <br />        color_counts[c] = 1<br />[/code]</pre>

&nbsp;

Mais on peut faire encore plus efficace en utilisant la méthode&nbsp;_**get**_&nbsp;présente dans les dictionnaires :

<pre xml:lang="css" lines="true">[code]<br />colors = ["brown", "red", "green", "yellow", "yellow", "brown", "brown", "black"]<br />color_counts = {}<br />for c in colors:<br />    color_counts[c] = color_counts.get(c, 0) + 1<br />[/code]</pre>

&nbsp;

<p style="text-align: center;">
  <strong>Je suis sur et certain qu&rsquo;il en existe encore d&rsquo;autres, certainement plus efficace&#8230;Si vous en trouvez n&rsquo;hésitez pas à commenter cet article</strong>
</p>