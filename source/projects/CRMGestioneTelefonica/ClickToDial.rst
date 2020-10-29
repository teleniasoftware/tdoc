=============
Click to Dial
=============

L'integrazione della funzionalità "Click to Dial" può essere svolta mediante la chiamata del metodo **dialNumber** via jsonrpc che permette di effettuare una chiamata ad un determinato numero di telefono.

.. warning:: La chiamata del metodo dialNumber necessita che sia stata effettuata l':doc:`autenticazione verso le TVox WebAPI<AutenticazioneTVoxWebAPI>`

La chiamata del metodo dialNumber va effettuata verso l'indirizzo **http://<tvox_url>/tvox/webapi** 
( dove <tvox_url> corrisponde al dominio o all'indirizzo IP in cui risiede il TVox )

----

Parametri richiesti
###################

Tale richiesta richiede, nel seguente ordine, i parametri: 

number
******
*String*    Numero da chiamare   **Campo obbligatorio**

accessCode
***********
*String*    Codice d'accesso     **Campo obbligatorio**

jobLabel
***********
*String*    Nome della chiamata  **Campo obbligatorio**

recordCall
***********
*boolean*   Registra chiamata

recFileName
***********
*String*    Nome del file di registrazione  

returnCallId
*************
*boolean*   Ritorna l'id di chiamata nella risposta

serviceCode
***********
*String*    Codice di servizio ( Call Tagging )


----

Richiesta di esempio
####################

.. code-block:: JSON

    {
      "jsonrpc":"2.0",
      "method":"dialNumber",
      "params":[
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