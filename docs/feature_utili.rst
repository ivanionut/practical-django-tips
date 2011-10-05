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

.. seealso:: https://docs.djangoproject.com/en/1.3/ref/django-admin/#cleanup

``diffsettings``
~~~~~~~~~~~~~~~~

.. code-block:: python
                
   django-admin.py diffsettings

.. seealso:: https://docs.djangoproject.com/en/1.3/ref/django-admin/#diffsettings

``shell`` (con `IPython`_ installato!)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: python
                
   django-admin.py shell

Utile per scrivere i `doctest`_ specialmente usando `IPython`_.

.. seealso:: https://docs.djangoproject.com/en/1.3/ref/django-admin/#shell

.. seealso::
   ``shell_plus`` di `django-extensions`_

``sqlcustom``
~~~~~~~~~~~~~

.. code-block:: python

    django-admin.py sqlcustom

Utile per scoprire se ci sono parti di codice SQL custom dimenticate
(dovreste minimizzare l'uso di codice non portabile).

.. seealso:: https://docs.djangoproject.com/en/1.3/ref/django-admin/#sqlcustom-appname-appname

``test``
~~~~~~~~

.. code-block:: python

    django-admin.py test

.. seealso:: https://docs.djangoproject.com/en/1.3/ref/django-admin/#test-app-or-test-identifier


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

* AUTHENTICATION_BACKENDS
* AUTH_PROFILE_MODULE
* CACHES
* CSRF_*
* DATABASE_ROUTERS
* EMAIL_BACKEND
* FILE_UPLOAD_PERMISSIONS
* INTERNAL_IPS
* LOGGING
* SEND_BROKEN_LINK_EMAILS
* TEMPLATE_LOADERS


.. seealso:: https://docs.djangoproject.com/en/1.3/ref/settings/

.. seealso:: :ref:`best_practice-split-setting`


Manager
=======

https://docs.djangoproject.com/en/1.3/topics/db/managers/

Context Processor
=================

https://docs.djangoproject.com/en/1.3/ref/templates/api/#subclassing-context-requestcontext

Database Multipli
=================

https://docs.djangoproject.com/en/1.3/topics/db/multi-db/

Class-based View
================

https://docs.djangoproject.com/en/1.3/topics/class-based-views/

https://docs.djangoproject.com/en/1.3/ref/class-based-views/

Template Tag
============

https://docs.djangoproject.com/en/1.3/ref/templates/builtins/


Local Flavor
============

https://docs.djangoproject.com/en/1.3/ref/contrib/localflavor/

I18N L10N
=========

https://docs.djangoproject.com/en/1.3/topics/i18n/

Model Validator
===============

https://docs.djangoproject.com/en/1.3/ref/validators/

.. include:: epilogue.rst
