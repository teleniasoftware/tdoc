.. _ChiamataServizioInbound_Abbattuta:

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
| Chiamata servizio | Chiamata di servizio, abbattuta | dateISO ---> dateTime   |
+                   + |br| *(dopo la risposta)*       +-------------------------+
|                   |                                 | idlastcall ---> callId  |
+                   +                                 +-------------------------+
|                   |                                 | cli ---> callerNumber   |
+-------------------+---------------------------------+-------------------------+
| Chiamata servizio | Chiamata abbattuta              | dateISO ---> dateTime   |
+                   + |br| *(prima della risposta)*   +-------------------------+
|                   |                                 | idlastcall ---> callId  |
+                   +                                 +-------------------------+
|                   |                                 | cli ---> callerNumber   |
+-------------------+---------------------------------+-------------------------+

Esempio richiesta
=================
.. code-block::

    http://democrm.teleniasoftware.com/service/hangup?dateTime=2020-11-20T10%3A24%3A46.959Z&callId=1605867847.783%40d92061befe&callerNumber=0987654321


.. |br| raw:: html

   <br />