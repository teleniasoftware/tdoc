==============
Nuova chiamata
==============

:Nome:
    Chiamata outbound - Nuova
:Tipo:
    ``GET``
:URI: http://democrm.teleniasoftware.com/outbound/new
:Eventi:

+-------------------+------------------+-------------------------+
| Tipo              | Evento           | Variabili               |
+===================+==================+=========================+
| Chiamata outbound | Nuova chiamata   | dateYMDms ---> dateTime |
+                   +                  +-------------------------+
|                   |                  | id ---> callId          |
+                   +                  +-------------------------+
|                   |                  | dnis ---> calledNumber  |
+                   +                  +-------------------------+
|                   |                  | userclid ---> agent     |
+-------------------+------------------+-------------------------+

Esempio richiesta
=================

``http:http://democrm.teleniasoftware.com/outbound/new?dateTime=2020-01-01T00%3A00%3A00.000Z&callId=1583932001.48%40d0834a2c15&calledNumber=0452224600&agent=op1``