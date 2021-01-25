.. _ChiamataServizioInbound_Ring:

================
Chiamata in ring
================

:Nome:
    Chiamata di servizio inbound - Ring
:Tipo:
    ``GET``
:URI: http://democrm.teleniasoftware.com/service/ring.php
:Eventi:

+-------------------+------------------+-------------------------+
| Tipo              | Evento           | Variabili               |
+===================+==================+=========================+
| Chiamata servizio | Chiamata in ring | dateISO ---> dateTime   |
+                   +                  +-------------------------+
|                   |                  | idlastcall ---> callId  |
+                   +                  +-------------------------+
|                   |                  | pin ---> agent          |
+                   +                  +-------------------------+
|                   |                  | servizio ---> service   |
+                   +                  +-------------------------+
|                   |                  | cli ---> callerNumber   |
+-------------------+------------------+-------------------------+

Esempio richiesta
=================

.. code-block:: sh

    http://democrm.teleniasoftware.com/service/new?dateTime=2020-11-20T10%3A24%3A08.674Z&callId=1605867847.783%40d92061befe&agent=op1&service=customercare&callerNumber=0987654321