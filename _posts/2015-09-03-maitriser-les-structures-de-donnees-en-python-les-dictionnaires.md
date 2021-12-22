---
id: 267
title: 'Maîtriser les structures de données en Python : les dictionnaires'
date: 2015-09-03T23:11:33+02:00
author: charlesen
layout: post
guid: https://charlesen.fr/?p=267
permalink: /maitriser-les-structures-de-donnees-en-python-les-dictionnaires/
categories:
  - tutoriel
tags:
  - array
  - dictionary
  - dictionnaire
  - données
  - hash
  - Python
  - stucture
  - tableau
---
Une des clés pour maîtriser le langage Python est la bonne compréhension de ses structures de données. Dans ce article je vous propose d&rsquo;étudier les dictionnaires.

Un dictonnaire en python (dict) s&rsquo;écrit à l&rsquo;aide d&rsquo;un couple _**clé->valeur**_, avec clé qui peut être de n&rsquo;importe quel type hashable (qui contient les méthodes **\_\_eq\_\_()** et **\_\_hash\_\_()**). la _**valeur**_ peut être de n&rsquo;importe quel type.

L&rsquo;intérêt des dictionnaires est clairement la rapidité d&rsquo;examen de grosse liste de données. Il est possible de vérifier l&rsquo;existence d&rsquo;une clé sans avoir besoin d&rsquo;examiner toutes les données. Toute la différence avec les tableaux qui utilise la notion d&rsquo;index.

<!--more-->

### <span style="font-size: 1.17em;">Comment créer un dictionnaire</span>

Pour créer un nouveau dictionnaire, il suffit de taper l&rsquo;instruction suivante :

<pre class="code" style="padding: 9.5px; margin: 20px 0px; font-size: 13px; line-height: 1.42857143; color: #333333; border: none; overflow: auto; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; background: #efefef;"><span class="o" style="color: #666666;">&gt;&gt;&gt;</span> <span class="n">a</span> <span class="o" style="color: #666666;">=</span> <span class="p">{}</span> </pre>

<span class="p">&nbsp;On peut ensuite y insérer des données :</span>

<pre class="code" style="padding: 9.5px; margin: 20px 0px; font-size: 13px; line-height: 1.42857143; color: #333333; border: none; overflow: auto; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; background: #efefef;"><span class="o" style="color: #666666;"></span><span class="o" style="color: #666666;">&gt;&gt;&gt;</span> <span class="n">a</span><span class="p">[</span><span class="s" style="color: #0000e6;">"nom"</span><span class="p">]</span> <span class="o" style="color: #666666;">=</span> <span class="s" style="color: #0000e6;">"edounze"</span><span class="o" style="color: #666666;">&gt;&gt;&gt;</span> <span class="n">a</span><span class="p">[</span><span class="s" style="color: #0000e6;">"prenom"</span><span class="p">]</span> <span class="o" style="color: #666666;">=</span> <span class="s" style="color: #0000e6;">"charles"</span><span class="o" style="color: #666666;">&gt;&gt;&gt;</span> <span class="n">a</span><span class="p">{</span><span class="s" style="color: #0000e6;">'nom'</span><span class="p">:</span> <span class="s" style="color: #0000e6;">'edounze'</span><span class="p">,</span> <span class="s" style="color: #0000e6;">'prenom'</span><span class="p">:</span> <span class="s" style="color: #0000e6;">'charles'</span><span class="p">}</span> </pre>

<span class="p">&nbsp;On peut également faire d&rsquo;une pierre deux coups (construction + ajout de données)</span>

<pre class="code" style="color: #333333; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; font-size: 13px; margin: 20px 0px; padding: 9.5px; line-height: 1.42857143; border: none; overflow: auto; background: #efefef;"><span class="o" style="color: #666666;">&gt;&gt;&gt;</span> <span class="n">a = </span><span class="p">{</span><span class="s" style="color: #0000e6;">'nom'</span><span class="p">:</span> <span class="s" style="color: #0000e6;">'edounze'</span><span class="p">,</span> <span class="s" style="color: #0000e6;">'prenom'</span><span class="p">:</span> <span class="s" style="color: #0000e6;">'charles'</span><span class="p">}</span> </pre>

