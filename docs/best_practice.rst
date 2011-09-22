.. -*- coding: utf-8 -*-

=============
Best Practice
=============

Salire sulle spalle dei giganti
===============================

Non reinventare la ruota!
-------------------------
+ Passare una giornata a cercare e provare applicazioni esistenti alla
  caccia dell'applicazione già pronta, non è tempo perso, anche se voi
  avreste scritto la "stessa" applicazione in meno tempo.
  
+ Il tempo risparmiato lo passerete a piangere sui vostri bug, che
  sicuramente ognuno di noi commette.
  
+ Se, per qualche motivo, non potete utilizzare applicazioni già
  esistenti, allora, compatibilmente con la licenza, derivate la
  vostra applicazione da applicazioni esistenti.

Leggere il codice di Django
---------------------------
+ Il codice scritto dagli sviluppatori Django è la massima espressione
  delle best practice di programmazione.
  
+ Leggetelo, sfogliatelo, traetene spunto, copiatene i pattern.


Scrievere buona documentazione (e subito!)
==========================================

+ Documentare sempre il codice
  
+ Seguire lo `stile ufficiale <https://docs.djangoproject.com/en/1.3/internals/contributing/#documentation-style>`_

+ Includere sempre un ``README.rst`` con almeno due righe che
  spieghino brevemente cosa fa un modulo o un'applicazione

+ Usare `Sphinx <http://sphinx.pocoo.org/>`_ (produce PDF, LaTeX, HTML)

  + Fare riferimento al codice con `autodoc
    <http://sphinx.pocoo.org/tutorial.html#autodoc>`_

+ Al limite, scrivere la documentazione *prima* di implementare il codice

  + se un progetto fallisce, costa molto meno cestinare la
    documentazione piuttosto che il costoso codice, anche se non
    documentato

+ `Buoni esempi di documentazione
  <http://sphinx.pocoo.org/examples.html#books-produced-using-sphinx>`_

Diversi approcci per diversi problemi
=====================================
+ Database transazionali solo per dati manipolati in operazioni
  transazionali

  - solo per operazioni *davvero* transazionali
  - sono poche le porzioni davvero transazionali in un'applicazione web odierna

+ Database non transazionali (key-value store, document store) per
  dati storici (e.g., log)

  - la velocità è più importante della consistenza
  - dati fortemente denormalizzati, disponibili subito

+ Task sincroni

  - solo se brevi
  - non devono "rompere" il ciclo "request-response"

+ Task asincroni
  - da usarsi per operazioni di durata imprecisata


Applicazioni piccole e riusabili
================================
Filosofia Unix.

Aggiungere piccole feature incrementalmente
-------------------------------------------

Fixture (dati predefiniti)
==========================

Strutturare i template
======================

Coding style
============

+ Seguire quanto più possibile la `Style Guide for Python Code (guida
  di stile per il codice Python)
  <http://www.python.org/dev/peps/pep-0008/>`__.
  
+ Seguire quanto più possibile il `Coding Style
  <https://docs.djangoproject.com/en/dev/internals/contributing/writing-code/coding-style/>`__
  di Django, anche se non avete in programma di includere il vostro
  codice in Django.
