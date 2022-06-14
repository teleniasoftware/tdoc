==================================
Chiamate di servizio dell'utente
==================================

Per recuperare la lista di chiamate di servizio in corso (in ringing o risposte) per un determinato utente/agente, ordinate dalla più recente alla più vecchia, può essere utilizzato il metodo **getServiceCurrentCalls** messo a disposizione dalle TVox WebApi.

.. warning:: Per utilizzare la funzionalità è necessario che sia stata effettuata l':doc:`autenticazione verso le TVox WebAPI<AutenticazioneTVoxWebAPI>`

La richiesta va effettuata verso l'indirizzo **https://<tvox_url>/tvox/webapi** 
( dove <tvox_url> corrisponde al dominio o all'indirizzo IP di |tvox| )

----

.. important:: I parametri specificati di seguito devono essere mantenuti nell'ordine riportato.

Parametri richiesti
###################

+--------------+---------+-----------------------------------------+--------------+
| Parametro    | Tipo    | Descrizione                             | Obbligatorio |
+==============+=========+=========================================+==============+
| username     | String  | Username dell'utente/agente             | Si           |
+--------------+---------+-----------------------------------------+--------------+

----

Richiesta di esempio
####################

.. code-block:: JSON

    {
      "jsonrpc":"2.0",
      "method":"getServiceCurrentCalls",
      "params":[
         "mrossi"
      ],
      "id":2
   }

.. note:: Una documentazione più dettagliata del metodo può essere trovata a questo |documentation_link|.


.. |documentation_link| raw:: html

    <a href="https://documenter.getpostman.com/view/805183/tvox-webapi-demo/RVfvFXDA#e3848e22-c379-4b69-8ebc-48605c6cb754" target="_blank">link</a>