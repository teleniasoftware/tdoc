.. _ChiamataTrasferita_Trasferita:

===================
Chiamata trasferita
===================

:Nome:
    Chiamata trasferita - Trasferita
:Tipo:
    ``GET``
:URI: http://democrm.teleniasoftware.com/transfer/transfer.php
:Eventi:

+-------------------+---------------------+--------------------------------+
| Tipo              | Evento              | Variabili                      |
+===================+=====================+================================+
| Trasferita        | Chiamata trasferita | dateISO ---> dateTime          |
+                   +                     +--------------------------------+
|                   |                     | id ---> callId                 |
+                   +                     +--------------------------------+
|                   |                     | clid ---> callerNumber         |
+                   +                     +--------------------------------+
|                   |                     | userdnis ---> transferToAgent  |
+-------------------+---------------------+--------------------------------+

Esempio richiesta
=================

.. code-block:: sh

    http://democrm.teleniasoftware.com/transfer/transfer?dateTime=2020-11-20T10%3A45%3A57.249Z&callId=1605869145.791%40d92061befe&callerNumber=0987654321&transfer=op2