.. -*- coding: utf-8 -*-

.. _front_end-index:

================================================================
Presentazione dei dati (per chi non può permettersi un designer)
================================================================
Gli argomenti affrontati in questa sezione prescindono da Django. Tuttavia, le risorse citate seguono la stessa filosofia di DRY Django e sono sono scritte, utilizzate o promosse da chi utilizza Django professionalmente.

Aspetti essenziali
==================
I seguenti sono aspetti dai quali non si può prescindere quando si pubblica una pagina web professionale.

Cross-compatibilità
-------------------
Anche se gli standard web sono, per l'appunto, standard, non tutti i browser li seguono e li implementano al 100%. Per avere una dimostrazione pratica, provate a fare `questo test <http://www.webstandards.org/files/acid2/test.html>`_ con diversi browser di diverse versioni. Esistono `browser più standard e, per altro, più sicuri di altri <http://browsehappy.com/>`_.

L'approccio che seguo normalmente è il seguente:

**Utilizzare l'ultima versione di browser (preferibilmente open source)**
    Ad esempio, io utilizzo `Google Chrome <http://google.com/chrome/>`_ perché è essenziale, sicuro e ha una console integrata che mi permette di fare live debugging di HTML, CSS e JavaScript.

**Impiegare librerie di astrazione per la cross-compatibilità**
    Ad esempio, io utilizzo `Modernizr`_
 
**Ignorare altri browser o versioni precedenti**
    specialmente se non più ufficialmente supportate: prima è bene avere una pagina ben costruita renderizzata correttamente su un browser di riferimento. In futuro potrete investire tempo a correggere gli errori di visualizzazione utilizzando servizi come `Browsershots <http://browsershots.org/>`_, che permettono di visualizzare la stessa pagina su vari sistemi operativi, browser, dimensioni di schermo.


La jungla dei framework
=======================
Esistono tantissimi framework sia per lo stile, CSS, sia per quello che io amo chiamare comportamento o "behavior" di una pagina. Oggi è molto difficile scegliere. Una query a Google per `best css framewokrs 2011` ritorna oltre 14,000,000 di risultati di cui il primo è un articolo su un blog che promette di discuterene "solo" 20. Per chi non è un designer di mestiere è difficile trovare il tempo di comparare 20 framework. Ancora più dura è trovare il coraggio di imbarcarsi in una strada che non si sa se sarà quella giusta.

Lungi da me vendere i seguenti come i migliori. Sono semplicemente quelli con cui lavoro ogni giorno e con i quali mi trovo bene. I criteri di scelta sono:

+ semplicità: quanto tempo mi ci vuole per imparare ad usarlo?
+ documentazione: c'è buona documentazione ricca di esempi?
+ comunità: esiste una comunità attiva che potrà darmi supporto in caso di errori o difficoltà iniziali?
+ integrazione con Django: esistono applicazioni Django che aiutano ad integrare i file statici necessari e che ne supportano il rilascio?
+ CDN: le librerie sono rilasciate su una CDN che mi permette di non preoccuparmi del deployment (la CDN più completa ad oggi è `Google Libraries API`_)?

Framework HTML consigliati
--------------------------
Come detto sopra, non sono necessarimente i migliori.

+ `HTML5 Boilerplate`_: essenziale, anche per creare una sola pagina statica.

Framework CSS consigliati
-------------------------
Come detto sopra, non sono necessarimente i migliori.

`Less`_
  Framework minimalistico ma decisamente flessibile, utile per la funzionalità che permette l'adattamento in maniera trasparente alle diverse dimensioni di schermo (e.g., portatile, palmare, tablet).
  
`Blueprint CSS`_
  Utile come primo framework e per progetti di media entità.

`compass`_
  Utile per superare i limiti della sintassi CSS (e.g., aggiungendo dichiarazioni di variabili, funzioni). Integrabile in Django via `django-compass`_.

`Susy`_
  Utile estensione di `compass`_ per la creazione e gestione di griglie.

Framework JavaScript consigliati
--------------------------------
Come detto sopra, non sono necessarimente i migliori. Da un certo punto di vista, questa lista è ordinata dalla libreria più "leggera" a quella più omnicomprensiva.

`mootools`_
  Libreria di astrazione ed effetti grafici.
  
`Prototype JS`_ + `script.aculo.us`_
  Libreria di astrazione + effetti grafici.

`jQuery`_ + `jQuery UI`_
  Libreria di astrazione + widget ed effetti grafici.


Django, aiutami tu!
-------------------
Django non mette a disposizione nulla che guidi il designer nella scrittura dei template, nemmeno delle linee guida. L'unica funzionalità pensata per un web designer si limita a `django.contrib.webdesign <https://docs.djangoproject.com/en/dev/ref/contrib/webdesign/>`_ che offre il solo tempate tag `{% lorem %}` utile a generare testo dummy riempitivo.

Fortunatamente esistono applicazioni utili:

+ django-richtemplates
+ django-uni-forms
+ django-template-utils

Riferimenti
===========

+ `Best Practices for Front-End Django Developers
  <http://www.slideshare.net/cosecant/best-practices-for-frontend-django-developers>`_

+ `web-developer's handbook`_

+ `Google Web Fonts <http://www.google.com/webfonts#ChoosePlace:select>`_

+ `Lista di librerie e framwework per il web <http://www.w3avenue.com/topics/libraries-frameworks/>`_

+ `Font squirrel`_

+ `Advanced Django Form Usage
  <http://www.slideshare.net/pydanny/advanced-django-forms-usage>`_
  (`Video della presentazione
  <http://blip.tv/djangocon/advanced-django-form-usage-5573287>`_ a
  `DjangoCon.us 2011 <http://djangocon.us/>`_)

+ `Microformats <http://microformats.org/>`_

+ `Separation: The Web Designer's Dilemma
  <http://www.alistapart.com/articles/separationdilemma/>`_


.. _Modernizr: http://www.modernizr.com/
.. _jQuery: http://jquery.com/
.. _jQuery UI: http://jqueryui.com/
.. _Prototype JS: http://prototypejs.org/
.. _script.aculo.us: http://script.aculo.us/
.. _mootools: http://mootools.net/
.. _Google Libraries API: http://code.google.com/apis/libraries/devguide.html#Libraries
.. _Less: http://lessframework.com/
.. _HTML5 Boilerplate: http://html5boilerplate.com/
.. _Blueprint CSS: http://blueprintcss.org/
.. _compass: http://compass-style.org/
.. _Susy: http://susy.oddbird.net/
.. _django-compass: https://bitbucket.org/zacharyvoase/django-compass
.. _web-developer's handbook: http://alvit.de/handbook/
.. _Font squirrel: http://www.fontsquirrel.com/
