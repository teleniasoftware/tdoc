============================================================
Attestazione terminali Yealink su internet tramite VPN TVox
============================================================

É possibile attestare i telefoni Yealink via Internet tramite la VPN di |tvox|

Attivazione servizio VPN
------------------------

L'attivazione del servizio VPN è effettuata tramite richiesta al ServiceDesk di Telenia Software. 

É inoltre necessario configurare il firewall dell'infrastruttura del cliente per esporre la porta *1195 UDP* attraverso l'indirizzo IP pubblico del server TVox.

Configurazione di |tvox|
-------------------------

Per funzionare correttamente gli interni devono essere configurati disabilitando la funzionalità *Peer To Peer*.

Tramite OCC, andare sulla modifica dell'interno Yealink e impostare Peer to Peer a *no*

.. image:: /images/TelefoniYealinkVPN/PeerToPeer.PNG

Configurazione del telefono Yealink
------------------------------------

Accedere all'interfaccia web del telefono Yealink, inserire username e password che di default sono: 

**Username:** *admin* |br|
**Password:** *admin*

Andare nella sezione Settings -> AutoProvision ed impostare l'URL di provisioning nel campo *Server URL*

.. important:: Il *Server URL* da impostare sul telefono deve corrispondere all'indirizzo *https://171.18.128.1*

.. image:: /images/TelefoniYealinkVPN/Autoprovisioning.png

Impostare il parametro RPort selezionando il valore *Enable Direct Process*

.. image:: /images/TelefoniYealinkVPN/Account_Advanced.png

Andare nella sezione Network -> Advanced ed abilitare la VPN del telefono, selezionare poi il valore *Openvpn* alla voce *Mode*.

Caricare il file tar specifico per il telefono fornito dal ServiceDesk Telenia alla voce Advanced -> Vpn -> *Upload VPN Config*

.. image:: /images/TelefoniYealinkVPN/VPN.png

