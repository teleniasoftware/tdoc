============
Click to SMS
============

L’integrazione della funzionalità "Click to SMS" può essere svolta mediante la chiamata del metodo **sendSms** via jsonrpc, che permette di effettuare l'invio di un SMS ad un determinato numero.

.. warning:: La chiamata del metodo sendSms necessita che sia stata effettuata l':doc:`autenticazione verso le TVox WebAPI<AutenticazioneTVoxWebAPI>`

La chiamata del metodo sendSms va effettuata verso l'indirizzo **http://<tvox_url>/tvox/webapi** 
( dove <tvox_url> corrisponde al dominio o all'indirizzo IP in cui risiede il TVox )

----

Parametri richiesti
###################

number
******
*String*    Numero del destinatario **Campo obbligatorio**

message
***********
*String*    Contenuto del messaggio **Campo obbligatorio**

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
