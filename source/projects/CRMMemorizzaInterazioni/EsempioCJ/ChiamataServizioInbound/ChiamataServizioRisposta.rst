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
| Chiamata servizio | Chiamata di servizio, risposta | dateYMDms ---> dateTime |
+                   +                                +-------------------------+
|                   |                                | idlastcall ---> callId  |
+-------------------+--------------------------------+-------------------------+

Esempio richiesta
=================

``http://democrm.teleniasoftware.com/service/answer?dateTime=2020-01-01T00%3A00%3A00.000Z&callId=1583932001.48%40d0834a2c15``