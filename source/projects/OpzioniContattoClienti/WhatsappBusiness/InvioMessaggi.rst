===============
Invio messaggi
===============

Una volta completata la creazione dell'applicazione Facebook sarà possible avviare nuove conversazioni mediante le api Graph di Facebook, disponibili nella `Guida ufficiale <https://developers.facebook.com/docs/whatsapp/cloud-api/guides>`_.

L'inizio di una conversazione può essere effttuata **solo** tramite un template creato dal portale WhatsApp Manager e ogni template dovrà prima essere validato da Facebook per essere utilizzato.

Creazione di un template
========================

- Accedere al portale `WhatsApp Manager <https://business.facebook.com/wa/manage/home>`_ e selezionare l'account business corretto

- Dal menu a sinistra navigare nella sezione **Modelli di messaggi**

- Cliccare il pulsante **Crea modello di messaggio**

.. figure:: /images/Whatsapp/Business/template-1.png

- Selezionare la tipologia di corretta del template e selezionare le lingue desiderate

.. figure:: /images/Whatsapp/Business/template-2.png

- Personalizzare il template aggiungendo un testo seguendo le `linee guida <https://developers.facebook.com/docs/whatsapp/api/messages/message-templates>`_ ufficiali

- Salvare il template e attendere la verifica da parte di Facebook


Esempi di invio messaggi
========================

L'invio dei messaggi può essere effettuato tramite una richiesta POST autenticata tramite access token (temporaneo o permanente). Il contenuto della richiesta identifica la modalità di invio tramite template o come messaggio di testo

``https://graph.facebook.com/{{Version}}/{{Phone-Number-ID}}/messages``

- **{{Version}}** corrisponde alla versione delle api Facebook, ad esempio v13.0
- **{{Phone-Number-ID}}** corrisponde all'ID fornito da Facebook relativo al numero di telefono con il quale si vuole effettuare l'invio
- **{{Recipient-Phone-Number}}** corrisponde al numero di telefono al quale si vuole inviare il messaggio

Invio tramite template
**********************

.. code-block:: json

    {
        "messaging_product": "whatsapp",
        "to": "{{Recipient-Phone-Number}}",
        "type": "template",
        "template": {
            "name": "codice_tvox",
            "language": {
                "code": "it"
            },
            "components": [
                {
                    "type": "body",
                    "parameters": [
                        {
                            "type": "text",
                            "text": "6346436456"
                        },
                    ]
                }
            ]
        }
    }

I template possono contenere variabili, sostituibili dal conenuto della property `components`. Ogni variabile dovrà essere sostituita da un opportuno valore per poter effettuare l'invio del messaggio

Invio tramite messaggio
***********************

.. code-block:: json

    {
        "messaging_product": "whatsapp",
        "to": "{{Recipient-Phone-Number}}",
        "type": "text",
        "text": {
            "preview_url": false,
            "body": "MESSAGE_CONTENT"
        }
    }