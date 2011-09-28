.. -*- coding: utf-8 -*-

.. _applicazioni_riusabili-index:

================================
Applicazioni riusabili in Django
================================

TODO

* Usare setting dedicati per ogni applicazione con valori di default
  appropriati e che richiedano poco o nessuno sforzo all'utente dopo
  l'installazione.

  .. seealso:: http://djangopatterns.com

  .. seealso:: https://github.com/glamkit

.. _applicazioni-app_based_settings:

Setting, file statici, template: un progetto senza il progetto
==============================================================

Un progetto `Django`_, così come creato dal comando
:command:`startproject`, ha la seguente struttura:

.. code-block:: bash

   $ django-admin.py startproject sampleproject
   $ tree sampleproject
   sampleproject
   ├── __init__.py
   ├── manage.py
   ├── settings.py
   └── urls.py

Di fatto, un progetto `Django`_ non ha bisogno di una directory in cui
vivere. Servono soltanto due moduli `Python`_ all'interno del
``sys.path``:

.. code-block:: python

   sampleproject.settings
   sampleproject.urls

E non serve altro! Il file ``manage.py`` è, di fatto, un rimpiazzo di
``django-admin.py`` con, in più, l'impostazione della variabile
d'ambiente:

.. code-block:: python

   os.environ[DJANGO_SETTINGS_MODULE] = 'sampleproject.settings'

Di fatto, nemmeno questo è necessario. È sufficiente infatti usare
l'opzione ``--settings`` per specificare il modulo dei setting
dinamicamente:

.. code-block:: bash

   $ django-admin.py [comando] --settings 'sampleproject.settings'

D'altra parte uno ha bisogno di altri ingredienti:

**Applicazioni specifiche**

  Pensateci più volte e ponetevi le solite domande. Ad esempio: non
  esiste un'applicazione che fa quello che mi serve? Se è da
  modificare ed è open source sarà sicuramente meglio che crearne una
  da zero.

  Se proprio dovete includere un'applicazione specifica del vostro
  progetto, sorge il problema di dove piazzare queste applicazioni.

**Template**

  Normalmente le buone applicazioni hanno già un set di template a
  corredo. Quindi, per esempio, se utilizzate `django-registration`_
  avrete:

  .. code-block:: bash

     $ tree django-registration/registration
     django-registration/registration
     ├── __init__.py
     ├── [...]
     ├── models.py
     ├── templates
     │   └── registration
     │       ├── base.html
     │       ├── [...]
     │       └── [...]
     └── urls.py

  Se non sono adatte al vostro progetto dovrete estenderle. Sorge
  quindi il problema di dove posizionzare questi template.

**File statici**

  Normalmente, i file statici di ogni buona applicazione che usate nel
  vostro progetto vivono nell'applicazione stessa. Quindi, come per i
  template, avrete una directory :file:`static/` o :file:`media/` (a
  seconda della versione di `Django`_ che usate). Attenzione, qui non
  stiamo parlando dei file eventualmente caricati a runtime quali, ad
  esempio, le foto del profilo di un utente che si è registrato---che
  solitamente vivono in una directory separata :file:`upload/`
  servita).

  D'altra parte avrete sicuramente bisogno di file statici dedicati,
  come ad esempio i fogli di stile, le immagini e il codice JavaScript
  che costituiscono il frontend del vostro sito (vedere anche
  :ref:`front_end-index`).

  Sorge quindi il problema di dove posizionzare questi file statici.

Questi tre problemi troverebbero una soluzione nella creazione di un
progetto usando :command:`startproject`. Suggerisco di non farlo per
evitare ancora di cascare di nuovo nel modo di pensare "a progetto",
che rende facile pensare a path assoluti.

La soluzione che propongo prevede di utilizzare un'applicazione che
abbia il seguente scheletro:

.. code-block:: bash

   $ tree django-mysite
   ├── AUTHORS
   ├── CHANGELOG
   ├── LICENSE
   ├── MANIFEST.in
   ├── README
   ├── mysite
   │   ├── __init__.py
   │   ├── admin.py    # probabilmente vuoto
   │   ├── models.py   # probabilmente vuoto
   │   ├── settings/   # setting
   │   ├── static/     # file statici
   │   ├── template/   # template
   │   └── wsgi/       # eventuali server WSGI
   └── setup.py        # script d'installazione


* Usando uno scheletro ``django-site-skel`` il lavoro sarà più
  facilmente ripetibile.

.. _applicazioni-skel:

Creare e aggiornare uno "scheletro" per applicazioni Django
===========================================================

* ``django-app-skel``
* Usare `versiontools
  <http://packages.python.org/versiontools/usage.html#adding-support-for-your-project>`_

TODO
