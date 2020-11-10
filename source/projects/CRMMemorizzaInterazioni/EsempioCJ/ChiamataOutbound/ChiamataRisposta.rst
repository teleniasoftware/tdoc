=================
Chiamata risposta
=================

:Nome:
    Chiamata outbound - Risposta
:Tipo:
    ``GET``
:URI: http://democrm.teleniasoftware.com/outbound/answer
:Eventi:

+-------------------+-------------------+-------------------------+
| Tipo              | Evento            | Variabili               |
+===================+===================+=========================+
| Chiamata outbound | Chiamata risposta | dateYMDms ---> dateTime |
+                   +                   +-------------------------+
|                   |                   | id ---> callId          |
+                   +                   +-------------------------+
|                   |                   | dnis ---> calledNumber  |
+-------------------+-------------------+-------------------------+

Esempio richiesta
=================

``http:http://democrm.teleniasoftware.com/outbound/answer?dateTime=2020-01-01T00%3A00%3A00.000Z&callId=1583932001.48%40d0834a2c15&calledNumber=0452224600``