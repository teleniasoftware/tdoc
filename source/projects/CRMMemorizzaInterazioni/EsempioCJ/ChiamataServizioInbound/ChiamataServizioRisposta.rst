.. _ChiamataServizioInbound_Risposta:

==============================
Chiamata di servizio, risposta
==============================

:Nome:
    Chiamata di servizio inbound - Risposta
:Tipo:
    ``GET``
:URI: http://democrm.teleniasoftware.com/service/answer.php
:Eventi:

+-------------------+--------------------------------+-------------------------+
| Tipo              | Evento                         | Variabili               |
+===================+================================+=========================+
| Chiamata servizio | Chiamata di servizio, risposta | dateISO ---> dateTime   |
+                   +                                +-------------------------+
|                   |                                | idlastcall ---> callId  |
+                   +                                +-------------------------+
|                   |                                | cli ---> callerNumber   |
+-------------------+--------------------------------+-------------------------+

Esempio richiesta
=================
.. code-block::

    http://democrm.teleniasoftware.com/service/answer?dateTime=2020-11-20T10%3A24%3A46.959Z&callId=1605867847.783%40d92061befe&callerNumber=0987654321