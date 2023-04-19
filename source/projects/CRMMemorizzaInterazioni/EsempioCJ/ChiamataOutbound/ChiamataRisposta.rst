.. _ChiamataOutbound_Risposta:

=================
Chiamata risposta
=================

:Nome:
    Chiamata outbound - Risposta
:Canale:
    ``Telefonico``
:Tipo:
    ``GET``
:URI: http://democrm.teleniasoftware.com/outbound/answer.php
:Eventi:

+-------------------+-------------------+-------------------------+
| Tipo              | Evento            | Variabili               |
+===================+===================+=========================+
| Chiamata outbound | Chiamata risposta | dateISO ---> dateTime   |
+                   +                   +-------------------------+
|                   |                   | id ---> callId          |
+                   +                   +-------------------------+
|                   |                   | dnis ---> calledNumber  |
+-------------------+-------------------+-------------------------+

Esempio richiesta
=================
.. code-block:: sh

    http://democrm.teleniasoftware.com/outbound/answer?dateTime=2020-11-20T10%3A29%3A47.324Z&callId=1583932001.48%40d0834a2c15&calledNumber=0987654321