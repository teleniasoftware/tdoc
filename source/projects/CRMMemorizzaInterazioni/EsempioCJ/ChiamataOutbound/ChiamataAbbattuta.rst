==================
Chiamata abbattuta
==================

:Nome:
    Chiamata outbound - Abbattuta
:Tipo:
    ``GET``
:URI: http://democrm.teleniasoftware.com/outbound/hangup
:Eventi:

+-------------------+--------------------+-------------------------+
| Tipo              | Evento             | Variabili               |
+===================+====================+=========================+
| Chiamata outbound | Chiamata abbattuta | dateYMDms ---> dateTime |
+                   +                    +-------------------------+
|                   |                    | id ---> callId          |
+                   +                    +-------------------------+
|                   |                    | dnis ---> calledNumber  |
+-------------------+--------------------+-------------------------+

Esempio richiesta
=================

``http:http://democrm.teleniasoftware.com/outbound/hangup?dateTime=2020-01-01T00%3A00%3A00.000Z&callId=1583932001.48%40d0834a2c15&calledNumber=0452224600``