==================================================================
Esempio: Ricostruisci lo storico messaggi della chat WEB/WhatsApp
==================================================================

Seguendo l'esempio riportato in ":ref:`EsempioCJ`" per il canale telefonico, è possibile costruire un Customer Journey anche per il canale Chat (sia WEB che WhatsApp) semplicemente configurando il canale adatto nella configurazione degli eventi.

Sfruttando l'id di sessione della Chat (variabile: ``uniqueid``) su eventi di servizio inbound, alla chiusura della sessione è possibile recuperare l'intero storico messaggi (allegati inclusi) tramite API REST (documentata |documentation_link|).


.. |documentation_link| raw:: html

    <a href="http://documentation.teleniasoftware.com/tvox_webapi/index.html#list-chat-session-messages"target="_blank"> qui</a>