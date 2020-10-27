============
Click to SMS
============

L’integrazione della funzionalità “Click to SMS può essere svolta mediante la chiamata di un metodo via jsonrpc che permette di effettuare l'invio di un SMS ad un determinato numero

Parametri richiesti
###################

number
******
*String*    Numero del destinatario **Campo obbligatorio**

message
***********
*String*    Contenuto del messaggio **Campo obbligatorio**


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
