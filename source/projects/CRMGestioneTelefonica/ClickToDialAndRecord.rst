======================
Click to Dial & Record
======================

L'integrazione della funzionalità "Click to Dial & Record" consente di effettuare una chiamata e gestirne la registrazione su un file audio. Questa funzionalità va integrate mediante l'utilizzo di alcuni metodi chiamati via jsonrcp.

.. warning:: La chiamata dei metodi jsonrcp necessitano che sia stata effettuata l':doc:`autenticazione verso le TVox WebAPI<AutenticazioneTVoxWebAPI>`

Le chiamate dei metodi vanno effettuate verso l'indirizzo **http://<tvox_url>/tvox/webapi** 
( dove <tvox_url> corrisponde al dominio o all'indirizzo IP in cui risiede il TVox )

Dopo aver :doc:`effettuato una chiamata<ClickToDial>` tramite il metodo dialNumber è possibile chiamare i seguenti metodi:

----

recOn
=====
Avvia la registrazione della chiamata attiva

Parametri richiesti
-------------------

recFileName
*******
*String*    Nome del file di registrazione. Se assente verrà generato automaticamente


Richiesta di esempio
--------------------

.. code-block:: JSON

    {
        "jsonrpc":"2.0",
        "method":"recOn",
        "params":[
            "recordedCall"
        ],
        "id":3
    }


----

recOff
=====
Blocca la registrazione della chiamata attiva. Per il corretto funzionamento del metodo è necessario che sia presente una chiamata attiva con una registrazione in corso.

Il metodo non richiede parametri.

Richiesta di esempio
--------------------

.. code-block:: JSON

    {
        "jsonrpc":"2.0",
        "method":"recOff",
        "params":[],
        "id":4
    }