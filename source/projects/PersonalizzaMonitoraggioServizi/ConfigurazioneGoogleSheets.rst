============================
Configurazione Google Sheets
============================

Introduzione
=============

La reportizzazione mediante le api Data Model può essere eseguita schedulata ed 
eseguita in maniera automatizzata mediante Google Sheets.

In questa guida si prenderà come riferimento un documento di report mensile suddiviso per agente.


Predisposizione del documento
=============================

Aprire il documento di esempio tramite `questo link <https://docs.google.com/spreadsheets/d/1d0Cg2D9UxfmMAcw6QE1BEBeeILZ_0Rck9tcSMa__lA0/edit?usp=sharing>`_ 

Una volta effettuato l'accesso con il proprio account Google, selezionare dal menu contestuale File -> Crea una copia

.. image:: ../../images/dataModel/googleSheets/5.png

Salvare quindi il nuovo documento su Drive dopo aver inserito il nome che si desidera.

.. image:: ../../images/dataModel/googleSheets/6.png

Una volta aperto il documento è possibile iniziare a compilare i valori delle varie colonne:

Colonne disponibili
********************

API KEY
--------
Chiave di accesso alle api per il Data Model, accessibile dal configuratore multicanale sotto la sezione Avanzate -> TVox Data Model

HOST
------
Dominio del server su cui effetturare le richieste, esempio: https://contact.teleniasoftware.com

PARAMETERS (Opzionale)
------------
Parametri opzionali relativi allo script di import dei valori. `Maggiori informazioni <http://documentation.teleniasoftware.com/datamodel/index.html#google-sheets>`_ 

REPORT TYPE
------------
Nome del metodo lanciato per l'esecuzione del report. Il file di esempio contiene il valore inboundCalls.

Per aggiungere più valori fare un click con il tasto destro del mouse sulla cella contenente la select e selezionare "Convalida dei dati".
Dal popup che verrà aperto aggiungere le varie voci separate da un virgola. 

.. image:: ../../images/dataModel/googleSheets/7.png

QUERY GRAPHQL
--------------
Contenuto della query GraphQL che si andrà a lanciare, esempio:

    search: {
        year: $year
        month: $month
        user: { 
            userName: { 
                operator: EQUAL, 
                value: $agent 
            } 
        }
        context:ACTIVE
    }

AGENTS
------
Lista degli agenti su cui verrà eseguita la query. Verranno presi in considerazione tutti i valori popolati di tale colonna.

EMAIL ADDRESS TO NOTIFY
-----------------------
Indirizzo email che verrà notificato al completamento del report


Schedulazione del report
========================

Per schedulare l'avvio automatico del report è necessario creare un trigger dal portale sviluppatori di google. Per fare ciò, basterà navigare dal menu contestuale verso la sezione Strumenti -> Editor di script.

Una volta reindirizzati a questa pagina, localizzare l'icona 

.. image:: ../../images/dataModel/googleSheets/2.png

Questa porterà alla pagina di configurazione dei trigger. 

Cliccare quindi il pulsante "Aggiungi attivatore" e configurare come segue:

.. image:: ../../images/dataModel/googleSheets/4.png

Questa configurazione ci permetterà di eseguire il report mensile in maniera automatica a mezzanotte di ogni primo giorno del mese

Se necessario, al salvataggio consentire l'accesso con il proprio account Google