### Récupération des données

La récupération des données se faire à l&rsquo;aide de la méthode interne _**get**_. Il est possible de préciser une valeur de sortie par défaut, dans le cas ou la clé serait vide.&nbsp;

<pre class="code" style="padding: 9.5px; margin: 20px 0px; font-size: 13px; line-height: 1.42857143; color: #333333; border: none; overflow: auto; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; background: #efefef;"><span class="o" style="color: #666666;">&gt;&gt;&gt;</span> <span class="n">data</span> <span class="o" style="color: #666666;">=</span> <span class="p">{</span><span class="s" style="color: #0000e6;">"name"</span><span class="p">:</span> <span class="s" style="color: #0000e6;">"charles"</span><span class="p">,</span> <span class="s" style="color: #0000e6;">"age"</span><span class="p">:</span> <span class="mi" style="color: #008c00;">27</span><span class="p">}</span><span class="o" style="color: #666666;">&gt;&gt;&gt;</span> <span class="n">data</span><span class="o" style="color: #666666;">.</span><span class="n">get</span><span class="p">(</span><span class="s" style="color: #0000e6;">"name"</span><span class="p">)</span><span class="s" style="color: #0000e6;">'charles'</span><span class="o" style="color: #666666;">&gt;&gt;&gt;</span> <span class="n">data</span><span class="o" style="color: #666666;">.</span><span class="n">get</span><span class="p">(</span><span class="s" style="color: #0000e6;">"adresse"</span><span class="p">,</span> <span class="s" style="color: #0000e6;">"Adresse inconnue"</span><span class="p">)</span><span class="s" style="color: #0000e6;">'Adresse inconnue'</span></pre>

Pour vérifier la présence ou l&rsquo;absence d&rsquo;une clé, il suffit d&rsquo;utiliser la méthode _**has_key**_ qui renvoie un booléen :

<pre class="code" style="padding: 9.5px; margin: 20px 0px; font-size: 13px; line-height: 1.42857143; color: #333333; border: none; overflow: auto; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; background: #efefef;"><span class="o" style="color: #666666;">&gt;&gt;&gt;</span> <span class="n">a</span><span class="o" style="color: #666666;">.</span><span class="n">has_key</span><span class="p">(</span><span class="s" style="color: #0000e6;">"name"</span><span class="p">)</span><span class="bp" style="color: #e34adc;">True</span></pre>

&nbsp;La suppresion d&rsquo;une clé se faire à l&rsquo;aide de l&rsquo;instruction&nbsp;_**del**_ :

<pre class="code" style="padding: 9.5px; margin: 20px 0px; font-size: 13px; line-height: 1.42857143; color: #333333; border: none; overflow: auto; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; background: #efefef;"><span class="o" style="color: #666666;">&gt;&gt;&gt;</span> <span class="k" style="color: #800000; font-weight: bold;">del</span> <span class="n">a</span><span class="p">[</span><span class="s" style="color: #0000e6;">"name"</span><span class="p">]</span><span class="o" style="color: #666666;">&gt;&gt;&gt;</span> <span class="n">a</span><span class="p">{</span><span class="s" style="color: #0000e6;">'prenom'</span><span class="p">:</span> <span class="s" style="color: #0000e6;">'charles'</span><span class="p">}</span></pre>

### Manipulation des données

Pour afficher les données d&rsquo;un dictionnaire, on peut utiliser différentes boucles, comme la boucle For :

<pre class="code" style="padding: 9.5px; margin: 20px 0px; font-size: 13px; line-height: 1.42857143; color: #333333; border: none; overflow: auto; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; background: #efefef;"><span class="o" style="color: #666666;">&gt;&gt;&gt;</span> <span class="n">fiche</span> <span class="o" style="color: #666666;">=</span> <span class="p">{</span><span class="s" style="color: #0000e6;">"name"</span><span class="p">:</span><span class="s" style="color: #0000e6;">"edounze"</span><span class="p">,</span><span class="s" style="color: #0000e6;">"prenom"</span><span class="p">:</span><span class="s" style="color: #0000e6;">"charles"</span><span class="p">}</span><span class="o" style="color: #666666;">&gt;&gt;&gt;</span> <span class="k" style="color: #800000; font-weight: bold;">for</span> cle,<span class="n">valeur</span> <span class="ow" style="color: #007020; font-weight: bold;">in</span> <span class="n">fiche</span><span class="o" style="color: #666666;">.</span><span class="n">items</span><span class="p">():</span><span class="o" style="color: #666666;">...</span>     <span class="k" style="color: #800000; font-weight: bold;">print</span> cle, <span class="n">valeur</span><span class="o" style="color: #666666;">...</span> <span class="n">nom edounze</span><span class="n">prenom charles</span></pre>

