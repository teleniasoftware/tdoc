===============================
Chiamata di servizio, abbattuta
===============================

:Nome:
    Chiamata di servizio inbound - Abbattuta
:Tipo:
    ``GET``
:URI: http://democrm.teleniasoftware.com/service/hangup.php
:Eventi:

+-------------------+---------------------------------+-------------------------+
| Tipo              | Evento                          | Variabili               |
+===================+=================================+=========================+
| Chiamata servizio | Chiamata di servizio, abbattuta | dateYMDms ---> dateTime |
+                   +                                 +-------------------------+
|                   |                                 | idlastcall ---> callId  |
+-------------------+---------------------------------+-------------------------+

Esempio richiesta
=================

``http://democrm.teleniasoftware.com/service/hangup?dateTime=2020-01-01T00%3A00%3A00.000Z&callId=1583932001.48%40d0834a2c15``