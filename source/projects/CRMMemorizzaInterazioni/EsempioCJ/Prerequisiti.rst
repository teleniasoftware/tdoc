============
Prerequisiti
============

Per questo esempio è necessario disporre di un TVox opportunamente licenziato e configurato per ricevere chiamate di servizio da numerazioni pubbliche, nello specifico devono esistere:

- Almeno un servizio di Contact Center, che noi chiameremo *Customer Care* (codice: *customercare*)
- Almeno due operatori di Contact Center appartenenti ad uno skillset associato al servizio *Customer Care*; gli operatori avranno username *op1* e *op2*
- Trunk configurato per ricevere chiamate da numerazioni pubbliche e inoltrarle al servizio *Customer Care*
- Contatto in rubrica esterna (associata al servizio *Customer Care*), che nel nostro caso si chiamerà *Mario Rossi* e avrà numero *0452224600*; il numero di questo contatto verrà usato come identificativo per essere associato al relativo contatto su CRM

------------

Di seguito è possibile scaricare i sorgenti dell'applicazione utilizzata in questo esempio. |br|
I sorgenti contengono:

- ``index.php``, pagina del nostro CRM su cui vedremo la scheda contatto con il suo Customer Journey che si popolerà delle interazioni di chiamata
- ``service/*.php``, Web Service per la gestione degli eventi di chiamata di servizio
- ``outbound/*.php``, Web Service per la gestione degli eventi di chiamata outbound
- ``transfer/*.php``, Web Service per la gestione degli eventi di chiamata trasferita

Per le finalità dell'esercizio è necessario disporre di un Web Server con interprete PHP raggiungibile dal TVox, nel nostro caso, all'indirizzo http://democrm.teleniasoftware.com.

Per mantenere una memoria delle interazioni associate al contatto è stato scelto di salvare le informazioni su un file JSON (`democrm_db.json`) in modo da non dover aggiungere ultieriori dipendenze.

I Web Service presenti nei sorgenti sono solo a scopo dimostrativo, ma possono essere presi come base per sviluppi più complessi; all'utilizzatore rimane comunque la piena libertà di sviluppo in termini di linguaggio e modalità implementative.

:download:`Scarica i sorgenti <esercizio_notificationservice.zip>`

::

     Disponibile a breve...

.. |br| raw:: html

   <br />