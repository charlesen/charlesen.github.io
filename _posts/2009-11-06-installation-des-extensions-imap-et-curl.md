---
id: 12
title: Installation des extensions IMAP et CURL
date: 2009-11-06T10:07:32+01:00
author: charlesen
layout: post
guid: https://charlesen.fr/?p=12
permalink: /installation-des-extensions-imap-et-curl/
categories:
  - tutoriel
tags:
  - curl
  - dédié
  - imap
  - installation extensions
  - serveur mutualisé
  - serveur ovh
---
<div>
  <span style="font-family: book antiqua,palatino;"><span style="font-size: 12pt;">Un petit tuto pour vous expliquer rapidement comment installer les extensions curl et Imap sur votre serveur</span></span>
</div>

<span style="font-family: book antiqua,palatino;"></p> 

<p>
  </span>
</p>

<div>
  <span style="font-family: book antiqua,palatino;"><span style="font-size: 12pt;">La librairie cURL permet de communiquer facilement avec de nombreux types de serveurs applicatifs comme FTP, FTPS, HTTP, HTTPS, SCP, SFTP, TFTP, TELNET, DICT, LDAP, LDAPS et FILE. L&rsquo;extension cURL permet d&rsquo;interagir en PHP avec tous ces protocoles de facon presque transparente.</span></span>
</div>

<div>
  <span style="font-family: book antiqua,palatino;"><span style="font-size: 12pt;">Nous allons étudier différents 2 d&rsquo;installation sur un serveur de type dédié.</span></span>
</div>

<div>
  <span style="font-family: book antiqua,palatino;"><span style="font-size: 10pt;"> </span></span>
</div>

<p>
  <span style="font-family: book antiqua,palatino;" /> <!--more--></span>
</p>

<h1>
  <span style="font-family: book antiqua,palatino;"><span style="font-size: 14pt;">Installation 1 : re-compilation de php</span></span>
</h1>

<p>
  <span style="font-family: book antiqua,palatino;"><br /></span>
</p>

<div>
  <span style="font-family: book antiqua,palatino;"><span style="font-size: 12pt;">Les sources de l&rsquo;extension curl sont inclues à php, donc pas besoin de te les télécharger</span></span>
</div>

<div>
  <span style="font-family: book antiqua,palatino;"><span style="font-size: 12pt;"><br /></span></span>
</div>

<div>
  <pre><p>
  <span style="font-size: 12pt;"><span style="font-family: book antiqua,palatino;"><strong><span style="color: #000000;">#./configure --prefix=/votre/repertoire/php --with-curl<code id="contenuCoded0e184">&lt;br /></code>#make<code id="contenuCoded0e184">&lt;br />#make install</code></span></strong></span></span>
</p>

<span style="font-family: book antiqua,palatino;"><br /><br /></span></pre></p>
</div>

<h1>
  <span style="font-family: book antiqua,palatino;"><span style="font-size: 14pt;">Installation 2 : aptititude, apt-get</span><strong><span style="font-size: 14pt;"><br /></span></strong></span>
</h1>

<div>
  <span style="font-family: book antiqua,palatino;"><strong><span style="font-size: 14pt;"><br /></span></strong></span>
</div>

<div>
  <span style="font-family: book antiqua,palatino;"><span style="font-size: 12pt;">Cette installation est beaucoup plus souple. Il faut simplement utiliser les commandes <a target="_blank" title="Man APT-GET" href="http://www.google.fr/url?sa=t&#038;source=web&#038;ct=res&#038;cd=1&#038;ved=0CAcQFjAA&#038;url=http%3A%2F%2Fpwet.fr%2Fman%2Flinux%2Fadministration_systeme%2Fapt_get&#038;ei=DAn0Sq7FCNaL4gbavqjgAw&#038;usg=AFQjCNGnS_sudMNzRBbPSK2wpGBFTNfyDQ&#038;sig2=HfghYKnHmSIWq83RHOj6Rw">apt-get</a> ou <a target="_blank" title="Man aptitude" href="http://doc.ubuntu-fr.org/aptitude">aptitude</a>.</span></span>
