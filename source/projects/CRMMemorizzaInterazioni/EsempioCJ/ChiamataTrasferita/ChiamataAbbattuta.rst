.. _ChiamataTrasferita_Abbattuta:

==================
Chiamata abbattuta
==================

:Nome:
    Chiamata trasferita - Abbattuta
:Canale:
    ``Telefonico``
:Tipo:
    ``GET``
:URI: http://democrm.teleniasoftware.com/transfer/hangup.php
:Eventi:

+-------------------+--------------------+-------------------------+
| Tipo              | Evento             | Variabili               |
+===================+====================+=========================+
| Chiamata inbound  | Chiamata abbattuta | dateISO ---> dateTime   |
+                   +                    +-------------------------+
|                   |                    | id ---> callId          |
+                   +                    +-------------------------+
|                   |                    | clid ---> callerNumber  |
+-------------------+--------------------+-------------------------+

Esempio richiesta
=================

.. code-block:: sh

    http://democrm.teleniasoftware.com/transfer/hangup?dateTime=2020-11-20T10%3A47%3A49.475Z&callId=11605869145.791%40d92061befe&callerNumber=0987654321