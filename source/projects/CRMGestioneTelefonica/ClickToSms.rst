============
Click to SMS
============

Per effettuare chiamate tramite la funzione "Click to SMS" va utilizzato il metodo **sendSms** messo a disposizione dalle TVox WebApi.

.. warning:: Per utilizzare la funzionalità è necessario che sia stata effettuata l':doc:`autenticazione verso le TVox WebAPI<AutenticazioneTVoxWebAPI>`

La richiesta va effettuata verso l'indirizzo **http://<tvox_url>/tvox/webapi** 
( dove <tvox_url> corrisponde al dominio o all'indirizzo IP di |tvox| )

----

Parametri richiesti
###################

+--------------+---------+-----------------------------------------+--------------+
| Parametro    | Tipo    | Descrizione                             | Obbligatorio |
+==============+=========+=========================================+==============+
| number       | String  | Numero del destinatario                 | Si           |
+--------------+---------+-----------------------------------------+--------------+
| message      | String  | Contenuto del messaggio                 | Si           |
+--------------+---------+-----------------------------------------+--------------+


----

Richiesta di esempio
####################

.. code-block:: JSON

   {
   "jsonrpc": "2.0", 
   "method": "sendSms", 
   "params": [
      "1234567890",
      "Message text"
   ], 
   "id": 2
   }

.. note:: Una documentazione più dettagliata del metodo può essere trovata a questo |documentation_link|.


.. |documentation_link| raw:: html

    <a href="https://documenter.getpostman.com/view/805183/tvox-webapi-demo/RVfvFXDA#9cc67f12-e4b0-4768-9689-d6ee8aa6e50f" target="_blank">link</a>