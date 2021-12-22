---
id: 66
title: Site de Gestion des stages étudiants
date: 2010-11-27T12:35:11+01:00
author: charlesen
layout: post
guid: https://charlesen.fr/?p=66
permalink: /site-de-gestion-des-stages-etudiants/
image: /wp-content/uploads/2010/11/images_blog_projets_LO09_java.png
categories:
  - Projets scolaires
tags:
  - développement java ee
  - EJB 3.0
  - Facelets
  - ingénieur utt
  - jquery
  - JSF
  - JSP
  - "projet de fin d'études ingénieur"
  - Servlets
  - Struts
  - XHTML/CSS
---
<span style="font-size: 12pt; font-family: book antiqua,palatino;"><img loading="lazy" class=" alignleft size-full wp-image-61" style="float: left;" title="Logo Java" src="https://charlesen.fr/wp-content/uploads/2010/11/images_blog_projets_LO09_java.png" alt="Logo Java" width="200" height="372" srcset="https://charlesen.fr/wp-content/uploads/2010/11/images_blog_projets_LO09_java.png 200w, https://charlesen.fr/wp-content/uploads/2010/11/images_blog_projets_LO09_java-161x300.png 161w" sizes="(max-width: 200px) 100vw, 200px" />Dans le cadre d&rsquo;une UV (Unité de Valeur) à l&rsquo;<a title="Site de l'Université de Technologie de Troyes" href="http://www.utt.fr/">Université de Technologie de Troyes,</a> j&rsquo;ai été amené à concevoir, puis à développer un site de gestion des stages, basé sur Java EE. Les technologies qui ont été mises en oeuvre sont précisement : <strong>JSF, Servlets, Managed Beans, EJB&nbsp; 3.0, XHTML/CSS, JQuery</strong></span>

<ul style="font-size: 12pt; font-family: book antiqua,palatino; text-align: justify;">
</ul>

<p style="text-align: justify;">
   
</p>

<p style="text-align: justify;">
  <span style="font-size: 12pt; font-family: book antiqua,palatino;">Ce projet a suivi toutes les phases de dévelopement habituelles, hormis l&rsquo;analyse qui a déja été faite. Ce qui donne :&nbsp; <strong>Conception, développement, tests & mise en production.</strong></span>
</p>



<p style="text-align: justify;">
  <span style="font-size: 12pt; font-family: book antiqua,palatino;">Le modèle de programmation utilisé est bien sûr MVC<strong>.</strong></span>
</p>

<ul style="text-align: justify;">
  <li>
    <span style="font-size: 12pt; font-family: book antiqua,palatino;">La vue est géré par <em><strong>JSF</strong></em></span>
  </li>
  <li>
    <span style="font-size: 12pt; font-family: book antiqua,palatino;">Le contrôle grâce à des <strong><em>Managed Beans</em></strong></span>
  </li>
  <li>
    <span style="font-size: 12pt; font-family: book antiqua,palatino;">Le modèle est pris en charge par <strong>EJB</strong></span>
  </li>
</ul>

<ul style="text-align: justify;">
</ul>

 <span style="font-size: 12pt; font-family: book antiqua,palatino;"></span> 

<p style="text-align: justify;">
  <span style="font-size: 12pt; font-family: book antiqua,palatino;">Ce projet avait pour objet la mise en place d&rsquo;un outil commun de suivi des stages des étudiants de l&rsquo;Université de Technologie de Troyes (UTT). </span>
</p>

<!--more-->

<p style="text-align: justify;">
  <span style="font-size: 12pt; font-family: book antiqua,palatino;">Il existe 2 types de stages en cycle ingénieur à l&rsquo;UTT : les stages TN09 et TN10. Ne me demandez d&rsquo;où viennent ces codes, je ne saurai pas vous répondre :).</span>
</p>

<p style="text-align: justify;">
  <span style="font-size: 12pt; font-family: book antiqua,palatino;">Dans le domaine informatique, l&rsquo;UTT propose deux choix de formation : </span>
</p>

