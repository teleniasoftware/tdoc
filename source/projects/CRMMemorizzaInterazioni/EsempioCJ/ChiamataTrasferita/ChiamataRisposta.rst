.. _ChiamataTrasferita_Risposta:

=================
Chiamata risposta
=================

:Nome:
    Chiamata trasferita - Risposta
:Tipo:
    ``GET``
:URI: http://democrm.teleniasoftware.com/transfer/answer.php
:Eventi:

+-------------------+-------------------+-------------------------+
| Tipo              | Evento            | Variabili               |
+===================+===================+=========================+
| Chiamata inbound  | Chiamata risposta | dateISO ---> dateTime   |
+                   +                   +-------------------------+
|                   |                   | id ---> callId          |
+                   +                   +-------------------------+
|                   |                   | clid ---> callerNumber  |
+-------------------+-------------------+-------------------------+

Esempio richiesta
=================
.. code-block::

    http://democrm.teleniasoftware.com/transfer/answer?dateTime=2020-11-20T10%3A46%3A31.601Z&callId=1605869145.791%40d92061befe&callerNumber=0987654321