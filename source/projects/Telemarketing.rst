==============
Telemarketing
==============

Il Sistema Power Dialer è lo strumento necessario per la generazione automatica di chiamate telefoniche, realizzato per effettuare **campagne di Telemarketing** o notifiche telefoniche con messaggi preregistrati sotto forma di IVR (**notifiche telefoniche massive**)

Il sistema Power Dialer è da intendersi quale un modulo che si aggiunge alle prestazioni Contact Center, in quanto gestisce le chiamate outbound in maniera tale che, una volta che una chiamata ha ottenuto la risposta da parte del contatto cercato, questa viene presa in carico da un apposito servizio di Contact Center che la accoda ai propri skillset analogamente a quanto avviene per i servizi di contact center inbound.

La quantità di chiamate generate dal Power Dialer è condizionata dal numero di operatori disponibili e da variabili opportunamente configurate dall'amministratore del sistema.

---------

La gestione del Power Dialer prevede la definizione di:

- **una o più liste**

- **una o più campagne**

- **una tabella di frontiera**


---------

Liste
=====

Nella definizione di una lista sono associabili le parametrizzazioni che consentono di stabilire quando ripianificare una chiamata, 
in termini di **numero di ritentativi** e **timeout di attesa** tra un tentativo ed il successivo a fronte di mancata risposta per i motivi di linea occupata, chiamata riagganciata, congestione o altro.

.. image:: ../images/PowerDialer/PD_Liste.JPG
   :scale: 60%
   :align: center


Gli esiti gestiti dal sistema di Power Dialing sono i seguenti:

- **Nessuna Risposta**: nessuna risposta fornita dal contatto chiamato.

- **Occupato**: il contatto risulta occupato in un'altra conversazione.

- **Abbattuta dal chiamato**: il contatto ha risposto e successivamente riagganciato la chiamata prima di essere messo in contatto con il servizio associato alla campagna.

- **Congestion**: il sistema TVox Communication Power Dialing non ha trovato alcun canale telefonico disponibile per effettuare la chiamata o, in alternativa, il numero selezionato non è risultato valido.

- **Chiusa dal sistema TVox Communication**: il contatto ha risposto ed è rimasto in attesa di essere servito dal servizio TVox Communication associato alla campagna. Scaduto il tempo massimo di attesa sul servizio il contatto è stato riagganciato.



---------

Campagne
========

La Campagna individua un identificativo logico a cui associare la programmazione temporale di una particolare attività di chiamate, una indicazione di massima circa le **risorse da destinare all'attività**, e l'insieme dei contatti da chiamare che sono raggruppati per liste.

.. image:: ../images/PowerDialer/PD_Campagne.JPG
   :scale: 60%
   :align: center 

Oltre al periodo di validità, l'abilitazione per le chiamate in uscita ed il servizio di outbound a cui inoltrare le chiamate stesse si vanno a definire i seguenti indicatori :

**Canali Riservati**: Numero massimo di canali telefonici in uscita dal TVox Communication utilizzati dalla campagna corrente calcolati 
come percentuale dei canali complessivamente configurati per il TVox Communication Power Dialing.

**Canali Impegnati**: Numero di canali impegnati in uscita dal TVox Communication per la campagna corrente calcolati come percentuale delle risorse presenti o disponibili tra quelle skillate per il servizio associato:

- `Risorse disponibili - (agenti loggati al servizio che si trovano in stato Pronto)`

- `Risorse presenti - (agenti loggati al servizio)`

`Tale valore è comunque regolato dal parametro “Canali Riservati” che consente di stabilire un limite superiore per il numero di chiamate attive per la stessa campagna.`

Operando su questo parametro si può ottenere un tuning sulle prestazioni del Power Dialer in termini di quantità di chiamate contemporaneamente iniziate per la campagna corrente.