<ul style="text-align: justify;">
  <li>
    <span style="font-size: 12pt; font-family: book antiqua,palatino;"><strong>ISI <span style="color: #333399;">(<span style="color: #993300;"><em>Informatique et Systèmes d&rsquo;Information</em></span>)</span></strong></span>
  </li>
  <li>
    <span style="font-size: 12pt; font-family: book antiqua,palatino;"><strong>SRT <span style="color: #333399;">(<span style="color: #993300;"><em> Systèmes, Réseaux et Télécommunications</em></span>) </span></strong><br /></span>
  </li>
</ul>

<p style="text-align: justify;">
   
</p>

<p style="text-align: justify;">
  <span style="font-size: 12pt; font-family: book antiqua,palatino;">Chaque programme propose des filières de spécialisation :</span>
</p>

<ul style="text-align: justify;">
  <li>
    <span style="font-size: 12pt; font-family: book antiqua,palatino;"><strong>SRT &#8211;> <span style="color: #993300;">Intégration de Réseaux</span></strong>(IR), <span style="color: #800000;"><strong>Technologies Mobiles et Systèmes embarqués</strong></span> (TMSE), <span style="color: #993300;"><strong>Sécurité des Systèmes et des Réseaux</strong></span>(SSR)</span>
  </li>
</ul>

<ul style="text-align: justify;">
  <li>
    <span style="font-size: 12pt; font-family: book antiqua,palatino;"><strong>ISI &#8211;> <span style="color: #993300;">Management des Systèmes d&rsquo;Information</span></strong> (MSI), <span style="color: #993300;"><strong>Management de Projets Logiciels</strong></span> (MPL), <span style="color: #993300;"><strong>Management du Risque Informationnel</strong></span> (MRI)</span>
  </li>
</ul>

<p style="text-align: justify;">
   
</p>

<p style="text-align: justify;">
  <span style="font-size: 12pt; font-family: book antiqua,palatino;">Notre application devait donc au final assurer le suivi commun des stages par différents types d&rsquo;acteurs : Responsables de Programmes, Responsables des Stages, Responsable du Service Relations Entreprises Etudiants (REE). On peut aussi citer comme acteurs (passifs) : les Enseignants suiveurs de stage (tuteurs) et les étudiants.<br /></span>
</p>

<ul style="font-family: book antiqua,palatino; font-size: 12pt; text-align: justify;">
  <li>
    <span style="font-size: 12pt; font-family: book antiqua,palatino;"><strong> F1 </strong>: gestion des enseignants-chercheurs suiveurs UTT par l&rsquo;un des trois responsables de programme d&rsquo;enseignement </span>
  </li>
  <li>
    <span style="font-size: 12pt; font-family: book antiqua,palatino;"><strong> F2</strong> : gestion des étudiants par l&rsquo;un des trois responsables de programme d&rsquo;enseignement </span>
  </li>
  <li>
    <span style="font-size: 12pt; font-family: book antiqua,palatino;"><strong> F3</strong> : gestion des stages par un membre du service REE </span>
  </li>
  <li>
    <span style="font-size: 12pt; font-family: book antiqua,palatino;"><strong> F4</strong> : affectation d&rsquo;un stage à un étudiant par le responsable des stages du programme de l&rsquo;étudiant </span>
  </li>
  <li>
    <span style="font-size: 12pt; font-family: book antiqua,palatino;"><strong> F5</strong> : attribution d&rsquo;un suiveur à chaque étudiant parmi la liste des enseignants-chercheurs définie par le responsable du programme effectuée par le responsable des stages du programme des étudiants </span>
  </li>
</ul>

<p style="text-align: justify;">
   
</p>

<p style="text-align: justify;">
  <span style="font-size: 12pt; font-family: book antiqua,palatino;">Pour ceux qui seraient tentés de voir le contenu (code source) du projet, je l&rsquo;ai commité sur un <a title="Dépot SVN du projet" href="http://code.google.com/p/gestion-stages-utt/">dépot chez Google</a></span>
