===================================
Ricerca registrazioni di chiamata
===================================

Per ricercare i dettagli delle registrazioni di chiamata va utilizzato il metodo **searchRecordedCall** messo a disposizione dalle TVox WebApi.

.. warning:: Per utilizzare la funzionalità è necessario che sia stata effettuata l':doc:`autenticazione verso le TVox WebAPI<AutenticazioneTVoxWebAPI>`

La richiesta va effettuata verso l'indirizzo **https://<tvox_url>/tvox/webapi** 
( dove <tvox_url> corrisponde al dominio o all'indirizzo IP di |tvox| )

----

.. important:: I parametri specificati di seguito devono essere mantenuti nell'ordine riportato.

Parametri richiesti
###################

+----------------+-----------------------+---------------------------------------------------------------------------------------------------+--------------+
| Parametro      | Tipo                  | Descrizione                                                                                       | Obbligatorio |
+================+=======================+===================================================================================================+==============+
| startFrom      | Date                  | Data inizio - Operazioni disponibli: ``GT``, ``GE``                                               | Si           |
+----------------+-----------------------+---------------------------------------------------------------------------------------------------+--------------+
| startTo        | Date                  | Data fine - Operazioni disponibli: ``LT``, ``LE``                                                 | Si           |
+----------------+-----------------------+---------------------------------------------------------------------------------------------------+--------------+
| users          | Set< String >         | Lista di utenti (username) - Operazioni disponibli: ``EQUAL``                                     | No           |
+----------------+-----------------------+---------------------------------------------------------------------------------------------------+--------------+
| exten          | String                | Interno - Operazioni disponibli: ``CONTAINS``, ``EQUAL``                                          | No           |
+----------------+-----------------------+---------------------------------------------------------------------------------------------------+--------------+
| direction      | RecordedCallDirection | Direzione (``INBOUND``, ``OUTBOUND``) - Operazioni disponibli: ``EQUAL``                          | No           |
+----------------+-----------------------+---------------------------------------------------------------------------------------------------+--------------+
| services       | Set< String >         | Lista di servizi (codici) - Operazioni disponibli: ``EQUAL``                                      | No           |
+----------------+-----------------------+---------------------------------------------------------------------------------------------------+--------------+
| clid           | String                | Numero del chiamante - Operazioni disponibli: ``CONTAINS``, ``EQUAL``                             | No           |
+----------------+-----------------------+---------------------------------------------------------------------------------------------------+--------------+
| dnis           | String                | Numero del chiamato - Operazioni disponibli: ``CONTAINS``, ``EQUAL``                              | No           |
+----------------+-----------------------+---------------------------------------------------------------------------------------------------+--------------+
| duration       | Integer               | Durata - Operazioni disponibli: ``EQUAL``, ``GT``, ``GE``, ``LT``, ``LE``                         | No           |
+----------------+-----------------------+---------------------------------------------------------------------------------------------------+--------------+
| note           | String                | Note - Operazioni disponibli: ``CONTAINS``, ``EQUAL``                                             | No           |
+----------------+-----------------------+---------------------------------------------------------------------------------------------------+--------------+
| userSites      | Set< Integer >        | Lista di siti utente (id) - Operazioni disponibli: ``EQUAL``                                      | No           |
+----------------+-----------------------+---------------------------------------------------------------------------------------------------+--------------+
| fileName       | String                | Nome del file della registazione - Operazioni disponibli: ``CONTAINS``, ``EQUAL``                 | No           |
+----------------+-----------------------+---------------------------------------------------------------------------------------------------+--------------+
| customFileName | String                | Nome personalizzato del file della registrazione - Operazioni disponibli: ``CONTAINS``, ``EQUAL`` | No           |
+----------------+-----------------------+---------------------------------------------------------------------------------------------------+--------------+
| externalData   | String                | Dati esterni - Operazioni disponibli: ``CONTAINS``, ``EQUAL``                                     | No           |
+----------------+-----------------------+---------------------------------------------------------------------------------------------------+--------------+
| type           | RecordedCallType      | Tipo registrazione (``SERVICE``, ``ON_DEMAND``, ``AUTOMATIC``) - Operazioni disponibli: ``EQUAL`` | No           |
+----------------+-----------------------+---------------------------------------------------------------------------------------------------+--------------+

Campi ordinalibili: ``date``, ``duration``

----

Richiesta di esempio
####################

.. code-block:: JSON

    {
      "jsonrpc": "2.0",
      "method": "searchRecordedCall",
      "id": 2,
      "params": [
         {
               "criterias": {
                  "startFrom": {
                     "operation": "GE",
                     "value": 1546300800000
                  },
                  "startTo": {
                     "operation": "LE",
                     "value": 1548979200000
                  },
                  "users": {
                     "operation": "EQUAL",
                     "value": null
                  },
                  "exten": {
                     "operation": "EQUAL",
                     "value": null
                  },
                  "direction": {
                     "operation": "EQUAL",
                     "value": null
                  },
                  "services": {
                     "operation": "EQUAL",
                     "value": null
                  },
                  "clid": {
                     "operation": "EQUAL",
                     "value": null
                  },
                  "dnis": {
                     "operation": "EQUAL",
                     "value": null
                  },
                  "duration": {
                     "operation": "GT",
                     "value": null
                  },
                  "note": {
                     "operation": "CONTAINS",
                     "value": null
                  },
                  "userSites": {
                     "operation": "EQUAL",
                     "value": null
                  },
                  "fileName": {
                     "operation": "CONTAINS",
                     "value": null
                  },
                  "customFileName": {
                     "operation": "CONTAINS",
                     "value": null
                  },
                  "externalData": {
                     "operation": "CONTAINS",
                     "value": null
                  },
                  "type": {
                     "operation": "EQUAL",
                     "value": null
                  }
               },
               "exclusions": null,
               "page": 1,
               "size": 10,
               "sortField": "date",
               "sortOrder": "ASC"
         }
      ]
   }

.. note:: Una documentazione più dettagliata del metodo può essere trovata a questo |documentation_legacy_link|.

.. |documentation_legacy_link| raw:: html

    <a href="https://documenter.getpostman.com/view/805183/tvox-webapi-demo/RVfvFXDA#955a1fea-c011-4d4c-9826-f1d0b5249eda" target="_blank">link</a>