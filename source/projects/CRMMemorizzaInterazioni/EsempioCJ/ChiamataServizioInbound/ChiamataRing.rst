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
| Chiamata servizio | Chiamata in ring | dateYMDms ---> dateTime |
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

``http://democrm.teleniasoftware.com/service/new?dateTime=2020-01-01T00%3A00%3A00.000Z&callId=1583932001.48%40d0834a2c15&agent=op1&service=customercare&callerNumber=0452224600``