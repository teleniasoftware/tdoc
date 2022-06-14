=============
Hangup Call
=============

.. important:: Per questa funzionalità è disponibile l'API REST documentata al seguente |documentation_link|. |br|
   Verificarne la disponibilità nella propria versione consultando la sezione "*Info*" dell'OCC. |br|
   Di seguito è dettagliata la versione "*Legacy*" che utilizza il protocollo JSON-RPC, ma si consiglia l'utlizzo della modalità REST.

Per riagganciare una chiamata in corso va utilizzato il metodo **hangupCall** messo a disposizione dalle TVox WebApi.

.. warning:: Per utilizzare la funzionalità è necessario che sia stata effettuata l':doc:`autenticazione verso le TVox WebAPI<AutenticazioneTVoxWebAPI>`

La richiesta va effettuata verso l'indirizzo **https://<tvox_url>/tvox/webapi** 
( dove <tvox_url> corrisponde al dominio o all'indirizzo IP di |tvox| )

----

.. important:: I parametri specificati di seguito devono essere mantenuti nell'ordine riportato.

Parametri richiesti
###################

+--------------+---------+-----------------------------------------------+--------------+
| Parametro    | Tipo    | Descrizione                                   | Obbligatorio |
+==============+=========+===============================================+==============+
| callId       | String  | Id della chiamata                             | Si           |
+--------------+---------+-----------------------------------------------+--------------+

----

Richiesta di esempio
####################

.. code-block:: JSON

    {
      "jsonrpc":"2.0",
      "method":"hangupCall",
      "params":[
         "1234@5678"
      ],
      "id":1
   }

.. |documentation_link| raw:: html

    <a href="http://documentation.teleniasoftware.com/tvox_webapi/index.html#hangup-call" target="_blank">link</a>

.. |br| raw:: html

   <br />