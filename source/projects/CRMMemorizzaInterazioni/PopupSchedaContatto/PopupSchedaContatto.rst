.. _PopupSchedaContatto:

=========================
Pop - up scheda contatto
=========================

All’arrivo di un’interazione apri automaticamente la scheda contatto del tuo crm in modo da fornire all’operatore di contact center tutte le informazioni utili alla gestione della richiesta, ottimizzando la produttività del Customer Care.

---------

La sezione Popup Manager permette di configurare l'apertura di una pagina (screen popup) su un'applicazione di terze parti durante la gestione di un'interazione di contact center (canale telefonico, web chat e whatsapp, video, canali custom) .

Questa funzione può essere scatenata:

- in fase di ring su client dell'agente
- all'atto della risposta da parte dell'agente
- alla chiusura della gestione
- on demand, a discrezione dell'agente

----------

La funzionalità può essere erogata in due modalità:

- Generazione URL su server
- Legacy (Windows BAT)

Nel primo caso, l'URL viene generato dal server e fornito al client che può eseguirlo in IFRAME all'interno del client stesso, oppure su una nuova scheda o finestra del browser predefinito della postazione

Nel secondo caso, la funzionalità viene erogata dallo script *winpopup.bat* direttamente dalla postazione utente che gestisce l'interazione:

- questa modalità consente al sistema di essere compatibile con installazioni passate che implementavano questo unico metodo;
- è l'unica modalità che consente di invocare eseguibili esterni WIN32 per interagire con applicativi che non supportano i comandi via URL.


Come si può notare nell'immagine seguente, per abilitare la funzionalità sui servizi si agisce tramite la tab *servizi associati* dove, per ogni servizio, è possibile effettuare la scelta sui singoli canali:

.. image:: /images/popup/tabServiziAssociati.PNG


.. toctree::  
   :hidden: 
   :maxdepth: 1

   SchedaContattoServer
   SchedaContattoLegacy
   