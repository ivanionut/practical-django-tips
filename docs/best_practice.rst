.. -*- coding: utf-8 -*-

.. _best_practice-index:

=============
Best Practice
=============

.. _best_practice-giants:

Salire sulle spalle dei giganti
===============================

Non reinventare la ruota!
-------------------------
* Passare una giornata a cercare e provare applicazioni esistenti alla
  caccia dell'applicazione già pronta, non è tempo perso, anche se voi
  avreste scritto la "stessa" applicazione in meno tempo.
  
* Il tempo risparmiato lo passerete a piangere sui vostri bug, che
  sicuramente ognuno di noi commette.
  
* Se, per qualche motivo, non potete utilizzare applicazioni già
  esistenti, allora, compatibilmente con la licenza, derivate la
  vostra applicazione a partire dal codice di applicazioni esistenti
  (`github`_ e `bitbucket`_, ma in generale `git`_ e `hg`_ facilitano
  molto questa pratica tramite il branching).

Leggere il codice di Django
---------------------------
* Il `codice scritto dagli sviluppatori Django
  <http://code.djangoproject.org>`_ è la massima espressione delle
  best practice di programmazione per applicazioni `Django`_.
  
* Leggetelo, sfogliatelo, traetene spunto, copiatene i pattern.

.. _best_practice-workflow:

Stabilire e seguire un workflow di lavoro
=========================================
* Ottimo esempio di workflow semplice dal `team Pocoo
  <http://www.pocoo.org/internal/release-management/>`_.

.. _best_practice-doc:

Scrievere buona documentazione (e subito!)
==========================================
* Documentare sempre il codice.
* Non procrastinare la scrittura della documentazione.
* Seguire lo `stile ufficiale
  <https://docs.djangoproject.com/en/1.3/internals/contributing/#documentation-style>`_

* Includere sempre un file README con almeno due righe che spieghino
  brevemente cosa fa un modulo o un'applicazione
* Usare `Sphinx <http://sphinx.pocoo.org/>`_ (produce PDF, LaTeX,
  HTML)

  * Fare riferimento al codice con `autodoc
    <http://sphinx.pocoo.org/tutorial.html#autodoc>`_

* Al limite, scrivere la documentazione *prima* di implementare il codice

  * se un progetto fallisce, costa molto meno cestinare la
    documentazione piuttosto che il costoso codice, anche se non
    documentato.

* `Buoni esempi di documentazione
  <http://sphinx.pocoo.org/examples.html#books-produced-using-sphinx>`_

.. _best_practice-test:

Scrivere i test
===============
* Usate almeno `pylint <http://pypi.python.org/pypi/pylint>`_ e/o `pyflakes <http://pypi.python.org/pypi/pyflakes>`_ per una
  verifica blanda della "qualità" del codice.
* Durante o addirittura *prima* di scrivere il codice.
* Sfruttare `doctest`_ per integrare test e documentazione.

.. seealso::
   :ref:`testing-index`

.. _best_practice-reusable:

Create applicazioni piccole e riusabili (principi)
==================================================

Ogni applicazione riusabile deve seguire i seguenti principi essenziali:

**Focused**

    Use case limitati; non includere nulla che non sia indispensabile.

    .. epigraph::
    
       ``Write programs that do one thing and do it well.''
       
       -- Doug McIlroy (inventor of UNIX pipes)

**Auto-contenuta**

    Tutti i requisiti per far funzionare l'applicazione sono inclusi o
    dichiarati.

**Adattabile**

    Non imporre troppe assunzioni (e.g., valori attesi in input,
    setting cablati), cercando così di rendere l'applicazione facile
    da personalizzare.

**Facilmente installabile**

    Se un'applicazione è difficile da installare si tenderà a non
    sfruttarla o a preferirne un'altra. È bene invece che per
    installare un'applicazione sia sufficiente quanto segue

    .. code-block:: bash

    (my-virtualenv) [user@host]$ pip install django-myapp

    Idealmente, l'applicazione è a questo punto già pronta all'uso, la
    procedura d'installazione fornisce istruzioni all'utente su come
    procedere.
    