### Méthodes intéressantes et usages

<h3 style="font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif; font-weight: 500; line-height: 1.1; color: #333333; margin-top: 20px; margin-bottom: 10px; font-size: 24px;">
  <code style="font-size: 21.6000003814697px; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; padding: 2px 4px; color: #c7254e; background-color: #f9f2f4;">a.clear()</code>
</h3>

Supprime toutes les entrées du dictionnaires **a**.

<h3 style="font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif; font-weight: 500; line-height: 1.1; color: #333333; margin-top: 20px; margin-bottom: 10px; font-size: 24px;">
  <code style="font-size: 21.6000003814697px; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; padding: 2px 4px; color: #c7254e; background-color: #f9f2f4;">a.copy()</code>
</h3>

Fais une copie du dictionnaire. Une modification du dictionnaire original n&rsquo;aura pas d&rsquo;impact sur la copie

<div class="codehilite" style="color: #333333; font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif; font-size: 14px; line-height: 20px; background: #f8f8f8;">
  <pre style="overflow: auto; font-size: 13px; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; padding: 9.5px; margin: 0px 0px 10px; line-height: 1.42857143; color: #333333; border: 1px solid #cccccc; background-color: #f5f5f5;">a <span class="o" style="color: #666666;">=</span> <span class="p">{</span><span class="mi" style="color: #666666;">1</span><span class="o" style="color: #666666;">:</span> <span class="sc" style="color: #ba2121;">'a'</span><span class="p">,</span> <span class="mi" style="color: #666666;">2</span><span class="o" style="color: #666666;">:</span> <span class="sc" style="color: #ba2121;">'b'</span><span class="p">,</span> <span class="mi" style="color: #666666;">3</span><span class="o" style="color: #666666;">:</span> <span class="sc" style="color: #ba2121;">'c'</span><span class="p">}</span><span class="n">copie_dict</span> <span class="o" style="color: #666666;">=</span> a<span class="p">.</span><span class="n">copy</span><span class="p">()</span><span class="n">copie_dict</span> <span class="err" style="border: 1px solid #ff0000;">#</span> <span class="p">{</span><span class="mi" style="color: #666666;">1</span><span class="o" style="color: #666666;">:</span> <span class="sc" style="color: #ba2121;">'a'</span><span class="p">,</span> <span class="mi" style="color: #666666;">2</span><span class="o" style="color: #666666;">:</span> <span class="sc" style="color: #ba2121;">'b'</span><span class="p">,</span> <span class="mi" style="color: #666666;">3</span><span class="o" style="color: #666666;">:</span> <span class="sc" style="color: #ba2121;">'c'</span><span class="p">}</span><span class="p">a[</span><span class="mi" style="color: #666666;">1</span><span class="p">]</span> <span class="o" style="color: #666666;">=</span> <span class="sc" style="color: #ba2121;">'z'</span><span class="n">copie_dict</span> <span class="err" style="border: 1px solid #ff0000;">#</span> <span class="p">{</span><span class="mi" style="color: #666666;">1</span><span class="o" style="color: #666666;">:</span> <span class="sc" style="color: #ba2121;">'a'</span><span class="p">,</span> <span class="mi" style="color: #666666;">2</span><span class="o" style="color: #666666;">:</span> <span class="sc" style="color: #ba2121;">'b'</span><span class="p">,</span> <span class="mi" style="color: #666666;">3</span><span class="o" style="color: #666666;">:</span> <span class="sc" style="color: #ba2121;">'c'</span><span class="p">}</span></pre>
  
  <h3 style="font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif; font-weight: 500; line-height: 1.1; color: #333333; margin-top: 20px; margin-bottom: 10px; font-size: 24px;">
    <code style="font-size: 21.6000003814697px; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; padding: 2px 4px; color: #c7254e; background-color: #f9f2f4;">del a[d]</code>
  </h3></p>