</p>
:   <span style="font-size: 12pt; font-family: book antiqua,palatino;">J&rsquo;avoue que le source n&rsquo;est pas tout le temps clean&#8230;Faut me comprendre j&rsquo;avais pas beaucoup de temps sur moi ^_^<br /></span>
<p style="text-align: center;">
  <em><strong><span style="font-size: 12pt; font-family: book antiqua,palatino;">Quelques Screenshots</span></strong></em>
</p>

<span style="font-size: 12pt; font-family: book antiqua,palatino;"><img loading="lazy" class=" size-full wp-image-62" style="display: block; margin-left: auto; margin-right: auto;" title="Page de connexion" src="https://charlesen.fr/wp-content/uploads/2010/11/images_blog_projets_LO09_ecran1.jpg" alt="Page de connexion" width="772" height="405" srcset="https://charlesen.fr/wp-content/uploads/2010/11/images_blog_projets_LO09_ecran1.jpg 807w, https://charlesen.fr/wp-content/uploads/2010/11/images_blog_projets_LO09_ecran1-300x158.jpg 300w, https://charlesen.fr/wp-content/uploads/2010/11/images_blog_projets_LO09_ecran1-768x404.jpg 768w, https://charlesen.fr/wp-content/uploads/2010/11/images_blog_projets_LO09_ecran1-700x368.jpg 700w" sizes="(max-width: 772px) 100vw, 772px" /></span>

 

<span style="font-size: 12pt; font-family: book antiqua,palatino;"><img loading="lazy" class=" size-full wp-image-63" style="display: block; margin-left: auto; margin-right: auto;" title="Affichage des suiveurs et des étudiants" src="https://charlesen.fr/wp-content/uploads/2010/11/images_blog_projets_LO09_ecran2.jpg" alt="Affichage des suiveurs et des étudiants" width="772" height="577" srcset="https://charlesen.fr/wp-content/uploads/2010/11/images_blog_projets_LO09_ecran2.jpg 772w, https://charlesen.fr/wp-content/uploads/2010/11/images_blog_projets_LO09_ecran2-300x224.jpg 300w, https://charlesen.fr/wp-content/uploads/2010/11/images_blog_projets_LO09_ecran2-768x574.jpg 768w, https://charlesen.fr/wp-content/uploads/2010/11/images_blog_projets_LO09_ecran2-700x523.jpg 700w" sizes="(max-width: 772px) 100vw, 772px" /></span>

 

<span style="font-size: 12pt; font-family: book antiqua,palatino;"><img loading="lazy" class=" size-full wp-image-64" style="display: block; margin-left: auto; margin-right: auto;" title="Ajout d'un nouveau suiveur" src="https://charlesen.fr/wp-content/uploads/2010/11/images_blog_projets_LO09_ecran3.png" alt="Ajout d'un nouveau suiveur" width="707" height="498" srcset="https://charlesen.fr/wp-content/uploads/2010/11/images_blog_projets_LO09_ecran3.png 707w, https://charlesen.fr/wp-content/uploads/2010/11/images_blog_projets_LO09_ecran3-300x211.png 300w, https://charlesen.fr/wp-content/uploads/2010/11/images_blog_projets_LO09_ecran3-700x493.png 700w" sizes="(max-width: 707px) 100vw, 707px" /></span>

 

<span style="font-size: 12pt; font-family: book antiqua,palatino;"><img loading="lazy" class=" size-full wp-image-65" style="display: block; margin-left: auto; margin-right: auto;" title="Recherche multi-critères" src="https://charlesen.fr/wp-content/uploads/2010/11/images_blog_projets_LO09_ecran4.jpg" alt="Recherche multi-critères" width="644" height="479" srcset="https://charlesen.fr/wp-content/uploads/2010/11/images_blog_projets_LO09_ecran4.jpg 644w, https://charlesen.fr/wp-content/uploads/2010/11/images_blog_projets_LO09_ecran4-300x223.jpg 300w" sizes="(max-width: 644px) 100vw, 644px" /><br /></span>