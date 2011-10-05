.. -*- coding: utf-8 -*-

.. _testing-index:

===================
Testing e Debugging
===================

Fare debugging senza fare testing è sbagliato, significherebbe cercare
di risolvere un errore senza sapere esattamente se l'errore c'è o se è
causato da codice nostro.

Testing
=======

* Fare testing di applicazioni web è difficile, questo è innegabile.
* È bene cercare di sfruttare ciò che `Django`_ e `Python`_ mettono a
  disposizione.
* Cominciate dai `doctest`_: sono facili da inserire e aiutano a
  documentare mentre si scrive un test.

Cosa evitare
------------
* Anche se la deadline è vicina, evitare di procrastinate la scrittura dei
  test dicendo "lo farò più tardi". Ve ne pentirete!
* Ove possibile, misurare la copertura del codice "esercitato" dai vostri test

  ..seealso::
    http://ericholscher.com/blog/2009/nov/13/django-testing-code-coverage/

Riferimenti
===========
* http://pycheesecake.org/wiki/PythonTestingToolsTaxonomy
* `Advanced Django`_
* `doctest`_
* `unittest`_
* `fixtures`_
* `Django Test Client <https://docs.djangoproject.com/en/1.3/topics/testing/#module-django.test.client>`_
* `Email Capture <https://docs.djangoproject.com/en/1.3/topics/testing/#django.core.mail.django.core.mail.outbox>`_

.. include:: epilogue.rst
