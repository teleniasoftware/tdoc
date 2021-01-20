============================
Configurazione Google Sheets
============================

Introduzione
=============

La reportizzazione mediante l\'Api di |dm| può essere schedulata ed eseguita in maniera automatizzata mediante Google Sheets.

In questa guida si prenderà come riferimento un documento di report mensile suddiviso per agente.


Predisposizione del documento
=============================

Aprire il documento di esempio tramite `questo link <https://docs.google.com/spreadsheets/d/1d0Cg2D9UxfmMAcw6QE1BEBeeILZ_0Rck9tcSMa__lA0/edit?usp=sharing>`__ 

Una volta effettuato l'accesso con il proprio account Google, selezionare dal menu contestuale File -> Crea una copia

.. figure:: /images/datamodel/googleSheets/5.png

Salvare quindi il nuovo documento su Drive dopo aver inserito il nome che si desidera.

.. figure:: /images/datamodel/googleSheets/6.png

Una volta aperto il documento è possibile iniziare a compilare i valori delle varie colonne:

Colonne disponibili
********************

+-------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
| Nome Colonna            | Descrizione                                                                                                                                                                                                              | Esempio                                                                                                                                  |
+-------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
| API KEY                 | Chiave di accesso alle api di |dm|, |br| accessibile dal configuratore multicanale sotto la sezione Avanzate -> TVox Data Model                                                                                          |                                                                                                                                          |
+-------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
| HOST                    | Dominio del server su cui effetturare le richieste, esempio: https://contact.teleniasoftware.com                                                                                                                         |                                                                                                                                          |
+-------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
| PARAMETERS (Opzionale)  | Parametri opzionali relativi allo script di import dei valori. `Maggiori informazioni <http://documentation.teleniasoftware.com/datamodel/index.html#google-sheets>`_                                                    |                                                                                                                                          |
+-------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
| REPORT TYPE             | Nome del metodo lanciato per l’esecuzione del report. |br| Il file di esempio contiene il valore inboundCallsCount                                                                                                       |                                                                                                                                          |
+-------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
| QUERY GRAPHQL           | Contenuto della query GraphQL che si andrà a lanciare                                                                                                                                                                    | search: { |br| year: $year month: $month user: { |br| userName: {|br| operator: EQUAL, value: $agent |br| } |br| } context:ACTIVE |br| } |
+-------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
| AGENTS                  | Lista degli agenti su cui verrà eseguita la query. |br| Il valore di ogni riga di questa colonna corrisponde all'username di un agente. |br| Nel file di report ad ogni agente corrisponderà un foglio di Google Sheets. |                                                                                                                                          |
+-------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
| EMAIL ADDRESS TO NOTIFY | Indirizzo email che verrà notificato al completamento del report                                                                                                                                                         |                                                                                                                                          |
+-------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
| YEAR                    |                                                                                                                                                                                                                          |                                                                                                                                          |
+-------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
| MONTH                   |                                                                                                                                                                                                                          |                                                                                                                                          |
+-------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+


Per aggiungere più valori sulla cella della colonna REPORT TYPE, fare click con il tasto destro del mouse sulla cella stessa e selezionare "Convalida dei dati".
Dal popup che verrà aperto aggiungere le varie voci separate da un virgola. 

.. figure:: /images/datamodel/googleSheets/7.png


Schedulazione del report
========================

Per schedulare l'avvio automatico del report è necessario creare un trigger dal portale sviluppatori di google. Per fare ciò, basterà navigare dal menu contestuale verso la sezione Strumenti -> Editor di script.

Una volta reindirizzati a questa pagina, localizzare l'icona 

.. image:: /images/datamodel/googleSheets/2.png

Questa porterà alla pagina di configurazione dei trigger. 

Cliccare quindi il pulsante "Aggiungi attivatore" e configurare come segue:

.. figure:: /images/datamodel/googleSheets/4.png

Questa configurazione ci permetterà di eseguire il report mensile in maniera automatica a mezzanotte di ogni primo giorno del mese

Se necessario, al salvataggio, consentire l'accesso con il proprio account Google