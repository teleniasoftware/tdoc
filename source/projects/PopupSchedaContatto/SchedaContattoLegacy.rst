=============================
Modalità Legacy (Windows BAT)
=============================

In questa sezione è stata mantenuta la possibilità di configurare il winpopup come nelle versioni precedenti all'introduzione della gestione tramite URL. 

Di seguito l'elenco delle variabili legate alla chiamata che possono essere utilizzate:


    - PIN: Utilizzato dall'agente per il login al servizio telefonico
    - USERNAME: Codice utente che identifica univocamente l'agente
    - IDCALL: Identificativo univoco della chiamata
    - CALLTYPE: Tipo chiamata: I=inbound, O=outbound
    - SKILLSET: Codice skillset assegnato all'agente che ha gestito la chiamata
    - SERVICE: Codice del servizio assegnato alla chiamata
    - CLI: Caller ID, Identificativo numerico del chiamante
    - DNIS: Dialed Number Identification Service, numero chiamato
    - RECEIVING_SITE NCC: ID del sito TVox su cui è iniziata la chiamata
    - DISTRIBUTION_SITE NCC: ID del sito dove si trova l'agente che ha risposto
    - EVENT: Istante in cui viene richiesta l'esecuzione del batch di popup. valori possibili "ring", "answer", "hangup" oppure "UNK"

Se al servizio è associato un IVR con lo scopo di collezionare dati (es: via DTMF) da correlare alla chiamata, questi vengono salvati e separati con il carattere separatore “|” in popupinfo_x.
Il TVoxClient recupera queste informazioni aggiuntive e le propone associate ad una o più delle seguenti variabili:

    - POPUPINFO_1: Primo dato collezionato, altrimenti UNK
    - POPUPINFO_2: Secondo dato collezionato, altrimenti UNK
    - ...
    - POPUPINFO_i: i-esimo dato collezionato, altrimenti UNK

Un esempio di utilizzo dello screen popup può essere il seguente:

.. code-block::

    if "%SERVICE%" == "servizio_1" GOTO REQ1
    if "%SERVICE%" == "servizio_2" GOTO REQ2
    :REQ1
    start "" "http://mycrm.net/call.php?pin=%PIN%&idcall=%IDCALL%&number=%CLI%"
    GOTO ESCI
    :REQ2
    start "" "http://crm.it/popup.php?pin=%PIN%&info=%POPUPINFO_2%&caller=%CLI%"
    GOTO ESCI
    :ESCI

