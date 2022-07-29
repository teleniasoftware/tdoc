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