`ESEMPIO`: Impostando il valore a '0% su Risorse disponibili' il sistema inizia una nuova chiamata a fronte di ogni operatore in stato 'Pronto'. Impostando il valore a '100% su Risorse disponibili' il sistema inizia due nuove chiamate a fronte di ogni operatore in stato 'Pronto', ecc...


---------

Tabella di Scambio
==================

La tabella di frontiera (denominata `ast_pd_interface`) è necessaria all'integrazione con applicazione CRM o di Telemarketing di terze parti.

Tale tabella dovrà contenere tanti record quanti sono i nominativi da contattare.

Per ogni record verranno riportati:

- l'identificativo numerico associato al chiaamnte (**id**)

- numero da chiamare (**phone_number**)

- identificativo numerico della campagna (**campagna**)

- identificativo numerico della lista (**lista**)

- contenuto da riportare nell'invocazione di un eventuale popup a fronte della presa della chiamata da parte dell'agente di CC (**data**)


.. image:: ../images/PowerDialer/PD_Tabella.JPG
   :scale: 60%
   :align: center 

Per poter inserire, modificare e cancellare i record della tabella di scambio "ast_pd_interface" è possibile accedere al databse 
con l'utenza dedicata (*user=tvox_pd password=tvox_pd*).


---------

Impostazioni generali
=====================

Le configurazioni generali da assegnare al modulo di Power Dialing inteso come servizio atto a generare chiamate uscenti prevedono che sia stabilito il livello di **occupazione delle linee (canali) disponibili** verso la rete PSTN o in generale verso il proprio carrier telefonico, **l'abilitazione telefonica** ad effettuare traffico outbound e il **tempo massimo di ring** che il sistema adotta per individuare quando una chiamata non ha ricevuto risposta.

.. image:: ../images/PowerDialer/PD_Impostazioni_generali.JPG
   :scale: 60%
   :align: center 


---------

.. note:: La configurazione dei parametri disponibili per la gestione delle campagne di chiamate telefoniche deve garantire il rispetto delle norme emanate dal Garante per la protezione dei dati personali in materia di chiamate mute (rif. Gazzetta Ufficiale n. 79 del 4 aprile 2014).


Per attenersi a queste norme è indispensabile seguire i suggerimenti che seguono:

– evitare di richiamare con intervallo inferiore di una settimana quei contatti che, pur avendo risposto alla chiamata, non sono stati messi in comunicazione con gli operatori del Contact Center entro un breve intervallo di tempo (max 5 secondi). Per fare ciò è sufficiente gestire il parametro “Chiusa dal sistema TVox” disponibile nel dettaglio di ogni lista di contatti che viene associata alla campagna di chiamate.

– si deve fare in modo che l'attesa sia almeno accompagnata da un messaggio oppure da una musica di attesa adeguata evitando assolutamente le attese silenziose. In questo caso è indispensabile che il servizio telefonico che si occupa dell'accodamento della chiamata agli operatori disponga della necessaria musica di attesa e che il timeout di coda sia nei termini richiesti inferiore alla decina di secondi.


---------

.. important:: Dopo aver completato la configurazione dei parametri di liste e campagne e aver caricato i riferimenti ai contatti nella tabella di scambio, per poter dare inizio alla campagna stessa, è necessario effettuare un reset dei contatori agendo sul parametro **“Abilita/Disabilita”** della campagna di riferimento: tale operazione va ripetuta ogniqualvolta si modificano i dati contenuti nella tabella di scambio per fare si che gli indicatori di progressione siano riferiti ad una effettiva fotografia della tabella stessa.


---------

Il recupero dell'esito delle chiamate avviene con la medesima utenza preposta per la configurazione della tabella di scambio ((user=tvox_pd password=tvox_pd))

Le tabelle interessate sono **ast_pd_history_<yyyymm>** che hanno la struttura analoga alla tabella ast_pd_interface e con le
tabelle **ast_calls_outbound_<yyyymm>** 

