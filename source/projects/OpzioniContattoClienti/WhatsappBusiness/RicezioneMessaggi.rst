==================
Ricezione messaggi
==================

Per ricevere i messaggi ricevuti verso l'account WhatsApp è necessario configurare un webhook dal portale Facebook Developers

Accedere al portale `Facebook Developers <https://developers.facebook.com/apps/>`_, selezionare l'applicazione precedentemente configurata e navigare verso la categoria **WhatsApp -> Configurazione** dal menu a sisnistra

.. figure:: /images/Whatsapp/Business/ricezione-1.png

Nella configurazione del webhook cliccare il tasto **Modifica**, inserire l'url per la ricezione dei messaggi nel formato `https://<DOMINIO_TVOX>/customerproxy/whatsapp/meta` e il token di verifica configurato su OCC

.. figure:: /images/Whatsapp/Business/ricezione-2.png

Configurare i permessi del webhook cliccando il tasto **Gestisci** e sottoscriversi al campo `messages`

.. figure:: /images/Whatsapp/Business/ricezione-3.png