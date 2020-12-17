=====
Prodotto
=====

TVox **Mediant Communication System** è un sistema di comunicazione Web Based accessibile via Internet. Orientato alla comunicazione multicanale, consente di accedere a servizi audio, video, chat, desktop e file sharing ed è basato su Sistema Operativo Linux CentOS 7 64 Bit

Ha funzionalità multi-customer dove la community e gli utenti ad essa associati e per ciascun utente si abilitano le funzionalità sopra elencate. Per TVoxMCS deve essere previsto e fornito un dominio pubblico che possa essere risolto sul server TVox-MCS perché possano essere erogati i servizi.
TVox-MCS può essere installato su piattaforme server standard  o virtualizzate **purché compatibili con il sistema operativo** indicato sopra. 

I sistemi di virtualizzazione supportati sono:

- **VMWare** (ESXi / vSphere) Richiesti Workstation v.7 e setup VMWare Tools 
- **Citrix System XEN Center** Installazione in modalità Hardware-assited Virtual Machine (no ParaVirtualization) 
- **Oracle VM Virtual Box** Richiesto setup extension pack

L’installazione in data center prevede risorse che sono  dipendenti dalla consistenza e numerosità di terminali mobili (APP), Client WEB e Widget attivi e pertanto le risorse computazionali e di disponibilità di banda in caso di installazioni massive devono seguire le seguenti indicazioni :

+-----------------+--------------------------------------------------------------+
| MCS Partner (a) |                            Risorse                           |
+-----------------+----------+------+-----------+--------+-----------------------+
|      Utenti     | CPU/Core |  RAM |   Disco   |   Eth  | Bandwith Internet (b) |
+-----------------+----------+------+-----------+--------+-----------------------+
|   Fino a 1000   |     4    | 8 Gb | 150GB SSD | 1 Gbit |       >=100Mb/s       |
+-----------------+----------+------+-----------+--------+-----------------------+
|   Fino a 10000  |     8    | 8 Gb | 150GB SSD |  1Gbit |       >=1000Mb/s      |
+-----------------+----------+------+-----------+--------+-----------------------+
**Ogni istanza MCS può gestire fino ad un massimo di 250 TVox**

Il sistema TVox-MCS dovrà essere connesso alla rete  Internet con  disponibilità di banda (massima) di circa 60 KB/s per ogni connessione attiva dei dispositivi   (APP, UCC Web RTC e Widget) e creata una connessione VPN OpenVPN per ogni TVOX di ciascun cliente finale.

.. warning:: Il servizio MCS non è ridondabile!