---
id: 253
title: Faciliter l’auto-complétion de formulaires avec Autofill
date: 2015-08-31T15:04:33+02:00
author: charlesen
layout: post
guid: https://charlesen.fr/?p=253
permalink: /faciliter-lauto-completion-de-formulaires-avec-autofill/
image: /wp-content/uploads/2015/08/images_mobile-form.png
categories:
  - tutoriel
tags:
  - attributs
  - autofill
  - card
  - carte
  - champs
  - checkout
  - chrome
  - credit
  - form
  - forms
  - formulaire
  - google
  - mobile
  - saisie
---
<img loading="lazy" class=" size-full wp-image-251" src="https://charlesen.fr/wp-content/uploads/2015/08/images_mobile-form.png" alt="" style="display: block; margin-left: auto; margin-right: auto;" width="200" height="379" srcset="https://charlesen.fr/wp-content/uploads/2015/08/images_mobile-form.png 200w, https://charlesen.fr/wp-content/uploads/2015/08/images_mobile-form-158x300.png 158w" sizes="(max-width: 200px) 100vw, 200px" />Personne,enfin je crois, n&rsquo;aime remplir des formulaires de plusieurs dizaines de champs, sur parfois plusieurs pages. Cela est surtout le cas quand il s&rsquo;agit de le faire depuis son smartphone : ça devient vite enervant, surtout s&rsquo;il s&rsquo;agit d&rsquo;un formulaire que l&rsquo;on avait déjà remplit dans le passé.

