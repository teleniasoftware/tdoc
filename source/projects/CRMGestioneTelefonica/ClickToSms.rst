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
