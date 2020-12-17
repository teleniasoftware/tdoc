===============
Networking
===============

Premessa: l'MCS, essendo un server che va esposto su internet, deve risiedere in una DMZ e *non deve avere alcun tipo di visibilità verso le LAN locali*.

---------------
MCS
---------------

Porte in ingresso da Internet a MCS:
------------------------------------

+----------------+-------------+---------------------------------------+---------------------------------------------------------------+
| Protocollo     | Porte       |              Servizio                 |                   Note e limitazioni                          |
+================+=============+=======================================+===============================================================+
|   UDP/TCP      |     3478    |            Stun/turn server           |                                                               |
+----------------+-------------+---------------------------------------+---------------------------------------------------------------+
|     UDP        | 10000–20000 |             RTP SRTP DTLS             |                                                               |
+----------------+-------------+---------------------------------------+---------------------------------------------------------------+
|   UDP/TCP      |     1194    | Server OpenVPN per tunnel VPN da TVox | Limitabile ai soli IP pubblici dei TVox se conosciuti         |
+----------------+-------------+---------------------------------------+---------------------------------------------------------------+
|     TCP        |      80     |         HTTP redirect to HTTPS        |                                                               |
+----------------+-------------+---------------------------------------+---------------------------------------------------------------+
|     TCP        |     443     |    HTTPS TVox WebClient / Teams App   |                                                               |
+----------------+-------------+---------------------------------------+---------------------------------------------------------------+
|     TCP        |      22     |                  SSH                  | Solo per gli IP di amministrazione e IP pubblici Telenia      |
|                |             |                                       | |br| (79.8.39.108/32 e 93.39.91.217/32)                       |
+----------------+-------------+---------------------------------------+---------------------------------------------------------------+

Porte in uscita da MCS a Internet:
----------------------------------

+------------+------------+-------------------------+-----------------------------------------------------------------+
| Protocollo |  Porte     |         Servizio        |                        Note e limitazioni                       |
+============+============+=========================+=================================================================+
|     TCP    |   443      |          HTTPS          | Richiesto per:                                                  |
|            |            |                         |                                                                 |
|            |            |                         | * Controllo aggiornamenti e licenza verso server AWS            |
|            |            |                         | * Integrazione Let’s Encrypt                                    |
+------------+------------+-------------------------+-----------------------------------------------------------------+
|   UDP/TCP  |   53       |           DNS           |                                                                 |
+------------+------------+-------------------------+-----------------------------------------------------------------+
|     TCP    | 25,465,587 | Invio e-mail di allarme | Limitabile all’IP del servizio di posta e alla porta utilizzata |
+------------+------------+-------------------------+-----------------------------------------------------------------+
|     UDP    |     123    |        NTP              |                                                                 |
+------------+------------+-------------------------+-----------------------------------------------------------------+

Va garantito l'accesso a Telenia dai nostri ip pubblici (79.8.39.108/32 e 93.39.91.217/32)

----
TVox
----

Porte in uscita da TVox a MCS:
------------------------------

+------------+-------------+------------------+--------------------+
| Protocollo |    Porte    |     Servizio     | Note e limitazioni |
+============+=============+==================+====================+
|   UDP/TCP  |     3478    | Stun/turn server |                    |
+------------+-------------+------------------+--------------------+
|     UDP    | 10000–20000 |   RTP SRTP DTLS  |                    |
+------------+-------------+------------------+--------------------+
|   UDP/TCP  |     1194    |  tunnel OpenVPN  |                    |
+------------+-------------+------------------+--------------------+

Porte in uscita da TVox a Internet:
-----------------------------------

+------------+---------------+----------------------------------+------------------------------------------------------------------+
| Protocollo |     Porte     |             Servizio             |                        Note e limitazioni                        |
+============+===============+==================================+==================================================================+
|     TCP    |    443,2197   | Apple Push Notification Service  |                                                                  |
+------------+---------------+----------------------------------+------------------------------------------------------------------+
|     TCP    | 443,5228-5230 | Google Push Notification Service |                                                                  |
+------------+---------------+----------------------------------+------------------------------------------------------------------+
|     TCP    |      443      |              HTTPS               | Richiesto per controllo aggiornamenti e licenza verso server AWS |
+------------+---------------+----------------------------------+------------------------------------------------------------------+
|   UDP/TCP  |       53      |               DNS                |                                                                  |
+------------+---------------+----------------------------------+------------------------------------------------------------------+
|     TCP    |  25,465,587   |     Invio e-mail di allarme      |  Limitabile all’IP del servizio di posta e alla porta utilizzata |
+------------+---------------+----------------------------------+------------------------------------------------------------------+
|     UDP    |     123       |               NTP                |                                                                  |
+------------+---------------+----------------------------------+------------------------------------------------------------------+

Porte in ingresso da Internet a TVox:
-------------------------------------

Non è richiesta alcuna esposizione pubblica da Internet per la corretta interconnessione con il servizio offerto da MCS.

--------------------
Postazioni operatori
--------------------

La comunicazione da TVox verso WebClient o TVoxTeamApp in modalità WebRTC quando quest'ultime si trovano all'interno della LAN aziendale deve essere di tipo LAN-to-LAN (no NAT).

.. note:: In assenza di visibilità LAN-to-LAN tra TVox e WebClient / TVoxTeamApp i flussi audio e video dovranno necesariamente transitare attraverso Internet utilizzando il servizio Stun/Turn dell'MCS.

Se è necessario limitare in uscita il traffico delle postazioni degli operatori è necessario consentire almeno le seguenti regole:


Da WebClient / TVoxTeamApp a MCS:
---------------------------------

+------------+-------------+----------------------+--------------------+
| Protocollo |    Porte    |       Servizio       | Note e limitazioni |
+============+=============+======================+====================+
|     TCP    |     443     | HTTPS TVox WebClient |                    |
+------------+-------------+----------------------+--------------------+
|   TCP/UDP  |     3478    |   Stun/Turn server   |                    |
+------------+-------------+----------------------+--------------------+
|     UDP    | 10000-20000 |     RTP SRTP DTLS    |                    |
+------------+-------------+----------------------+--------------------+

Da WebClient / TVoxTeamApp a TVox in LAN:
-----------------------------------------

+------------+-------------+----------------------+--------------------+
| Protocollo |    Porte    |       Servizio       | Note e limitazioni |
+============+=============+======================+====================+
|     TCP    |     443     | HTTPS TVox WebClient |                    |
+------------+-------------+----------------------+--------------------+
|     UDP    | 10000-20000 |     RTP SRTP DTLS    |                    |
+------------+-------------+----------------------+--------------------+

Da TVox a WebClient / TVoxTeamApp in LAN:
-----------------------------------------

+------------+-------------+----------------------+--------------------+
| Protocollo |    Porte    |       Servizio       | Note e limitazioni |
+============+=============+======================+====================+
|     UDP    |  1024-65536 |     RTP SRTP DTLS    |                    |
+------------+-------------+----------------------+--------------------+



.. note:: I dispositivi **IOS** devono poter raggiungere i servizi di notifca PUSH di Apple. |br| Vedere https://support.apple.com/en-us/HT203609

.. note:: I dispositivi **Android** devono poter raggiungere i servizi di notifca PUSH di Apple. |br| Vedere https://firebase.google.com/docs/cloud-messaging/concept-options#messaging-ports-and-your-firewall
