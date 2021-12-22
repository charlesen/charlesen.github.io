---
id: 212
title: eXtraire du contenu XML en JavaScript pur
date: 2012-09-25T16:02:20+02:00
author: charlesen
layout: post
guid: https://charlesen.fr/?p=212
permalink: /extraire-du-contenu-xml-en-javascript-pur/
categories:
  - tutoriel
---
<div>
  En voulant extraire un fichier xml aujourd&rsquo;hui en passant par jQuery (mon l&rsquo;application utilise la version 1.4.2) je me suis rendu compte que la fonction parseXML n&rsquo;était pas présente dans cette version du Framework JavaScript&#8230;Bon il a quand même fallut que j&rsquo;aille faire un tour dans le fichier jQuery, version non-compressée bien sûr, l&rsquo;autre est absolument illisible. De là un <strong>CTRL + F + « parseXML »</strong> me confirme l&rsquo;absence de la fonction dans la version 1.4.2&#8230;.Et là&#8230;c&rsquo;est le drame&#8230;..Noooooon !!&nbsp;
</div>

<div>
</div>

<div>
  Ne pouvant pas décider de passer brusquement à une version supérieur (étant donné que l&rsquo;application développée est basée sur cette version 1.4.2&#8230;prudence, prudence), j&rsquo;ai choisi de créer une petite fonction JavaScript qui ferait ce travail aussi facilement qu&rsquo;en jQuery. En voici le contenu :
</div>

<div>
</div>

<div>
  <div class="rj_insertcode">
    <div class="rj_insertcode_javascript" style="overflow: auto; width: 80%; height: auto; border: 1px solid #054b6e; background: #f8f8f8;">
      <table class="javascript" style="border-collapse: collapse; width: 100%;">
        <tr>
          <td colspan="2" style="background: #dddddd; color: #054b6e; padding: 2px 0px; text-align: center; font: bold italic 12px Verdana, Geneva, Arial, Helvetica, sans-serif;">
            Parser XML
          </td>
        </tr>
        
        <tr class="li1">
          <td style="width: 1px; background: #f0f0f0; vertical-align: top; color: #676f73; border-right: 1px dotted #dddddd; font-size: 12px; text-align: right;">
            <pre style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;">1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 </pre>
          </td>
          
          <td style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;">
            <pre style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;"><span style="vertical-align: top;">	<span style="color: #006600; font-style: italic;">//Parser XML</span></span> <span style="vertical-align: top;">	<span style="color: #003366; font-weight: bold;">function</span> parseXML<span style="color: #009900;">(</span>txt<span style="color: #009900;">)</span> <span style="color: #009900;">{</span></span> <span style="vertical-align: top;">		<span style="color: #000066; font-weight: bold;">if</span> <span style="color: #009900;">(</span>window.<span style="color: #660066;">DOMParser</span><span style="color: #009900;">)</span></span> <span style="vertical-align: top;">		  <span style="color: #009900;">{</span></span> <span style="vertical-align: top;">		  parser<span style="color: #339933;">=</span><span style="color: #003366; font-weight: bold;">new</span> DOMParser<span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span></span> <span style="vertical-align: top;">		  xmlDoc<span style="color: #339933;">=</span>parser.<span style="color: #660066;">parseFromString</span><span style="color: #009900;">(</span>txt<span style="color: #339933;">,</span><span style="color: #3366cc;">"text/xml"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span></span> <span style="vertical-align: top;">		  <span style="color: #009900;">}</span></span> <span style="vertical-align: top;">		<span style="color: #000066; font-weight: bold;">else</span> <span style="color: #006600; font-style: italic;">// Internet Explorer</span></span> <span style="vertical-align: top;">		  <span style="color: #009900;">{</span></span> <span style="vertical-align: top;">		  xmlDoc<span style="color: #339933;">=</span><span style="color: #003366; font-weight: bold;">new</span> ActiveXObject<span style="color: #009900;">(</span><span style="color: #3366cc;">"Microsoft.XMLDOM"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span></span> <span style="vertical-align: top;">		  xmlDoc.<span style="color: #660066;">async</span><span style="color: #339933;">=</span><span style="color: #003366; font-weight: bold;">false</span><span style="color: #339933;">;</span></span> <span style="vertical-align: top;">		  xmlDoc.<span style="color: #660066;">loadXML</span><span style="color: #009900;">(</span>txt<span style="color: #009900;">)</span><span style="color: #339933;">;</span> </span> <span style="vertical-align: top;">		  <span style="color: #009900;">}</span></span> <span style="vertical-align: top;">		<span style="color: #000066; font-weight: bold;">return</span> xmlDoc<span style="color: #339933;">;</span></span> <span style="vertical-align: top;">	<span style="color: #009900;">}</span></span></pre>
          </td>
        </tr>
      </table>
    </div></p>
  </div></p>
</div>

<div>
</div>

<div>
</div>

<div>
  Et l&rsquo;utilisation se fait très simplement. Considérons le contenu XML suivant :
</div>

<div>
</div>

<div>
  <div class="rj_insertcode">
    <div class="rj_insertcode_javascript" style="overflow: auto; width: 80%; height: auto; border: 1px solid #054b6e; background: #f8f8f8;">
      <table class="javascript" style="border-collapse: collapse; width: 100%;">
        <tr>
          <td colspan="2" style="background: #dddddd; color: #054b6e; padding: 2px 0px; text-align: center; font: bold italic 12px Verdana, Geneva, Arial, Helvetica, sans-serif;">
            Contenu XML
          </td>
        </tr>
        
        <tr class="li1">
          <td style="width: 1px; background: #f0f0f0; vertical-align: top; color: #676f73; border-right: 1px dotted #dddddd; font-size: 12px; text-align: right;">
            <pre style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;">1 2 3 4 5 6 </pre>
          </td>
          
          <td style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;">
            <pre style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;"><span style="vertical-align: top;"><span style="color: #339933;">&lt;</span>book category<span style="color: #339933;">=</span><span style="color: #3366cc;">"mobile"</span><span style="color: #339933;">&gt;</span></span> <span style="vertical-align: top;">    <span style="color: #339933;">&lt;</span>title lang<span style="color: #339933;">=</span><span style="color: #3366cc;">"fr"</span><span style="color: #339933;">&gt;</span>Développer avec jQuery Mobile<span style="color: #339933;">&lt;/</span>title<span style="color: #339933;">&gt;</span></span> <span style="vertical-align: top;">    <span style="color: #339933;">&lt;</span>author<span style="color: #339933;">&gt;</span>Mobile<span style="color: #339933;">-</span>tuts<span style="color: #339933;">!&lt;/</span>author<span style="color: #339933;">&gt;</span></span> <span style="vertical-align: top;">    <span style="color: #339933;">&lt;</span>year<span style="color: #339933;">&gt;</span><span style="color: #cc0000;">2012</span><span style="color: #339933;">&lt;/</span>year<span style="color: #339933;">&gt;</span></span> <span style="vertical-align: top;">    <span style="color: #339933;">&lt;</span>price<span style="color: #339933;">&gt;</span>Free<span style="color: #339933;">&lt;/</span>price<span style="color: #339933;">&gt;</span></span> <span style="vertical-align: top;"><span style="color: #339933;">&lt;/</span>book<span style="color: #339933;">&gt;</span></span></pre>
          </td>
        </tr>
      </table>
    </div></p>
  </div></p>
</div>

<div>
</div>

<div>
</div>

<div>
  Pour récupérer le titre et le nom de l&rsquo;auteur, il suffit de faire :
</div>

<div>
</div>

<div>
  <div class="rj_insertcode">
    <div class="rj_insertcode_javascript" style="overflow: auto; width: 80%; height: auto; border: 1px solid #054b6e; background: #f8f8f8;">
      <table class="javascript" style="border-collapse: collapse; width: 100%;">
        <tr>
          <td colspan="2" style="background: #dddddd; color: #054b6e; padding: 2px 0px; text-align: center; font: bold italic 12px Verdana, Geneva, Arial, Helvetica, sans-serif;">
            Exemple d&rsquo;utilisation
          </td>
        </tr>
        
        <tr class="li1">
          <td style="width: 1px; background: #f0f0f0; vertical-align: top; color: #676f73; border-right: 1px dotted #dddddd; font-size: 12px; text-align: right;">
            <pre style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;">1 2 3 4 5 6 7 8 9 </pre>
          </td>
          
          <td style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;">
            <pre style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;"><span style="vertical-align: top;">xmlDoc <span style="color: #339933;">=</span> parseXML<span style="color: #009900;">(</span>response<span style="color: #009900;">)</span><span style="color: #339933;">; // Le contenu est par exemple retourné en ajax</span></span> <span style="vertical-align: top;">titre<span style="color: #339933;">=</span>xmlDoc.<span style="color: #660066;">getElementsByTagName</span><span style="color: #009900;">(</span><span style="color: #3366cc;">"title"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span></span> <span style="vertical-align: top;">auteur<span style="color: #339933;">=</span>xmlDoc.<span style="color: #660066;">getElementsByTagName</span><span style="color: #009900;">(</span><span style="color: #3366cc;">"author"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span></span> <span style="vertical-align: top;"><span style="color: #000066; font-weight: bold;">for</span> <span style="color: #009900;">(</span>i<span style="color: #339933;">=</span><span style="color: #cc0000;"></span><span style="color: #339933;">;</span>i<span style="color: #339933;">&lt;</span>title.<span style="color: #660066;">length</span><span style="color: #339933;">;</span>i<span style="color: #339933;">++</span><span style="color: #009900;">)</span><span style="color: #009900;">{</span></span> <span style="vertical-align: top;">      <span style="color: #003366; font-weight: bold;">var</span> noeudTitre <span style="color: #339933;">=</span> titre<span style="color: #009900;">[</span>i<span style="color: #009900;">]</span>.<span style="color: #660066;">nodeName</span><span style="color: #339933;">,</span> <span style="color: #339933; line-height: 18px;">// contient la chaine "title"</span></span> <span style="vertical-align: top;">      titreContenu<span style="color: #339933;">=</span> titre<span style="color: #009900;">[</span>i<span style="color: #009900;">]</span>.<span style="color: #660066;">childNodes</span><span style="color: #009900;">[</span><span style="color: #cc0000;"></span><span style="color: #009900;">]</span>.<span style="color: #660066;">nodeValue</span><span style="color: #339933;">; <span style="line-height: 18px;"> </span><span style="line-height: 18px;">// contient la chaine "Développer avec..."</span><br /></span></span><span style="vertical-align: top;">      <span style="color: #003366; font-weight: bold;">var</span> noeudAuteur <span style="color: #339933;">=</span> auteur<span style="color: #009900;">[</span>i<span style="color: #009900;">]</span>.<span style="color: #660066;">nodeName</span><span style="color: #339933;">,</span> </span> <span style="vertical-align: top;">      auteurContenu<span style="color: #339933;">=</span> title<span style="color: #009900;">[</span>i<span style="color: #009900;">]</span>.<span style="color: #660066;">childNodes</span><span style="color: #009900;">[</span><span style="color: #cc0000;"></span><span style="color: #009900;">]</span>.<span style="color: #660066;">nodeValue</span><span style="color: #339933;">; <span style="line-height: 18px;"> </span><span style="line-height: 18px;">// contient la chaine "Mobile-tuts!"</span><br /></span></span><span style="vertical-align: top;"><span style="color: #009900;">}</span></span></pre>
          </td>
        </tr>
      </table>
    </div></p>
  </div></p>
</div>

<div>
</div>

<div>
  Voilà, rien de bien compliqué 🙂
</div>