---
id: 25
title: 'Créer des effets Web 2.0 avec le mambo mkreflex &#8211; compatible joomla 1.0'
date: 2009-10-20T16:04:18+02:00
author: charlesen
layout: post
guid: https://charlesen.fr/?p=25
permalink: /creer-des-effets-web-20-avec-le-mambo-mkreflex-compatible-joomla-10/
categories:
  - tutoriel
tags:
  - gimp
  - image reflex
  - joomla 1.5
  - joomla 1.6
  - mkreflex
  - photoshop
  - "réflexion d'image"
---
<span style="font-size: 12pt;"><span style="font-family: book antiqua,palatino;">MfReflex est un mambot qui vous permet d&rsquo;ajouter facilement des effets de reflexion style Web 2.0 avec une inclinaison des images. Il est simple d&rsquo;utilisation et vous évitera l&rsquo;utilisation de logiciel un peu compliqué et surtout payant comme photoshop. La seule chose qu&rsquo;on puisse lui reprocher c&rsquo;est sa seul compatibilité avec Joomla 1.0</span></span>

<span style="font-size: 12pt;"><span style="font-family: book antiqua,palatino;"> <!--more--></span></span> 

### <span style="font-size: 12pt;"><span style="font-family: book antiqua,palatino;"><span style="color: #808000;">Syntaxe</span></span></span>

<span style="font-size: 12pt;"><span style="font-family: book antiqua,palatino;">Pour ajouter des effets à vos images, il suffit d&rsquo;utiliser la syntaxe suivante:<br /><strong>{mfreflex dossier/</strong><strong>votre_image</strong><strong>}</strong></span></span>

<span style="font-size: 12pt;"><span style="font-family: book antiqua,palatino;">Les images ont pour racine le dossier: <code>images/stories</code>. Si vous possédez donc une image stockée dans <code>images/stories</code> folder, votre syntaxe deviendra: <strong>{mfreflex votre_image}</strong></span></span>

<span style="font-size: 12pt;"><span style="font-family: book antiqua,palatino;">De même si vous posséder un sous-dossier <code>images/stories/dossier2</code> , la syntaxe sera: <strong>{mfreflex </strong><strong><code>dossier2</code>/</strong><strong>votre_image</strong><strong>}</strong></span></span>

<span style="font-size: 12pt;"><span style="font-family: book antiqua,palatino;">Il est nécessaire que le navigateur est javascript d&rsquo;activé. Dans le cas contraire l&rsquo;effet ne sera pris en compte, et le navigateur affichera votre image sans formatage</span></span>

<span style="font-size: 12pt;"><span style="font-family: book antiqua,palatino;"><strong> </strong><strong>{mfreflex powered_by.png}</strong></span></span>

### <span style="font-size: 12pt;"><span style="font-family: book antiqua,palatino;"><span style="color: #808000;">Configuration avancée</span></span></span>

<span style="font-size: 12pt;"><span style="font-family: book antiqua,palatino;">mfReflex utilise plusieurs paramètres séparés par le symbole | (pipe).</span></span>

  1. <span style="font-size: 12pt;"><span style="font-family: book antiqua,palatino;">Le chemin et le nom de l&rsquo;image. C&rsquo;est la syntaxe de base du plugin.<br /><em>Exemple:</em> <strong>{mfreflex dossier/nom_image}</strong></span></span> 
  2. <span style="font-size: 12pt;"><span style="font-family: book antiqua,palatino;">l&rsquo;attribut ALT permet bien sûr d&rsquo;ajouter un texte alternatif . <br /><em>Exemple:</em> <strong>{mfreflex </strong><strong>dossier/nom_image</strong><strong>|Logo}</strong></span></span> 
  3. <span style="font-size: 12pt;"><span style="font-family: book antiqua,palatino;">Positionner l&rsquo;image à gauche ou à droite.<br /><em>Exemple:</em> <strong>{mfreflex </strong><strong>dossier/nom_image</strong><strong>|Logo|right}</strong></span></span> 
  4. <span style="font-size: 12pt;"><span style="font-family: book antiqua,palatino;">Choisir l&rsquo;opacité de la reflexion en pourcentage (0-100%). La valeur par défaut est 33%.<br /><em>Exemple:</em> <strong>{mfreflex </strong><strong>dossier/nom_image</strong><strong>|Logo|right|90}</strong></span></span> 
  5. <span style="font-size: 12pt;"><span style="font-family: book antiqua,palatino;">Choisir une bordure pour l&rsquo;image. La reflexion montrera aussi la bordure. Utiliser des valeurs en pixels de 0 à 100. La valeur par défaut est 0.<br /><em>Exemple:</em> <strong>{mfreflex </strong><strong>dossier/nom_image</strong><strong>|Logo|right|90|5}</strong></span></span> 
  6. <span style="font-size: 12pt;"><span style="font-family: book antiqua,palatino;">Distance entre l&rsquo;image et la reflexion. Utiliser des valeurs en pixels de 0 à 100. La valeur par défaut est 0.<br /><em>Exemple:</em> <strong>{mfreflex </strong><strong>dossier/nom_image</strong><strong>|Logo|right|90|5|10}</strong></span></span> 
  7. <span style="font-size: 12pt;"><span style="font-family: book antiqua,palatino;">Effet 3D Z-tilt. Vous pourrez choisir entre right, none et left. <!-- By default, the script rotates through the tilt variations.-->
    
    <br /><em>Exemple:</em> <strong>{mfreflex </strong><strong>dossier/nom_image</strong><strong>|Logo|right|90|5|10|none}</strong></span></span> 

<!-- 

<p><span style="font-size: 12pt;"            >Now I would have a reflex image with an ALT attribute called "Logo", floating on the right, with a reflection opacity of 90%, a border of 5 pixels, with a distance of 10 pixels between the image and the reflection and with no Z-tilt.</span></p>

 

<p><span style="font-size: 12pt;"            >Only the first parameter must be filled. All others are optional. If you don't want to use the parameter, leave it empty. For example, if you want all default settings, but another Z-tilt, use the following syntax:<br /><strong>{mfreflex imgpath/img_name||||||none}</strong></span></p>

 -->