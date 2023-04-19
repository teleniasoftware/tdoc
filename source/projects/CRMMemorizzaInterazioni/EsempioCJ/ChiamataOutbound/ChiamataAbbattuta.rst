.. _ChiamataOutbound_Abbattuta:

==================
Chiamata abbattuta
==================

:Nome:
    Chiamata outbound - Abbattuta
:Canale:
    ``Telefonico``
:Tipo:
    ``GET``
:URI: http://democrm.teleniasoftware.com/outbound/hangup.php
:Eventi:

+-------------------+--------------------+-------------------------+
| Tipo              | Evento             | Variabili               |
+===================+====================+=========================+
| Chiamata outbound | Chiamata abbattuta | dateISO ---> dateTime   |
+                   +                    +-------------------------+
|                   |                    | id ---> callId          |
+                   +                    +-------------------------+
|                   |                    | dnis ---> calledNumber  |
+-------------------+--------------------+-------------------------+

Esempio richiesta
=================

.. code-block:: sh

    http://democrm.teleniasoftware.com/outbound/hangup?dateTime=2020-11-20T10%3A30%3A06.985Z&callId=1583932001.48%40d0834a2c15&calledNumber=0987654321