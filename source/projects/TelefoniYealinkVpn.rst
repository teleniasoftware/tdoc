============================================================
Attestazione terminali Yealink su internet tramite VPN TVox
============================================================

E' possibile attestare i telefoni Yealink su internet tramite la VPN di |tvox|

Configurazione di |tvox|
-------------------------

Tramite OCC, andare sulla modifica dell'interno Yealnk e impostare Peer to Peer a *no*

.. image:: /images/TelefoniYealinkVPN/PeerToPeer.PNG

Contattare il ServiceDesk di Telenia Software per ottenere la configurazione della VPN Server.

Configurazione del telefono Yealink
------------------------------------

Accedere all'interfaccia web del telefono Yealink, inserire username e password che di default sono: 

**Username:** *admin* |br|
**Password:** *admin*

Andare nella sezione Settings -> AutoProvision ed impostare l'url di provisioning nel campo *Server Url*

.. important:: Il *Server Url*  da impostare sul telefono corrisponde all'IP *171.18.128.1*

.. image:: /images/TelefoniYealinkVPN/Autoprovisioning.png

Impostare il parametro RPort selezionando il valore *Enable Direct Process*

.. image:: /images/TelefoniYealinkVPN/Account_Advanced.png

Andare nella sezione Network -> Advanced ed abilitare la VPN del telefono, selezionare poi il valore *Openvpn* alla voce *Mode*.

Caricare il file tar fornito dal ServiceDesk Telenia alla voce Advanced -> Vpn -> *Upload VPN Config*

.. image:: /images/TelefoniYealinkVPN/VPN.png

