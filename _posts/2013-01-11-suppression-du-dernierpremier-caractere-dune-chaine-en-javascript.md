---
id: 213
title: 'Suppression du dernier/premier caractère d&rsquo;une chaîne en Javascript'
date: 2013-01-11T08:06:54+01:00
author: charlesen
layout: post
guid: https://charlesen.fr/?p=213
permalink: /suppression-du-dernierpremier-caractere-dune-chaine-en-javascript/
categories:
  - tutoriel
tags:
  - chaîne de caractère
  - javascript
  - regular expressions
  - remove last char
  - string replace
  - suppression
---
<div>
  Etant de bonne humeur aujourd&rsquo;hui, j&rsquo;ai envie de voir avec vous quelques trucs et astuces en Javascript. J&rsquo;ai commandé le livre de John Resig (<a href="http://www.amazon.fr/gp/product/193398869X/ref=as_li_ss_tl?ie=UTF8&camp=1642&creative=19458&creativeASIN=193398869X&linkCode=as2&tag=charlehomepa-21" title="Commander le livre">Secrets of the JavaScript Ninja</a><img loading="lazy" src="http://www.assoc-amazon.fr/e/ir?t=charlehomepa-21&l=as2&o=8&a=193398869X" width="1" height="1" border="0" style="border: none !important; margin: 0px !important;" /> ) qui ne devrait pas tarder, et je pense après lecture vous proposer pas mal de contenu sur ce super langage de script.
</div>

<div>
  Mais pour le moment, nous allons voir comment supprimer un quelconque caractère contenu dans une chaine en Javascript. Considérons la chaine de caractère <strong>str = « Hello World ! »</strong>
</div>

<div>
</div>

<div>
</div>

### Suppression du premier caractère

<div>
</div>

<div>
  <div class="rj_insertcode">
    <div style="overflow: auto; width: 100%; height: auto; border: 1px solid #054b6e; background: #f8f8f8;" class="rj_insertcode_javascript">
      <table style="border-collapse: collapse; width: 100%;" class="javascript">
        <tr>
          <td style="background: #dddddd; color: #054b6e; padding: 2px 0px; text-align: center; font: bold italic 12px Verdana, Geneva, Arial, Helvetica, sans-serif;" colspan="2">
            On supprime le premier caractère (« h »)
          </td>
        </tr>
        
        <tr class="li1">
          <td style="width: 1px; background: #f0f0f0; vertical-align: top; color: #676f73; border-right: 1px dotted #dddddd; font-size: 12px; text-align: right;">
            <pre style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;">1 </pre>
          </td>
          
          <td style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;">
            <pre style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;"><span style="vertical-align: top;">console.<span style="color: #660066;">log</span> <span style="color: #009900;">(</span>str.<span style="color: #660066;">replace</span><span style="color: #009900;">(</span><span style="color: #009966; font-style: italic;">/^.(\s+)?/</span><span style="color: #339933;">,</span> <span style="color: #3366cc;">''</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span></span></pre>
          </td>
        </tr>
      </table>
    </div></p>
  </div></p>
</div>

<div>
</div>

<div>
  Renvoie : <em><strong>« <span style="color: #000000; font-family: Consolas, 'Lucida Console', monospace; font-size: 12px; line-height: normal; white-space: pre-wrap;">ello World !</span>« </strong>&nbsp;</em>
</div>

<div>
</div>

<div>
</div>

<div>
  <h3>
    Suppression du dernier caractère
  </h3>
  
  <div>
  </div></p>
</div>

<div>
  <div class="rj_insertcode">
    <div style="overflow: auto; width: 100%; height: auto; border: 1px solid #054b6e; background: #f8f8f8;" class="rj_insertcode_javascript">
      <table style="border-collapse: collapse; width: 100%;" class="javascript">
        <tr>
          <td style="background: #dddddd; color: #054b6e; padding: 2px 0px; text-align: center; font: bold italic 12px Verdana, Geneva, Arial, Helvetica, sans-serif;" colspan="2">
            On supprime le dernier caractère (« ! »)
          </td>
        </tr>
        
        <tr class="li1">
          <td style="width: 1px; background: #f0f0f0; vertical-align: top; color: #676f73; border-right: 1px dotted #dddddd; font-size: 12px; text-align: right;">
            <pre style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;">1 </pre>
          </td>
          
          <td style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;">
            <pre style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;"><span style="vertical-align: top;">console.<span style="color: #660066;">log</span> <span style="color: #009900;">(</span>str.<span style="color: #660066;">replace</span><span style="color: #009900;">(</span><span style="color: #009966; font-style: italic;">/(\s+)?.$/</span><span style="color: #339933;">,</span> <span style="color: #3366cc;">''</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span></span></pre>
          </td>
        </tr>
      </table>
    </div></p>
  </div></p>
</div>

<div>
</div>

<div>
  Renvoie : <em><strong>« <span style="color: #000000; font-family: Consolas, 'Lucida Console', monospace; font-size: 12px; line-height: normal; white-space: pre-wrap;">Hello World</span>« </strong></em>
</div>

<div>
</div>

### Suppression d&rsquo;un caractère spécifique

<div>
</div>

<div>
  <div class="rj_insertcode">
    <div style="overflow: auto; width: 100%; height: auto; border: 1px solid #054b6e; background: #f8f8f8;" class="rj_insertcode_javascript">
      <table style="border-collapse: collapse; width: 100%;" class="javascript">
        <tr>
          <td style="background: #dddddd; color: #054b6e; padding: 2px 0px; text-align: center; font: bold italic 12px Verdana, Geneva, Arial, Helvetica, sans-serif;" colspan="2">
            Suppression du caractère « o » dans la chaine
          </td>
        </tr>
        
        <tr class="li1">
          <td style="width: 1px; background: #f0f0f0; vertical-align: top; color: #676f73; border-right: 1px dotted #dddddd; font-size: 12px; text-align: right;">
            <pre style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;">1 </pre>
          </td>
          
          <td style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;">
            <pre style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;"><span style="vertical-align: top;">console.<span style="color: #660066;">log</span> <span style="color: #009900;">(</span>str.<span style="color: #660066;">replace</span><span style="color: #009900;">(</span><span style="color: #009966; font-style: italic;">/o/gi</span><span style="color: #339933;">,</span> <span style="color: #3366cc;">''</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span></span></pre>
          </td>
        </tr>
      </table>
    </div></p>
  </div></p>
</div>

<div>
</div>

<div>
  Renvoie : <em><strong>« <span style="color: #000000; font-family: Consolas, 'Lucida Console', monospace; font-size: 12px; line-height: normal; white-space: pre-wrap;">Hell Wrld !</span>« </strong></em>
</div>

<div>
</div>

<div>
  Voilà, rien de très compliqué 🙂
</div>