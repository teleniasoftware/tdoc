.. _ChiamataOutbound_Nuova:

==============
Nuova chiamata
==============

:Nome:
    Chiamata outbound - Nuova
:Canale:
    ``Telefonico``
:Tipo:
    ``GET``
:URI: http://democrm.teleniasoftware.com/outbound/new.php
:Eventi:

+-------------------+------------------+-------------------------+
| Tipo              | Evento           | Variabili               |
+===================+==================+=========================+
| Chiamata outbound | Nuova chiamata   | dateISO ---> dateTime   |
+                   +                  +-------------------------+
|                   |                  | id ---> callId          |
+                   +                  +-------------------------+
|                   |                  | dnis ---> calledNumber  |
+                   +                  +-------------------------+
|                   |                  | userclid ---> agent     |
+-------------------+------------------+-------------------------+

Esempio richiesta
=================

.. code-block:: sh

    http://democrm.teleniasoftware.com/outbound/new?dateTime=2020-11-20T10%3A29%3A31.207Z&callId=1605868170.789%40d92061befe&calledNumber=0987654321&agent=op1