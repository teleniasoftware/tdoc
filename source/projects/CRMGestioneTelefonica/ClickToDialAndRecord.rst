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

+-------------+------------+-----------------------------------------------+--------------+
| Parametro   | Tipo       | Descrizione                                   | Obbligatorio |
+=============+============+===============================================+==============+
| username    | String     | Username dell'utente che effettua la chiamata | Si           |
+-------------+------------+-----------------------------------------------+--------------+
| recFileName | String     | Nome del file di registrazione                | No           |
+-------------+------------+-----------------------------------------------+--------------+


Richiesta di esempio
--------------------

.. code-block:: JSON

    {
        "jsonrpc":"2.0",
        "method":"recOn",
        "params":[
            "mrossi",
            "recordedCall"
        ],
        "id":3
    }

.. note:: Una documentazione più dettagliata del metodo può essere trovata a questo |documentation_link_1|.


.. |documentation_link_1| raw:: html

    <a href="https://documenter.getpostman.com/view/805183/tvox-webapi-demo/RVfvFXDA#d9bb6d61-1bee-2fbf-9868-939d980e3806" target="_blank">link</a>


----

recOff
======

Blocca la registrazione della chiamata attiva. Per il corretto funzionamento del metodo è necessario che sia presente una chiamata attiva con una registrazione in corso.

Parametri richiesti
-------------------

+-------------+------------+-----------------------------------------------+--------------+
| Parametro   | Tipo       | Descrizione                                   | Obbligatorio |
+=============+============+===============================================+==============+
| username    | String     | Username dell'utente che effettua la chiamata | Si           |
+-------------+------------+-----------------------------------------------+--------------+
| callId      | String     | Id della chiamata                             | Si           |
+-------------+------------+-----------------------------------------------+--------------+

Richiesta di esempio
--------------------

.. code-block:: JSON

    {
        "jsonrpc":"2.0",
        "method":"recOff",
        "params":[
            "mrossi",
            "1234@5678"
        ],
        "id":4
    }

.. note:: Una documentazione più dettagliata del metodo può essere trovata a questo |documentation_link_2|.


.. |documentation_link_2| raw:: html

    <a href="https://documenter.getpostman.com/view/805183/tvox-webapi-demo/RVfvFXDA#f702d5ac-cf26-88fd-b641-750d7898e4b3" target="_blank">link</a>