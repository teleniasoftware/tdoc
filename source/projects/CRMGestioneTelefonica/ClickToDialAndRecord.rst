======================
Click to Dial & Record
======================

La funzione "Click to Dial & Record", messa a disposizione dalle TVox WebApi, consente di effettuare una chiamata e gestirne la registrazione su file audio.

.. warning:: Per utilizzare la funzionalità è necessario che sia stata effettuata l':doc:`autenticazione verso le TVox WebAPI<AutenticazioneTVoxWebAPI>`

La richiesta va effettuata verso l'indirizzo **http://<tvox_url>/tvox/webapi** 
( dove <tvox_url> corrisponde al dominio o all'indirizzo IP di |tvox| )

Dopo aver :doc:`effettuato una chiamata<ClickToDial>` tramite il metodo **dialNumber** è possibile utilizzare i seguenti metodi:

----

recOn
=====
Avvia la registrazione della chiamata attiva

Parametri richiesti
-------------------

+--------------+---------+-----------------------------------------+--------------+
| Parametro    | Tipo    | Descrizione                             | Obbligatorio |
+==============+=========+=========================================+==============+
| recFileName  | String  | Nome del file di registrazione          | No           |
+--------------+---------+-----------------------------------------+--------------+


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