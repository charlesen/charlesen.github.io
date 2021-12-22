---
id: 135
title: 'Construire des applications Android à l&rsquo;aide des WebView'
date: 2011-02-15T11:37:55+01:00
author: charlesen
layout: post
guid: https://charlesen.fr/?p=135
permalink: /construire-des-applications-android-a-laide-de-webview/
image: /wp-content/uploads/2011/02/images_market-intl.png
categories:
  - tutoriel
---
<img loading="lazy" class=" alignleft size-full wp-image-133" src="https://charlesen.fr/wp-content/uploads/2011/02/images_market-intl.png" border="0" alt="Android Market" title="Android Market" style="float: left;" width="104" height="120" />Une méthode facile pour passer d&rsquo;une application (service) web, à une application native [Android](index.php?option=com_content&view=article&id=87:android-devient-la-plateforme-mobile-la-plus-importante-au-monde&catid=36&Itemid=61 "Voir l'article sur Android") est l&rsquo;utilisation d&rsquo;une classe bien spéciale sous Android appelée _**WebView**_. Cette classe, qui hérite de la classe _**View**_ offre la possibilité d&rsquo;afficher une page web à l&rsquo;intérieur d&rsquo;une activité. On peut donc, à partir d&rsquo;un site web (à peu près) optimisé pour les mobiles, créer une application dite native. Voyons comment ça marche.

<!--more-->

  * <span style="font-family: book antiqua,palatino; font-size: 12pt;"><strong>Ajouter le WebView au layout</strong></span>

C&rsquo;est la première chose à faire. Cliquez donc sur votre fichier layout.xml ou une chose du genre, et ajouter les lignes suivantes :

<div class="rj_insertcode">
  <div class="rj_insertcode_xml" style="overflow: auto; width: 100%; height: auto; border: 1px solid #054b6e; background: #ffffff;">
    <table class="xml" style="border-collapse: collapse; width: 100%;">
      <tr class="li1">
        <td style="width: 1px; background: none repeat scroll 0% 0% #f0f0f0; vertical-align: top; color: #676f73; border-right: 1px dotted #dddddd; font-size: 12px; text-align: right;">
          <pre style="margin: 0pt; background: none repeat scroll 0% 0% transparent; vertical-align: top; padding: 0px 4px; font-size: 12px;">1<br />2<br />3<br />4<br />5<br />6</pre>
        </td>
        
        <td style="margin: 0pt; background: none repeat scroll 0% 0% transparent; vertical-align: top; padding: 0px 4px; font-size: 12px;">
          <pre style="margin: 0pt; background: none repeat scroll 0% 0% transparent; vertical-align: top; padding: 0px 4px; font-size: 12px;"><span style="vertical-align: top;"><span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;?xml</span> <span style="color: #000066;">version</span>=<span style="color: #ff0000;">"1.0"</span> <span style="color: #000066;">encoding</span>=<span style="color: #ff0000;">"utf-8"</span><span style="color: #000000; font-weight: bold;">?&gt;</span></span></span><br /><span style="vertical-align: top;"><span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;WebView</span>  <span style="color: #000066;">xmlns:android</span>=<span style="color: #ff0000;">"http://schemas.android.com/apk/res/android"</span></span></span><br /><span style="vertical-align: top;"><span style="color: #009900;">    <span style="color: #000066;">android:id</span>=<span style="color: #ff0000;">"@+id/webview"</span></span></span><br /><span style="vertical-align: top;"><span style="color: #009900;">    <span style="color: #000066;">android:layout_width</span>=<span style="color: #ff0000;">"fill_parent"</span></span></span><br /><span style="vertical-align: top;"><span style="color: #009900;">    <span style="color: #000066;">android:layout_height</span>=<span style="color: #ff0000;">"fill_parent"</span></span></span><br /><span style="vertical-align: top;"><span style="color: #009900;"><span style="color: #000000; font-weight: bold;">/&gt;</span></span></span></pre>
        </td>
      </tr>
    </table>
  </div></p>
</div>

 