</div>

Supprimer la valeur associé à la clé _**&lsquo;d&rsquo;**_.

&nbsp;

<h3 style="font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif; font-weight: 500; line-height: 1.1; color: #333333; margin-top: 20px; margin-bottom: 10px; font-size: 24px;">
  <code style="font-size: 21.6000003814697px; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; padding: 2px 4px; color: #c7254e; background-color: #f9f2f4;">dict.fromkeys(seq[, value])</code>
</h3>

Crée une copie du dictionnaire a avec des clés identiques. Si la variable _value_ (optionnelle) est précisée, ses valeurs seront ajouter au nouveau dictionnaire.

<div class="codehilite" style="color: #333333; font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif; font-size: 14px; line-height: 20px; background: #f8f8f8;">
  <pre style="overflow: auto; font-size: 13px; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; padding: 9.5px; margin: 0px 0px 10px; line-height: 1.42857143; color: #333333; border: 1px solid #cccccc; background-color: #f5f5f5;"><span class="n">my_list</span> <span class="o" style="color: #666666;">=</span> <span class="p">[</span><span class="mi" style="color: #666666;">1</span><span class="p">,</span> <span class="mi" style="color: #666666;">2</span><span class="p">,</span> <span class="mi" style="color: #666666;">3</span><span class="p">]</span><span class="n">my_dictionary</span> <span class="o" style="color: #666666;">=</span> <span class="n">dict</span><span class="p">.</span><span class="n">fromkeys</span><span class="p">(</span><span class="n">my_list</span><span class="p">,</span> <span class="mi" style="color: #666666;"></span><span class="p">)</span><span class="n">my_dictionary</span> <span class="err" style="border: 1px solid #ff0000;">#</span> <span class="p">{</span><span class="mi" style="color: #666666;">1</span><span class="o" style="color: #666666;">:</span> <span class="mi" style="color: #666666;"></span><span class="p">,</span> <span class="mi" style="color: #666666;">2</span><span class="o" style="color: #666666;">:</span> <span class="mi" style="color: #666666;"></span><span class="p">,</span> <span class="mi" style="color: #666666;">3</span><span class="o" style="color: #666666;">:</span> <span class="mi" style="color: #666666;"></span><span class="p">}</span></pre>
  
  <h3 style="font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif; font-weight: 500; line-height: 1.1; color: #333333; margin-top: 20px; margin-bottom: 10px; font-size: 24px;">
    <code style="font-size: 21.6000003814697px; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; padding: 2px 4px; color: #c7254e; background-color: #f9f2f4;">len(a)</code>
  </h3></p>
</div>

&nbsp;Renvoie la taille du dictionnaire **a**.

<div class="codehilite" style="color: #333333; font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif; font-size: 14px; line-height: 20px; background: #f8f8f8;">
  <pre style="overflow: auto; font-size: 13px; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; padding: 9.5px; margin: 0px 0px 10px; line-height: 1.42857143; color: #333333; border: 1px solid #cccccc; background-color: #f5f5f5;"><span class="n">print</span> <span class="err" style="border: 1px solid #ff0000;">'</span><span class="n">le dictionnaire</span> <span class="n">contient</span> <span class="p">{}</span> <span class="n">entrées</span><span class="err" style="border: 1px solid #ff0000;">'</span><span class="p">.</span><span class="n">format</span><span class="p">(</span><span class="n">len</span><span class="p">(</span><span class="n">a</span><span class="p">))</span> </pre></p>
</div>

<h3 style="font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif; font-weight: 500; line-height: 1.1; color: #333333; margin-top: 20px; margin-bottom: 10px; font-size: 24px;">
  <code style="font-size: 21.6000003814697px; font-family: Menlo, Monaco, Consolas, 'Courier New', monospace; padding: 2px 4px; color: #c7254e; background-color: #f9f2f4;">k not in d</code>
</h3>

&nbsp;Permet de tester la non-existence d&rsquo;une valeur