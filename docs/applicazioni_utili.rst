.. -*- coding: utf-8 -*-

.. _applicazioni_utili-index:

===========================
Lista di applicazioni utili
===========================

Questa sezione non vuole sostituire le utilissime liste "community
driven" (si veda :ref:`applicazioni_utili-lists`) di applicazioni
`Django`_. Le applicazioni ed i pacchetti qui menzionati sono scelti
secondo la mia esperienza a la lista è senz'altro breve rispetto alla
montagna di applicazioni esistenti.


Database
========
* South

.. seealso:: `database-migration
   <http://djangopackages.com/grids/g/database-migration/>`_ su `Django
     Packages`_


Sviluppo
========
* django-devserver
* django-debug-toolbar
* django-extensions
  
.. seealso:: `developer-tools
   <http://djangopackages.com/grids/g/developer-tools/>`_ su `Django
     Packages`_


Debugging
=========
* django-debug-toolbar
* django-debug-logging
* django-sentry
* django-extensions


Templating
==========
* django-uni-form
* django-templatetag-sugar
* django-template-utils
* django-paging
* django-floppyform
* django-form-utils
* django-richtemplates


Assets
======
* django-filebrowser

  .. seealso:: `asset-managers
     <http://djangopackages.com/grids/g/asset-managers/>`_ su `Django
     Packages`_

Caching
=======
* django-varnish
* django-memcached (statistiche di utilizzo di `memcached`_)
* django-tyrant-cache

.. seealso:: `caching <http://djangopackages.com/grids/g/caching/>`_
   su `Django Packages`_


Admin
=====
* django-grappelli
* diango-nexus

.. seealso:: `admin-interface
   <http://djangopackages.com/grids/g/admin-interface/>`_ su `Django
   Packages`_


Translation
===========
* django-rosetta


Users
=====
* django-registration
* django-profiles

.. seealso:: `profiles
   <http://djangopackages.com/grids/g/profiles/>`_ su `Django
   Packages`_

Deployment
==========
* django-gargoyle
* django-mediasync

.. seealso:: `deployment
   <http://djangopackages.com/grids/g/deployment/>`_ su `Django
   Packages`_

Miscellanea
===========
* django-celery
* django-taggit
* django-chunks

.. _applicazioni_utili-lists:
  
Liste di applicazioni e pacchetti
=================================
In ordine di importanza, vale la pena di guardare:

`Django Packages <http://djangopackages.com/grids/>`_

  Lista "community driven" che calcola automaticamente la bontà dei
  paccketti in base a metriche oggettive (e.g., "quante volte è stata
  scaricata da `github`_?", "quante volte è stata scaricata da
  `PyPi`_?"). Tra parentesi i creatori hanno rilasciato anche un
  framework, `opencomparison
  <https://github.com/opencomparison/opencomparison>`_, per creare
  siti comparativi con la stessa impronta.

Una `ricerca su github
<https://github.com/search?type=Repositories&q=%22django-%22>`_

  Va preso con la giusta dose di sale in zucca, perché si tratta di
  codice non sempre rilasciato ufficialmente.

Una `ricerca su bitbucket
<https://bitbucket.org/repo/all/followers?name=django->`_

  Idem come per `github`_.

Una `ricerca su PyPi
<http://pypi.python.org/pypi?%3Aaction=search&term=django-&submit=search>`_

  Idem. Con la differenza che su `PyPi` troverete codice che, sebbene
  open source, l'autore ha deciso di rilasciare "ufficialmente".