</div>

<div>
  <span style="font-family: book antiqua,palatino;"><span style="font-size: 12pt;"><br /></span></span>
</div>

<div>
  <span style="font-family: book antiqua,palatino;"><span style="font-size: 12pt;">La première chose à faire est de vérifier la présence et surtout l&rsquo;état des paquets :</span></span>
</div>

<div>
  <span style="font-family: book antiqua,palatino;"><strong><span style="color: #000000;"><span style="font-size: 12pt;">#aptitude search curl | grep php</span></span></strong></span>
</div>

<div>
  <div>
    <span style="font-family: book antiqua,palatino;"><strong><span style="color: #000000;"><span style="font-size: 12pt;">#aptitude search imap | grep php </span></span></strong></span>
  </div>
  
  <div>
    <span style="font-family: book antiqua,palatino;"><strong><span style="color: #000000;"><span style="font-size: 12pt;"><br /></span></span></strong></span>
  </div></p>
</div>

<div>
  <span style="font-family: book antiqua,palatino;"><span style="font-size: 12pt;"> Le premier caractère de chaque ligne indique l&rsquo;état courant du paquet : p (non présent dans le système), i(installé), c (paquet supprimé du système), v(paquet virtuel) </span></span>
</div>

<div>
  <span style="font-family: book antiqua,palatino;"><span style="font-size: 12pt;">Si vos lignes indiquent <strong>p</strong>, alors vous avez le droit de continuer la lecture de ce billet 🙂</span></span>
</div>

<div>
  <span style="font-family: book antiqua,palatino;"><span style="font-size: 12pt;">Il faut ensuite mettre à jour les paquets (liens de téléchargements,&#8230;)</span></span>
</div>

<div>
  <span style="font-family: book antiqua,palatino;"><span style="font-size: 12pt;"><br /></span></span>
</div>

<div>
  <span style="font-family: book antiqua,palatino;"><strong><span style="font-size: 12pt;">#apt-get update</span></strong></span>
</div>

<div>
  <span style="font-family: book antiqua,palatino;"><span style="font-size: 12pt;">et enfin les installer :</span></span>
</div>

<div>
  <span style="font-family: book antiqua,palatino;"><span style="font-size: 12pt;"><strong>#apt-get install php5-curl php5-imap</strong><br /></span></span>
</div>

<div>
  <span style="font-family: book antiqua,palatino;"><span style="font-size: 12pt;">Ne pas oubliez de redémarrer le serveur apache</span></span>
</div>

<div>
  <span style="font-family: book antiqua,palatino;"><span style="font-size: 12pt;"><br /></span></span>
</div>

<div>
  <span style="font-family: book antiqua,palatino;"><span style="font-size: 12pt;"><strong>#/etc/init.d/php5/apache2 restart</strong>(il se peut que ce chemin soit différent chez vous &#8212; vérifiez votre configuration)</span></span>
</div>

<div>
  <span style="font-family: book antiqua,palatino;"><span style="font-size: 12pt;">Vérifiez que les extensions sont bien présentes, soit depuis votre manager en regarder les informations de php, soit en créant un fichier <em>info.php</em> </span></span>
</div>

<div>
  <span style="font-family: book antiqua,palatino;"><span style="font-size: 12pt;"><span style="color: #993300;"><strong> </strong></span><br /></span></span>
</div>

<div>
  <span style="font-family: book antiqua,palatino;"><span style="font-size: 12pt;"><span style="color: #800000;"> </span></span></span>
</div>

<div>
</div>

<div>
  <span style="font-family: book antiqua,palatino;"><span style="font-size: 12pt;">Voilà, c&rsquo;est aussi simple que ça 🙂</span></span>
</div>