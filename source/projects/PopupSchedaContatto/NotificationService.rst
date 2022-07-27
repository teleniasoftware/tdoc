.. _popup-scheda-contatto-notification-service:
================================
Servizi di notifica
================================

I servizi di notifica possono essere configurati dall'apposita sezione dell'OCC **Notification Service**.

.. image:: ../../images/notificationService/ConfigurazioneOCC_Servizi.png

Come mostrato in figura, da questa interfaccia è possibile cercare (1) e gestire (2) i servizi configurati oppure crearne di nuovi (3).

Crea un nuovo servizio di notifica
==================================

In questa sezione puoi configurare gli eventi di chiamata che verranno notificati su un singolo Web Service.

.. warning:: Sul server dove risiede il Web Service, le richieste provenienti da TVox devono essere consentite e non bloccate da alcun controllo di accesso o firewall. In genere, le richieste **HTTP** viaggiano sulla porta *8080*/*80*, mentre le richieste **HTTPS** sulla porta *443*.

Vediamo nel dettaglio quali sono i parametri di configurazione del Web Service in riferimento alla seguente immagine:

.. image:: ../../images/notificationService/ConfigurazioneOCC_CreaServizio_WS.png

#. **Nome**: descrive brevemente il gruppo di eventi notificati al Web Service corrente
#. **Abilitato**: abilita/disabilita le notifiche al Web Service corrente
#. **Tipo**: metodo HTTP con cui verranno eseguite le richieste verso il Web Service, può essere di 2 tipi:

    #. `GET`, le variabili configurate sugli eventi vengono notificate attraverso parametri in `query string <https://it.wikipedia.org/wiki/Query_string>`_
    #. `POST`, le variabili configurate sugli eventi vengono notificate all'interno del body della richiesta (``Context-Type: application/x-www-form-urlencoded``)
    #. `SALESFORCE`, le richieste verso Salesforce vengono autenticate tramite flusso OAuth 2.0 JWT Bearer, come documentato `qui <https://help.salesforce.com/s/articleViewid=sf.remoteaccess_oauth_jwt_flow.htm&type=5>`_, è necessario completare la configurazione dei parametri di autenticazione Salesforce (sezione OCC "Configurazione generali di sistema > Autenticazione e sicurezza > Salesforce"). Le variabili configurate vengono notificate all'interno del body della richiesta (``Context-Type: application/x-www-form-urlencoded``), come per il tipo POST.
#. **URI**: URI del Web Service su cui verranno eseguite le richieste
#. **Username** (*Opzionale*): username di autenticazione tramite |basic_authentication_link|. Non previsto per il tipo `SALESFORCE`
#. **Password** (*Opzionale*): password di autenticazione tramite |basic_authentication_link|. Non previsto per il tipo `SALESFORCE`
#. **Timeout connessione**: tempo massimo (in secondi) entro cui la richiesta tenterà una connessione verso l'URI configurato
#. **Timeout risposta**: tempo massimo (in secondi) che la richiesta aspetterà per avere una risposta dall'URI configurato

Ora approfondiamo la configurazione degli eventi:

.. image:: ../../images/notificationService/ConfigurazioneOCC_CreaServizio_Eventi.png

#. **Abilitato**: abilita/disabilita le notifiche del singolo evento al Web Service corrente
#. **Tipo**: tipologia della chiamata da notificare
#. **Evento**: evento da notificare in base al tipo di chiamata selezionato
#. **Filtro** (*Opzionale*): se l'evento riguarda una chiamata di servizio, è possibile filtrare l'evento su un singolo servizio 
#. **Variabili**: mappa chiave/chiave delle informazioni dell'evento da notificare al Web Service

La descrizione dettagliata degli eventi e delle variabili configurabili può essere trovata nella documentazione tecnica.

Documentazione tecnica
======================

Per conoscere la versione di libreria "Notification Service" attualmente disponibile nel vostro sistema TVox, potete andare sull'OCC nella sezione info.
Conoscendo la vostra versione potete accedere alla |documentation_link|

.. image:: ../../images/info.png

Log
======================

.. .. image:: ../../images/notificationService/ConfigurazioneOCC_Log.png

Nella sezione *Log* è possibile visionare e scaricare il log mensile delle notifiche prodotte dal Notification Service. |br|
Questo può tornare molto utile sia in fase di sviluppo del Web Service, sia per un'analisi approfondita nel caso in cui vi fosse qualche malfunzionamento.

.. note:: Il log viene mantenuto per 12 mesi.

Esempio: Chiamata in ring
=========================

:Nome:
    Chiamata di servizio inbound - Ring
:Tipo:
    ``GET``
:URI: http://democrm.teleniasoftware.com/service/ring.php
:Eventi:

+-------------------+------------------+-------------------------+
| Tipo              | Evento           | Variabili               |
+===================+==================+=========================+
| Chiamata servizio | Chiamata in ring | dateISO ---> dateTime   |
+                   +                  +-------------------------+
|                   |                  | idlastcall ---> callId  |
+                   +                  +-------------------------+
|                   |                  | pin ---> agent          |
+                   +                  +-------------------------+
|                   |                  | servizio ---> service   |
+                   +                  +-------------------------+
|                   |                  | cli ---> callerNumber   |
+-------------------+------------------+-------------------------+

**Richiesta generata**

.. code-block:: sh

    http://democrm.teleniasoftware.com/service/new?dateTime=2020-11-20T10%3A24%3A08.674Z&callId=1605867847.783%40d92061befe&agent=op1&service=customercare&callerNumber=0987654321

Esempio: Chiamata abbattuta
===============================

:Nome:
    Chiamata di servizio inbound - Abbattuta
:Tipo:
    ``GET``
:URI: http://democrm.teleniasoftware.com/service/hangup.php
:Eventi:

+-------------------+---------------------------------+-------------------------+
| Tipo              | Evento                          | Variabili               |
+===================+=================================+=========================+
| Chiamata servizio | Chiamata di servizio, abbattuta | dateISO ---> dateTime   |
+                   + |br| *(dopo la risposta)*       +-------------------------+
|                   |                                 | idlastcall ---> callId  |
+                   +                                 +-------------------------+
|                   |                                 | cli ---> callerNumber   |
+-------------------+---------------------------------+-------------------------+
| Chiamata servizio | Chiamata abbattuta              | dateISO ---> dateTime   |
+                   + |br| *(prima della risposta)*   +-------------------------+
|                   |                                 | idlastcall ---> callId  |
+                   +                                 +-------------------------+
|                   |                                 | cli ---> callerNumber   |
+-------------------+---------------------------------+-------------------------+

**Richiesta generata**

.. code-block:: sh

    http://democrm.teleniasoftware.com/service/hangup?dateTime=2020-11-20T10%3A24%3A46.959Z&callId=1605867847.783%40d92061befe&callerNumber=0987654321

Esempio: Chiamata trasferita
============================

:Nome:
    Chiamata trasferita - Trasferita
:Tipo:
    ``GET``
:URI: http://democrm.teleniasoftware.com/transfer/transfer.php
:Eventi:

+-------------------+---------------------+--------------------------------+
| Tipo              | Evento              | Variabili                      |
+===================+=====================+================================+
| Trasferita        | Chiamata trasferita | dateISO ---> dateTime          |
+                   +                     +--------------------------------+
|                   |                     | id ---> callId                 |
+                   +                     +--------------------------------+
|                   |                     | clid ---> callerNumber         |
+                   +                     +--------------------------------+
|                   |                     | userdnis ---> transferToAgent  |
+-------------------+---------------------+--------------------------------+

**Richiesta generata**

.. code-block:: sh

    http://democrm.teleniasoftware.com/transfer/transfer?dateTime=2020-11-20T10%3A45%3A57.249Z&callId=1605869145.791%40d92061befe&callerNumber=0987654321&transfer=op2


.. |br| raw:: html

    <br />
 
.. |documentation_link| raw:: html
 
    <a href="http://documentation.teleniasoftware.com/notification_service/index.html#introduction"target="_blank"> Documentazione tecnica</a>
 
.. |basic_authentication_link| raw:: html
 
    <a href="https://it.wikipedia.org/wiki/Basic_access_authentication"target="_blank">Basic Authentication</a>