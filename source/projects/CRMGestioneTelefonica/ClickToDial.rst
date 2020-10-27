=============
Click to Dial
=============

L'integrazione della funzionalità "Click to Dial" può essere svolta mediante la chiamata di un metodo via jsonrpc che permette di effettuare una chiamata ad un determinato numero.

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