On y dit simplement que notre WebView (et donc notre page web) s&rsquo;affichera de façon à occuper tout l&rsquo;espace qui lui est offert par son élèment parent (fill_parent).

 

  * <span style="font-size: 12pt; font-family: book antiqua,palatino;"><strong>Appeler le WebView dans votre activité</strong></span>

A prèsent dans votre activité principale, il vous suffit d&rsquo;initialiser votre WebView et d&rsquo;afficher le site, en utilisant la méthode [**loadUrl()**](http://d.android.com/reference/android/webkit/WebView.html#loadUrl%28java.lang.String%29 "Voir la méthode..."):

<div class="rj_insertcode">
  <div class="rj_insertcode_xml" style="overflow: auto; width: 100%; height: auto; border: 1px solid #054b6e; background: #f8f8f8;">
    <table class="xml" style="border-collapse: collapse; width: 100%;">
      <tr class="li1">
        <td style="width: 1px; background: none repeat scroll 0% 0% #f0f0f0; vertical-align: top; color: #676f73; border-right: 1px dotted #dddddd; font-size: 12px; text-align: right;">
          <pre style="margin: 0pt; background: none repeat scroll 0% 0% transparent; vertical-align: top; padding: 0px 4px; font-size: 12px;">1<br />2</pre>
          
          <pre style="margin: 0pt; background: none repeat scroll 0% 0% transparent; vertical-align: top; padding: 0px 4px; font-size: 12px;">3</pre>
        </td>
        
        <td style="margin: 0pt; background: none repeat scroll 0% 0% transparent; vertical-align: top; padding: 0px 4px; font-size: 12px;">
          <pre style="margin: 0pt; background: none repeat scroll 0% 0% transparent; vertical-align: top; padding: 0px 4px; font-size: 12px;"><span style="vertical-align: top;">WebView myWebView = (WebView) findViewById(R.id.webview);</span><br /><span style="vertical-align: top;">myWebView.loadUrl("http://m.charlesen.fr");</span></pre>
          
          <pre style="margin: 0pt; background: none repeat scroll 0% 0% transparent; vertical-align: top; padding: 0px 4px; font-size: 12px;"><span style="vertical-align: top;">myWebView.setWebViewClient(new WebViewClient()); // </span><span style="color: #666666; font-style: italic; font-size: 12px; line-height: 18px; background-color: transparent;">Tous les liens s'ouvriront directement depuis la WebView</span></pre>
        </td>
      </tr>
    </table>
  </div></p>
</div>

 

La dernière chose à faire est d&rsquo;autoriser l&rsquo;accès internet à votre application, en modifiant le fichier **manifest** :

<div class="rj_insertcode">
  <div class="rj_insertcode_xml" style="overflow: auto; width: 100%; height: auto; border: 1px solid #054b6e; background: #f8f8f8;">
    <table class="xml" style="border-collapse: collapse; width: 100%;">
      <tr class="li1">
        <td style="width: 1px; background: none repeat scroll 0% 0% #f0f0f0; vertical-align: top; color: #676f73; border-right: 1px dotted #dddddd; font-size: 12px; text-align: right;">
          <pre style="margin: 0pt; background: none repeat scroll 0% 0% transparent; vertical-align: top; padding: 0px 4px; font-size: 12px;">1<br />2<br />3<br />4</pre>
        </td>
        
        <td style="margin: 0pt; background: none repeat scroll 0% 0% transparent; vertical-align: top; padding: 0px 4px; font-size: 12px;">
          <pre style="margin: 0pt; background: none repeat scroll 0% 0% transparent; vertical-align: top; padding: 0px 4px; font-size: 12px;"><span style="vertical-align: top;"><span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;manifest</span> ... <span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br /><span style="vertical-align: top;">    <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;uses-permission</span> <span style="color: #000066;">android:name</span>=<span style="color: #ff0000;">"android.permission.INTERNET"</span> <span style="color: #000000; font-weight: bold;">/&gt;</span></span></span><br /><span style="vertical-align: top;">    ...</span><br /><span style="vertical-align: top;"><span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/manifest<span style="color: #000000; font-weight: bold;">&gt;</span></span></span></span></pre>
        </td>
      </tr>
    </table>
  </div></p>
</div>

 

Voici un exemple complet, avec mon site web mobile développé à l&rsquo;aide de [jQuery Mobile](index.php?option=com_content&view=article&id=93:introduction-a-jquery-mobile-framework-de-developpement-mobile&catid=35&Itemid=61 "Voir l'article sur jQuery Mobile"), et porté sous Android :

<table class="java" style="border-collapse: collapse; width: 100%;">
  <tr>
    <td style="background: #dddddd; color: #054b6e; padding: 2px 0px; text-align: center; font: bold italic 12px Verdana, Geneva, Arial, Helvetica, sans-serif;" colspan="2">
      Activité principale
    </td>
  </tr>
  
  <tr class="li1">
    <td style="width: 1px; background: #f0f0f0; vertical-align: top; color: #676f73; border-right: 1px dotted #dddddd; font-size: 12px; text-align: right;">
      <pre style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;">1<br />2<br />3<br />4<br />5<br />6<br />7<br />8<br />9<br />10<br />11<br />12<br />13<br />14<br />15<br />16<br />17<br />18<br />19<br />20<br />21<br />22<br />23<br />24<br />25</pre>
    </td>
    
    <td style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;">
      <pre style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;"><span style="vertical-align: top;"><span style="color: #000000; font-weight: bold;">package</span> <span style="color: #006699;">fr.charlesen.projets</span><span style="color: #339933;">;</span></span><br /><span style="vertical-align: top;"> </span><br /><span style="vertical-align: top;"><span style="color: #000000; font-weight: bold;">import</span> <span style="color: #006699;">android.app.Activity</span><span style="color: #339933;">;</span></span><br /><span style="vertical-align: top;"><span style="color: #000000; font-weight: bold;">import</span> <span style="color: #006699;">android.os.Bundle</span><span style="color: #339933;">;</span></span><br /><span style="vertical-align: top;"><span style="color: #000000; font-weight: bold;">import</span> <span style="color: #006699;">android.webkit.WebSettings</span><span style="color: #339933;">;</span></span><br /><span style="vertical-align: top;"><span style="color: #000000; font-weight: bold;">import</span> <span style="color: #006699;">android.webkit.WebView</span><span style="color: #339933;">;</span></span><br /><span style="vertical-align: top;"> </span><br /><span style="vertical-align: top;"><span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">class</span> charlesenmob <span style="color: #000000; font-weight: bold;">extends</span> Activity <span style="color: #009900;">{</span></span><br /><span style="vertical-align: top;">    <span style="color: #008000; font-style: italic; font-weight: bold;">/** Called when the activity is first created. */</span></span><br /><span style="vertical-align: top;">    @Override</span><br /><span style="vertical-align: top;">    <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000066; font-weight: bold;">void</span> onCreate<span style="color: #009900;">(</span>Bundle savedInstanceState<span style="color: #009900;">)</span> <span style="color: #009900;">{</span></span><br /><span style="vertical-align: top;">        <span style="color: #000000; font-weight: bold;">super</span>.<span style="color: #006633;">onCreate</span><span style="color: #009900;">(</span>savedInstanceState<span style="color: #009900;">)</span><span style="color: #339933;">;</span></span><br /><span style="vertical-align: top;">        setContentView<span style="color: #009900;">(</span>R.<span style="color: #006633;">layout</span>.<span style="color: #006633;">main</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span></span><br /><span style="vertical-align: top;"> </span><br /><span style="vertical-align: top;">        <span style="color: #666666; font-style: italic;">// Instanciation du WebView...</span></span><br /><span style="vertical-align: top;">        WebView wvSite <span style="color: #339933;">=</span> <span style="color: #009900;">(</span>WebView<span style="color: #009900;">)</span>findViewById<span style="color: #009900;">(</span>R.<span style="color: #006633;">id</span>.<span style="color: #006633;">webview</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span></span><br /><span style="vertical-align: top;"> </span><br /><span style="vertical-align: top;">        <span style="color: #666666; font-style: italic;">//...on active JavaScript...</span></span><br /><span style="vertical-align: top;">        WebSettings webSettings <span style="color: #339933;">=</span> wvSite.<span style="color: #006633;">getSettings</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span></span><br /><span style="vertical-align: top;">        webSettings.<span style="color: #006633;">setJavaScriptEnabled</span><span style="color: #009900;">(</span><span style="color: #000066; font-weight: bold;">true</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span></span><br /><span style="vertical-align: top;"> </span><br /><span style="vertical-align: top;">        <span style="color: #666666; font-style: italic;">//...et on charge la page</span></span><br /><span style="vertical-align: top;">        wvSite.<span style="color: #006633;">loadUrl</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"http://m.charlesen.fr"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span></span><br /><span style="vertical-align: top;">    <span style="color: #009900;">}</span></span><br /><span style="vertical-align: top;"><span style="color: #009900;">}</span></span></pre>
    </td>
  </tr>
</table>

 

<table class="xml" style="border-collapse: collapse; width: 100%;">
  <tr>
    <td style="background: none repeat scroll 0% 0% #dddddd; color: #054b6e; padding: 2px 0px; text-align: center; font: italic bold 12px Verdana,Geneva,Arial,Helvetica,sans-serif;" colspan="2">
      main.xml
    </td>
  </tr>
  
  <tr class="li1">
    <td style="width: 1px; background: none repeat scroll 0% 0% #f0f0f0; vertical-align: top; color: #676f73; border-right: 1px dotted #dddddd; font-size: 12px; text-align: right;">
      <pre style="margin: 0pt; background: none repeat scroll 0% 0% transparent; vertical-align: top; padding: 0px 4px; font-size: 12px;">1<br />2<br />3<br />4<br />5<br />6<br />7<br />8<br />9</pre>
    </td>
    
    <td style="margin: 0pt; background: none repeat scroll 0% 0% transparent; vertical-align: top; padding: 0px 4px; font-size: 12px;">
      <pre style="margin: 0pt; background: none repeat scroll 0% 0% transparent; vertical-align: top; padding: 0px 4px; font-size: 12px;"><span style="vertical-align: top;"><span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;?xml</span> <span style="color: #000066;">version</span>=<span style="color: #ff0000;">"1.0"</span> <span style="color: #000066;">encoding</span>=<span style="color: #ff0000;">"utf-8"</span><span style="color: #000000; font-weight: bold;">?&gt;</span></span></span><br /><span style="vertical-align: top;"><span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;LinearLayout</span> <span style="color: #000066;">xmlns:android</span>=<span style="color: #ff0000;">"http://schemas.android.com/apk/res/android"</span></span></span><br /><span style="vertical-align: top;"><span style="color: #009900;">	<span style="color: #000066;">android:orientation</span>=<span style="color: #ff0000;">"vertical"</span> <span style="color: #000066;">android:layout_width</span>=<span style="color: #ff0000;">"fill_parent"</span></span></span><br /><span style="vertical-align: top;"><span style="color: #009900;">	<span style="color: #000066;">android:layout_height</span>=<span style="color: #ff0000;">"fill_parent"</span><span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br /><span style="vertical-align: top;">	<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;WebView</span> <span style="color: #000066;">xmlns:android</span>=<span style="color: #ff0000;">"http://schemas.android.com/apk/res/android"</span></span></span><br /><span style="vertical-align: top;"><span style="color: #009900;">		<span style="color: #000066;">android:id</span>=<span style="color: #ff0000;">"@+id/webview"</span> <span style="color: #000066;">android:layout_width</span>=<span style="color: #ff0000;">"fill_parent"</span></span></span><br /><span style="vertical-align: top;"><span style="color: #009900;">		<span style="color: #000066;">android:layout_height</span>=<span style="color: #ff0000;">"wrap_content"</span> <span style="color: #000000; font-weight: bold;">/&gt;</span></span></span><br /><span style="vertical-align: top;"><span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/LinearLayout<span style="color: #000000; font-weight: bold;">&gt;</span></span></span></span><br /><span style="vertical-align: top;"> </span></pre>
    </td>
  </tr>
</table>

 

<table class="xml" style="border-collapse: collapse; width: 100%;">
  <tr>
    <td style="background: none repeat scroll 0% 0% #dddddd; color: #054b6e; padding: 2px 0px; text-align: center; font: italic bold 12px Verdana,Geneva,Arial,Helvetica,sans-serif;" colspan="2">
      strings.xml
    </td>
  </tr>
  
  <tr class="li1">
    <td style="width: 1px; background: none repeat scroll 0% 0% #f0f0f0; vertical-align: top; color: #676f73; border-right: 1px dotted #dddddd; font-size: 12px; text-align: right;">
      <pre style="margin: 0pt; background: none repeat scroll 0% 0% transparent; vertical-align: top; padding: 0px 4px; font-size: 12px;">1<br />2<br />3<br />4<br />5<br />6<br />7</pre>
    </td>
    
    <td style="margin: 0pt; background: none repeat scroll 0% 0% transparent; vertical-align: top; padding: 0px 4px; font-size: 12px;">
      <pre style="margin: 0pt; background: none repeat scroll 0% 0% transparent; vertical-align: top; padding: 0px 4px; font-size: 12px;"><span style="vertical-align: top;"><span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;?xml</span> <span style="color: #000066;">version</span>=<span style="color: #ff0000;">"1.0"</span> <span style="color: #000066;">encoding</span>=<span style="color: #ff0000;">"utf-8"</span><span style="color: #000000; font-weight: bold;">?&gt;</span></span></span><br /><span style="vertical-align: top;"><span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;resources<span style="color: #000000; font-weight: bold;">&gt;</span></span></span></span><br /><span style="vertical-align: top;">    <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;string</span> <span style="color: #000066;">name</span>=<span style="color: #ff0000;">"app_name"</span><span style="color: #000000; font-weight: bold;">&gt;</span></span>charlesen.fr<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/string<span style="color: #000000; font-weight: bold;">&gt;</span></span></span></span><br /><span style="vertical-align: top;">    <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;string</span> <span style="color: #000066;">name</span>=<span style="color: #ff0000;">"homepage"</span><span style="color: #000000; font-weight: bold;">&gt;</span></span>charlesen.fr - Version Mobile<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/string<span style="color: #000000; font-weight: bold;">&gt;</span></span></span></span><br /><span style="vertical-align: top;"><span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/resources<span style="color: #000000; font-weight: bold;">&gt;</span></span></span></span><br /><span style="vertical-align: top;"> </span></pre>
    </td>
  </tr>
</table>

 

<table class="xml" style="border-collapse: collapse; width: 100%;">
  <tr>
    <td style="background: #dddddd; color: #054b6e; padding: 2px 0px; text-align: center; font: bold italic 12px Verdana, Geneva, Arial, Helvetica, sans-serif;" colspan="2">
      Fichier manifest
    </td>
  </tr>
  
  <tr class="li1">
    <td style="width: 1px; background: #f0f0f0; vertical-align: top; color: #676f73; border-right: 1px dotted #dddddd; font-size: 12px; text-align: right;">
      <pre style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;">1<br />2<br />3<br />4<br />5<br />6<br />7<br />8<br />9<br />10<br />11<br />12<br />13<br />14<br />15</pre>
    </td>
    
    <td style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;">
      <pre style="margin: 0; background: none; vertical-align: top; padding: 0px 4px; font-size: 12px;"><span style="vertical-align: top;"><span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;?xml</span> <span style="color: #000066;">version</span>=<span style="color: #ff0000;">"1.0"</span> <span style="color: #000066;">encoding</span>=<span style="color: #ff0000;">"utf-8"</span><span style="color: #000000; font-weight: bold;">?&gt;</span></span></span><br /><span style="vertical-align: top;"><span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;manifest</span> <span style="color: #000066;">xmlns:android</span>=<span style="color: #ff0000;">"http://schemas.android.com/apk/res/android"</span></span></span><br /><span style="vertical-align: top;"><span style="color: #009900;">	<span style="color: #000066;">package</span>=<span style="color: #ff0000;">"fr.charlesen.projets"</span> <span style="color: #000066;">android:versionCode</span>=<span style="color: #ff0000;">"1"</span></span></span><br /><span style="vertical-align: top;"><span style="color: #009900;">	<span style="color: #000066;">android:versionName</span>=<span style="color: #ff0000;">"1.0"</span><span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br /><span style="vertical-align: top;">	<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;uses-permission</span> <span style="color: #000066;">android:name</span>=<span style="color: #ff0000;">"android.permission.INTERNET"</span> <span style="color: #000000; font-weight: bold;">/&gt;</span></span></span><br /><span style="vertical-align: top;">	<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;uses-sdk</span> <span style="color: #000066;">android:minSdkVersion</span>=<span style="color: #ff0000;">"9"</span> <span style="color: #000000; font-weight: bold;">/&gt;</span></span></span><br /><span style="vertical-align: top;">	<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;application</span> <span style="color: #000066;">android:icon</span>=<span style="color: #ff0000;">"@drawable/icon"</span> <span style="color: #000066;">android:label</span>=<span style="color: #ff0000;">"@string/app_name"</span><span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br /><span style="vertical-align: top;">		<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;activity</span> <span style="color: #000066;">android:name</span>=<span style="color: #ff0000;">".charlesenmob"</span> <span style="color: #000066;">android:label</span>=<span style="color: #ff0000;">"@string/homepage"</span><span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br /><span style="vertical-align: top;">			<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;intent-filter<span style="color: #000000; font-weight: bold;">&gt;</span></span></span></span><br /><span style="vertical-align: top;">				<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;action</span> <span style="color: #000066;">android:name</span>=<span style="color: #ff0000;">"android.intent.action.MAIN"</span> <span style="color: #000000; font-weight: bold;">/&gt;</span></span></span><br /><span style="vertical-align: top;">				<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;category</span> <span style="color: #000066;">android:name</span>=<span style="color: #ff0000;">"android.intent.category.LAUNCHER"</span> <span style="color: #000000; font-weight: bold;">/&gt;</span></span></span><br /><span style="vertical-align: top;">			<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/intent-filter<span style="color: #000000; font-weight: bold;">&gt;</span></span></span></span><br /><span style="vertical-align: top;">		<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/activity<span style="color: #000000; font-weight: bold;">&gt;</span></span></span></span><br /><span style="vertical-align: top;">	<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/application<span style="color: #000000; font-weight: bold;">&gt;</span></span></span></span><br /><span style="vertical-align: top;"><span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/manifest<span style="color: #000000; font-weight: bold;">&gt;</span></span></span></span></pre>
    </td>
  </tr>
</table>

 

<p style="text-align: center;">
  Ca donne ça avec l&rsquo;émulateur :
</p>

<p style="text-align: center;">
   
</p>

<img loading="lazy" class=" size-full wp-image-134" src="https://charlesen.fr/wp-content/uploads/2011/02/images_charlesenmob.png" border="0" alt="charlesen.fr Mobile" title="charlesen.fr Mobile" style="display: block; margin-left: auto; margin-right: auto;" width="500" height="439" srcset="https://charlesen.fr/wp-content/uploads/2011/02/images_charlesenmob.png 500w, https://charlesen.fr/wp-content/uploads/2011/02/images_charlesenmob-300x263.png 300w" sizes="(max-width: 500px) 100vw, 500px" /> 

<div id="_mcePaste" class="mcePaste" style="position: absolute; left: -10000px; top: 129px; width: 1px; height: 1px; overflow: hidden;">
  <pre class="prettyprint"><span class="typ">WebView</span><span class="pln"> myWebView </span><span class="pun">=</span><span class="pun">(</span><span class="typ">WebView</span><span class="pun">)</span><span class="pln"> findViewById</span><span class="pun">(</span><span class="pln">R</span><span class="pun">.</span><span class="pln">id</span><span class="pun">.</span><span class="pln">webview</span><span class="pun">);</span><span class="pln"><br />myWebView</span><span class="pun">.</span><span class="pln">loadUrl</span><span class="pun">(</span><span class="str">"http://www.example.com"</span><span class="pun">);</span></pre></p>
</div>