.. _best_prctice-distribute:

Create applicazioni e distribuitele
===================================

.. seealso::
   :ref:`applicazioni_riusabili-index`

.. _best_practice-incremental-features:

Aggiungere piccole feature incrementalmente
===========================================
* Non aggiungere una feature ad una vostra applicazione se la feature
  non è di stretta pertinenza.

* Nel dubbio, create una nuova applicazione: è meglio avere due
  applicazioni piccole (e per questo più semplici da debuggare) con
  una feature ciascuna, piuttosto che una sola applicazione con una
  feature "fuori posto".

Applicazioni portabili
======================
* Usare feature di Django solo se non deprecate.
* Tenersi informati sulle prossime release di Django per sapere quali
  cambiamenti verranno introdotti.

Fixture (dati predefiniti)
==========================
* Non appena avete popolato le vostre applicazioni e vi sono dati a
  sufficienza per fare una demo, salvate i dati in una o più fixture.
* Separare le fixture per applicazione.
* Le fixture sono utilissime per i test.


Usare meccanismi di caching
===========================
* Imparare come funzionano i vari livelli di caching previsti da
  `Django`_ prima di mettervi alla rincorsa del mecchanismo di caching
  capace di a battere `memcached`_ e simili.
* Non mettere tutto in cache, usare la cache accuratamente.
* Pensare agli utenti autenticati e a quelli autenticati e progettare
  la politica di caching di conseguenza.


.. _best_practice-split-setting:

Separate i setting per compartimenti
====================================

.. code-block:: bash

   $ ls settings/

   __init__.py
   10-base.conf
   20-database.conf
   30-templates.conf
   40-cache.conf
   ...


.. code-block:: python

   # settings/__init__.py
   
   import os.path
   import glob

   conffiles = glob.glob(os.path.join(os.path.dirname(__file__), '*.conf'))
   conffiles.sort()
   for f in conffiles:
       execfile(os.path.abspath(f))


Setting di sviluppo e di deployment
-----------------------------------

.. code-block:: bash

   $ ls settings/

   __init__.py                   # aggiunto al repository
   10-base.conf
   11-base.machine.local.conf    # escluso dal repository (e.g., creato via
                                 # Fabric o a mano durante il deployment)
   30-templates.conf             # aggiunto al repository
   40-cache.conf                 # aggiunto al repository
   41-cache.machine.local.conf   # escluso dal repository
   ...
   70-registration.app.conf      # override dei setting per


* https://code.djangoproject.com/wiki/SplitSettings#UsingalistofconffilesTransifex


Seuire uno stile di codice consistente
======================================
* Seguire quanto più possibile la `Style Guide for Python Code (guida
  di stile per il codice Python)
  <http://www.python.org/dev/peps/pep-0008/>`_.
* Seguire quanto più possibile il `Coding Style
  <https://docs.djangoproject.com/en/dev/internals/contributing/writing-code/coding-style/>`_
  di Django, anche se non avete in programma di includere il vostro
  codice in Django.

.. _best_practice-approaches:

Seguire diversi approcci per diversi problemi
=============================================

Dati e database
---------------
* Database transazionali solo per dati manipolati in operazioni
  transazionali

  * solo per operazioni *davvero* transazionali
  * sono poche le porzioni davvero transazionali in un'applicazione
    web odierna


* Database non transazionali/relazionali (key-value store, document store) per
  dati storici (e.g., log)

  * la velocità è più importante della consistenza
  * dati fortemente denormalizzati, disponibili subito
  * `ottima comparazione <http://kkovacs.eu/cassandra-vs-mongodb-vs-couchdb-vs-redis>`_

Funzioni
--------
* Task inerentemente sincroni

  * implementateli solo se di durata breve e nota
  * non devono "rompere" il ciclo "request-response"

* Task asincroni
  
  * da usarsi per operazioni di durata imprecisata

