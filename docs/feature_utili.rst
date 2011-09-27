.. -*- coding: utf-8 -*-

==========================================
Feature native utili (a volte dimenticate)
==========================================

Comandi poco conosciuti di ``django-admin.py``
==============================================

Premessa
--------

``django-admin.py`` è meglio di ``python manage.py`` perché aiuta a
dimenticarsi il concetto di "progetto". Infatti ``django-admin.py``
vive nel ``$PATH`` della nostra shell, non nella cartella di progetto.

Comandi utili
-------------

``startproject`` (dimenticatevelo!)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: python

   django-admin.py startproject


.. caution::

   Non usare ``startproject`` se non durante il `Django tutorial`_.

``cleanup``
~~~~~~~~~~~

.. code-block:: python

   django-admin.py cleanup

``diffsettings``
~~~~~~~~~~~~~~~~

.. code-block:: python
                
   django-admin.py diffsettings

``shell`` (con `IPython`_ installato!)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: python
                
   django-admin.py shell

Utile per scrivere i `doctest`_!

.. seealso::
   ``shell_plus`` di `django-extensions`_

``sqlcustom``
~~~~~~~~~~~~~

.. code-block:: python

    django-admin.py sqlcustom

Utile per scoprire se ci sono parti di codice SQL custom dimenticate
(dovreste minimizzare l'uso di codice non portabile).

``test``
~~~~~~~~

.. code-block:: python

    django-admin.py test


Setting
=======

Setting deprecati
-----------------

Controllare sempre la lista dei setting deprecati e adeguate le vostre
applicazioni di conseguenza:

* `Setting deprecati in Django 1.1
  <https://docs.djangoproject.com/en/1.1/ref/settings/#deprecated-settings>`_
* `Setting deprecati in Django 1.2
  <https://docs.djangoproject.com/en/1.2/ref/settings/#deprecated-settings>`_
* `Setting deprecati in Django 1.3
  <https://docs.djangoproject.com/en/1.3/ref/settings/#deprecated-settings>`_


Setting utili
-------------



.. seealso:: :ref:`best_practice-split-setting`

Manager
=======

Context Processor
=================

Database Multipli
=================
https://docs.djangoproject.com/en/1.3/topics/db/multi-db/

Class-based View
================

Template Tag
============