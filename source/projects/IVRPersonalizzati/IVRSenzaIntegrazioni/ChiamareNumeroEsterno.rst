============================
 Chiamare un numero esterno
============================

Analogamente all'azione precedente, questa consente il trasferimento verso un numero esterno a TVox:

.. image:: /images/IVR_chiama_esterno1.png


I parametri previsti consentono di impostare:

-   **Numero da chiamare**: il numero esterno cui la chiamata deve essere trasferita
-   **Tempo di ring**: il tempo massimo di ring in secondi
-   **Tentativi**: il numero massimo di tentativi in attesa  della risposta da parte del numero chiamato. Superato tale numero senza risposta, la chiamata passa al nodo successivo dell'ivr.
-   **Abilitazione**: va scelta l'abilitazione da utilizzare per il trasferimento. Il numero da chiamare, impostato nel primo campo, deve contenerere eventuali access code previsti dall'abilitazione.
-   **Registrazione della chiamata**: Tramite questo flag è possibile registrare la chiamata trasferita esternamente

.. image:: /images/IVR_chiama_esterno2.png