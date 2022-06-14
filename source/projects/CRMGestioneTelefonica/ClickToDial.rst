=============
Click to Dial
=============

.. important:: Per questa funzionalità è disponibile l'API REST documentata al seguente |documentation_link|. |br|
   Verificarne la disponibilità nella propria versione consultando la sezione "*Info*" dell'OCC. |br|
   Di seguito è dettagliata la versione "*Legacy*" che utilizza il protocollo JSON-RPC, ma si consiglia l'utlizzo della modalità REST.

Per effettuare chiamate tramite la funzione "Click to Dial" va utilizzato il metodo **dialNumber** messo a disposizione dalle TVox WebApi.

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
| username     | String  | Username dell'utente che effettua la chiamata | Si           |
+--------------+---------+-----------------------------------------------+--------------+
| number       | String  | Numero da chiamare                            | Si           |
+--------------+---------+-----------------------------------------------+--------------+
| accessCode   | String  | Codice d'accesso                              | Si           |
+--------------+---------+-----------------------------------------------+--------------+
| jobLabel     | String  | Label della chiamata                          | Si           |
+--------------+---------+-----------------------------------------------+--------------+
| recordCall   | boolean | Registra chiamata                             | No           |
+--------------+---------+-----------------------------------------------+--------------+
| recFileName  | String  | Nome del file di registrazione                | No           |
+--------------+---------+-----------------------------------------------+--------------+
| returnCallId | boolean | Ritorna l'id di chiamata nella risposta       | No           |
+--------------+---------+-----------------------------------------------+--------------+
| serviceCode  | String  | Codice di servizio ( Call Tagging )           | No           |
+--------------+---------+-----------------------------------------------+--------------+

----

Richiesta di esempio
####################

.. code-block:: JSON

    {
      "jsonrpc":"2.0",
      "method":"dialNumber",
      "params":[
         "mrossi",
         "600",
         "",
         "",
         false,
         null,
         true,
         ""
      ],
      "id":2
   }

.. note:: Una documentazione più dettagliata del metodo può essere trovata a questo |documentation_legacy_link|.

.. |documentation_link| raw:: html

    <a href="http://documentation.teleniasoftware.com/tvox_webapi/index.html#dial-number" target="_blank">link</a>


.. |documentation_legacy_link| raw:: html

    <a href="https://documenter.getpostman.com/view/805183/tvox-webapi-demo/RVfvFXDA#f02dc2cd-464c-4a2a-9ecd-50e56eadb893" target="_blank">link</a>

.. |br| raw:: html

   <br />