Pour résoudre cette difficulté rencontrée par les internautes, les navigateurs ont intégré l&rsquo;auto-complétion des champs de formulaires. Chrome en particulier a introduit Autofill qui permet de stocker vos informations de saisies dans un formulaire, pour les rendre disponible lors d&rsquo;une prochaine saisie comportant des champs similaires (notons les plus courants : adresse, ville, pays, nom, numéro de carte de crédit,&#8230;). Dans cet article, nous allons voir comment Autofill vous fera gagner énormement de temps, à vous ainsi qu&rsquo;à votre utilisateurs.

<!--more-->

### Autofill : comment ça marche ?

Imaginez que vous vous inscrivez sur un site de vente en ligne, créé par un très&nbsp;[bon développeur](index.php?option=com_contact&view=contact&id=1&Itemid=56). Vous renseignez des informations de base comme votre Nom, prénom, Adresse, ville, Pays et Carte bancaire. Vous validez le formulaire pour créer votre compte.

Quelques jours plus tard vous décidez de vous inscrire sur un site de covoiturage, développé par un autre [bon développeur](index.php?option=com_contact&view=contact&id=1&Itemid=56), qui là aussi vous demande votre Nom, prénom, Adresse, ville, Pays et Carte bancaire. Avec Autofill, vous n&rsquo;aurez plus à ressaisir ces informations puisqu&rsquo;elles auront déjà été sauvegardées dans votre navigateur. Il vous suffira alors de cliquer sur le premier champs (Nom), puis de saisir la première lettre pour voir apparaitre une suggestion de données.

<img loading="lazy" class=" size-full wp-image-252" src="https://charlesen.fr/wp-content/uploads/2015/08/images_chrome-form.png" alt="" style="display: block; margin-left: auto; margin-right: auto;" width="427" height="227" srcset="https://charlesen.fr/wp-content/uploads/2015/08/images_chrome-form.png 427w, https://charlesen.fr/wp-content/uploads/2015/08/images_chrome-form-300x159.png 300w" sizes="(max-width: 427px) 100vw, 427px" /> 

En cliquant sur la suggestion (touche « Entrée »), le formulaire se remplira automatiquement, vous faisant gagner un temps précieux dans votre journée déjà bien chargée.

Autofill gère différents types d&rsquo;attributs comme les cartes de crédits, le Nom, l&rsquo;Adress,&#8230;

### Carte de crédit

<table>
  <tr>
    <th>
      Attribut « name »
    </th>
    
    <th>
      Attribut « autocomplete »
    </th>
  </tr>
  
  <tr>
    <td>
      ccname
    </td>
    
    <td>
      cc-name
    </td>
  </tr>
  
  <tr>
    <td>
      cardnumber
    </td>
    
    <td>
      cc-number
    </td>
  </tr>
  
  <tr>
    <td>
      cvc
    </td>
    
    <td>
      cc-csc
    </td>
  </tr>
  
  <tr>
    <td>
      ccmonth
    </td>
    
    <td>
      cc-exp-month
    </td>
  </tr>
  
  <tr>
    <td>
      ccyear
    </td>
    
    <td>
      cc-exp-year
    </td>
  </tr>
  
  <tr>
    <td>
      exp-date
    </td>
    
    <td>
      cc-exp
    </td>
  </tr>
  
  <tr>
    <td>
      card-type
    </td>
    
    <td>
      cc-type
    </td>
  </tr>
</table>

&nbsp;

<pre>&lt;label for="frmNameCC"&gt;Nom du détenteur de la carte&lt;/label&gt;<br /> &lt;input autocomplete="cc-name" name="ccname" required="" type="text" id="frmNameCC" placeholder="Nom complet" /&gt;<br /> <br /> &lt;label for="frmCCNum"&gt;Numéro de carte&lt;/label&gt;<br /> &lt;input autocomplete="cc-number" name="cardnumber" required="" type="text" id="frmCCNum" /&gt;<br /> <br /> &lt;label for="frmCCCVC"&gt;Cryptogramme&lt;/label&gt;<br /> &lt;input autocomplete="cc-csc" name="cvc" required="" type="text" id="frmCCCVC" /&gt; <br /> <br /> &lt;label for="frmCCExp"&gt;Date d'expiration&lt;/label&gt;<br /> &lt;input autocomplete="cc-exp" name="cc-exp" required="" type="text" id="frmCCExp" placeholder="MM-YYYY" /&gt;</pre>

### Nom

<table>
  <tr>
    <th>
      Attribut « name »
    </th>
    
    <th>
      Attribut « autocomplete »
    </th>
  </tr>
  
  <tr>
    <td>
      name
    </td>
    
    <td>
      name (Nom complet)
    </td>
  </tr>
  
  <tr>
    <td>
      fname
    </td>
    
    <td>
      given-name(Prénom)
    </td>
  </tr>
  
  <tr>
    <td>
      mname
    </td>
    
    <td>
      additional-name(Deuxième Prénom)
    </td>
  </tr>
  
  <tr>
    <td>
      lname
    </td>
    
    <td>
      family-name(Nom de famille)
    </td>
  </tr>
</table>

<pre>&lt;label for="frmNameA"&gt;Nom&lt;/label&gt; &lt;input name="name" id="frmNameA" placeholder="Nom complet" required autocomplete="name"&gt;</pre>

### Email

<table>
  <tr>
    <th>
      Attribut « name »
    </th>
    
    <th>
      Attribut « autocomplete »
    </th>
  </tr>
  
  <tr>
    <td>
      email
    </td>
    
    <td>
      email
    </td>
  </tr>
</table>

<pre>&lt;label for="frmEmailA"&gt;Email&lt;/label&gt;<br />&lt;input type="email" name="email" id="frmEmailA" placeholder="<a href="mailto:charles@example.com&quot;">charles@example.com"</a> required autocomplete="email"&gt;&lt;label for="frmEmailC"&gt;Confirmer l'Email&lt;/label&gt;<br />&lt;input type="email" name="emailC" id="frmEmailC" placeholder="<a href="mailto:charles@example.com&quot;">charles@example.com"</a>  required autocomplete="email"&gt;</pre>

### Adresse

<table>
  <tr>
    <th>
      Attribut « name »
    </th>
    
    <th>
      Attribut « autocomplete »
    </th>
  </tr>
  
  <tr>
    <td>
      adress
    </td>
    
    <td>
      street-address (Si l&rsquo;adresse postale s&rsquo;écrit sur une seule ligne)
    </td>
  </tr>
  
  <tr>
    <td>
      city
    </td>
    
    <td>
      address-line1, address-line2 (Si l&rsquo;adresse postale s&rsquo;écrit sur deux lignes)
    </td>
  </tr>
  
  <tr>
    <td>
      region
    </td>
    
    <td>
      address-level1 (Région)
    </td>
  </tr>
  
  <tr>
    <td>
      province
    </td>
    
    <td>
      address-level2 (Département ou autre en fonction du Pays)
    </td>
  </tr>
  
  <tr>
    <td>
      state
    </td>
    
    <td>
      postal-code (Code postal)
    </td>
  </tr>
  
  <tr>
    <td>
      zip
    </td>
    
    <td>
      country
    </td>
  </tr>
  
  <tr>
    <td>
      zip2
    </td>
    
    <td>
      &nbsp;
    </td>
  </tr>
  
  <tr>
    <td>
      postal
    </td>
    
    <td>
      &nbsp;
    </td>
  </tr>
  
  <tr>
    <td>
      country
    </td>
    
    <td>
      &nbsp;
    </td>
  </tr>
</table>

<pre>&lt;label for="frmAddressS"&gt;Adresse&lt;/label&gt;<br />&lt;input name="ship-address" required id="frmAddressS" placeholder="17, rue du Berry" autocomplete="shipping street-address"&gt;<br />&lt;label for="frmCityS"&gt;Ville&lt;/label&gt;<br />&lt;input name="ship-city" required id="frmCityS" placeholder="Troyes" autocomplete="shipping address-level2"&gt;<br />&lt;label for="frmStateS"&gt;Région&lt;/label&gt;<br />&lt;input name="ship-state" required id="frmStateS" placeholder="Champagne-Ardenne" autocomplete="shipping address-level1"&gt;<br />&lt;label for="frmZipS"&gt;Code postal&lt;/label&gt;<br />&lt;input name="ship-zip" required id="frmZipS" placeholder="10000" autocomplete="shipping postal-code"&gt;<br />&lt;label for="frmCountryS"&gt;Pays&lt;/label&gt;<br />&lt;input name="ship-country" required id="frmCountryS" placeholder="FRANCE" autocomplete="shipping country"&gt;</pre>

### Téléphone

<table>
  <tr>
    <th>
      Attribut « name »
    </th>
    
    <th>
      Attribut « autocomplete »
    </th>
  </tr>
  
  <tr>
    <td>
      phone
    </td>
    
    <td>
      tel (Numéro de téléphone)
    </td>
  </tr>
  
  <tr>
    <td>
      mobile
    </td>
    
    <td>
      &nbsp;
    </td>
  </tr>
  
  <tr>
    <td>
      country-code
    </td>
    
    <td>
      &nbsp;
    </td>
  </tr>
  
  <tr>
    <td>
      area-code
    </td>
    
    <td>
      &nbsp;
    </td>
  </tr>
  
  <tr>
    <td>
      exchange
    </td>
    
    <td>
      &nbsp;
    </td>
  </tr>
  
  <tr>
    <td>
      suffix
    </td>
    
    <td>
      country
    </td>
  </tr>
  
  <tr>
    <td>
      ext
    </td>
    
    <td>
      &nbsp;
    </td>
  </tr>
</table>

### Exemple complet

<pre>&lt;form method="post" id="usrForm"&gt;<br /> &lt;fieldset&gt;<br /> &lt;legend&gt;Informations de contact&lt;/legend&gt;<br /> &lt;label for="frmNameA"&gt;Nom&lt;/label&gt;<br /> &lt;input name="name" id="frmNameA" placeholder="Nom complet" required autocomplete="name"&gt;<br /> &lt;label for="frmEmailA"&gt;Email&lt;/label&gt;<br /> &lt;input type="email" name="email" id="frmEmailA" placeholder="<a href="mailto:charles@example.com&quot;">charles@example.com"</a>; required autocomplete="email"&gt;<br /> &lt;label for="frmEmailC"&gt;Confirmer l'Email&lt;/label&gt;<br /> &lt;input type="email" name="emailC" id="frmEmailC" placeholder="<a href="mailto:charles@example.com&quot;">charles@example.com"</a>; required autocomplete="email"&gt;<br /> &lt;label for="frmPhoneNumA"&gt;Téléphone&lt;/label&gt;<br /> &lt;input type="tel" name="phone" id="frmPhoneNumA" placeholder="+33650780934" required autocomplete="tel"&gt;&lt;datalist id="chocType"&gt;<br /> &lt;option value="white"&gt;<br /> &lt;option value="milk"&gt;<br /> &lt;option value="dark"&gt;&lt;/datalist&gt;<br /> &lt;/fieldset&gt;<br /> &lt;fieldset&gt;<br /> &lt;legend&gt;Envoi&lt;/legend&gt;<br /> &lt;label for="frmAddressS"&gt;Adresse postale&lt;/label&gt;<br /> &lt;input name="ship-address" required id="frmAddressS" placeholder="17, rue du Berry" autocomplete="shipping street-address"&gt;<br /> &lt;label for="frmCityS"&gt;Ville&lt;/label&gt;<br /> &lt;input name="ship-city" required id="frmCityS" placeholder="Troyes" autocomplete="shipping locality"&gt;<br /> &lt;label for="frmStateS"&gt;Région&lt;/label&gt;<br /> &lt;input name="ship-state" required id="frmStateS" placeholder="Champagne-Ardenne" autocomplete="shipping region"&gt;<br /> &lt;label for="frmZipS"&gt;Code postal&lt;/label&gt;<br /> &lt;input name="ship-zip" required id="frmZipS" placeholder="10000" autocomplete="shipping postal-code"&gt;<br /> &lt;label for="frmCountryS"&gt;Pays&lt;/label&gt;<br /> &lt;input name="ship-country" required id="frmCountryS" placeholder="FRANCE" autocomplete="shipping country"&gt;&lt;label&gt;<br /> &lt;input type="checkbox" name="billAndShip" id="cbBillAndShip"&gt;<br /> &lt;br&gt;Envoi à cette adresse.&lt;/label&gt;<br /> &lt;/fieldset&gt;<br /> &lt;fieldset&gt;<br /> &lt;legend&gt;Adresse de Facturation&lt;/legend&gt;<br /> &lt;label for="frmAddressB"&gt;Adresse&lt;/label&gt;<br /> &lt;input name="bill-address" id="frmAddressB" required placeholder="17, rue du Berry" autocomplete="billing street-address"&gt;<br /> &lt;label for="frmCityB"&gt;Ville&lt;/label&gt;<br /> &lt;input name="bill-city" id="frmCityB" required placeholder="Troyes" autocomplete="billing locality"&gt;<br /> &lt;label for="frmStateB"&gt;Région&lt;/label&gt;<br /> &lt;input name="bill-state" id="frmStateB" required placeholder="Champagne-Ardenne" autocomplete="billing region"&gt;<br /> &lt;label for="frmZipB"&gt;Code postal&lt;/label&gt;<br /> &lt;input name="bill-zip" id="frmZipB" required placeholder="10000" autocomplete="billing postal-code"&gt;<br /> &lt;label for="frmCountryB"&gt;Pays&lt;/label&gt;<br /> &lt;input name="bill-country" id="frmCountryB" required placeholder="FRANCE" autocomplete="billing country"&gt;&lt;/fieldset&gt;&lt;div id="paymentSec"&gt;<br /> &lt;fieldset&gt;<br /> &lt;legend&gt;Paiement&lt;/legend&gt;<br /> &lt;label for="frmNameCC"&gt;Détenteur de la carte&lt;/label&gt;<br /> &lt;input name="ccname" id="frmNameCC" required placeholder="Full Name" autocomplete="cc-name"&gt;<br /> &lt;label for="frmCCNum"&gt;Numéro de carte bancaire&lt;/label&gt;<br /> &lt;input name="cardnumber" id="frmCCNum" required autocomplete="cc-number"&gt;<br /> &lt;label for="frmCCCVC"&gt;Cryptogramme&lt;/label&gt;<br /> &lt;input name="cvc" id="frmCCCVC" required autocomplete="cc-csc"&gt;<br /> &lt;label for="frmCCExp"&gt;Date d'expiration&lt;/label&gt;<br /> &lt;input name="cc-exp" id="frmCCExp" required placeholder="MM-YYYY" autocomplete="cc-exp"&gt;<br /> &lt;div&gt;<br /> &lt;button class="btn" id="butCheckout"&gt;Valider&lt;/button&gt;<br /> &lt;/div&gt;<br /> &lt;/fieldset&gt;<br /> &lt;/div&gt;<br /> &lt;/form&gt;</pre>