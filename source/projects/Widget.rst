Widget
======

Introduzione
------------

La libreria widget di Telenia permette di mettere in comunicazione i tuoi clienti con i servizi configurati 
e gli operatori loggati sul tuo Server Tvox usando uno dei canali licenziati.

I canali ad ora disponibili sono:

- Telefonico
- Video
- Chat
- Mail
- Callback

La libreria widget fornisce due funzioni:

- Una interfaccia per la connessione al Server.
- Una libreria grafica per poter disegnare la widget.

La libreria è prodotta nel linguaggio javascript e richiede la conoscenza di `rxjs <https://rxjs-dev.firebaseapp.com/>`_.

**Network**

La connessione al server avviene tramite websocket, inizializzata via http tramite la porta 443.

**Webrtc**

Per la comunicazione audio e video è utilizzato il protocollo WebRTC.
Gli Ice Server del protocollo WebRTC comunicano sulla porta 3478 mentre i flussi audio e video, 
criptati tramite il protocollo DTLS, sono instaurati nelle porte tra la 10000 e 20000.

Documentazione tecnica
=======================

`Widget <http://documentation.teleniasoftware.com/widget/index.html>`_