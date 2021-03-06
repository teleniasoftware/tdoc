Funzioni dell'integrazione
===========================

PSTN Gateway
------------

.. image:: ../../../images/microsoft/teams/teams_arch_01.png

La funzione base di questa integrazione prevede che |tvox_pbx| agisca come gateway per la gestione delle linee telefoniche aziendali e ne permette l'utilizzo con |msteams| senza sostituire l'infrastruttura.

Le linee possono essere:

- linee PSTN geografiche
- IPPBX esistenti 

Interconnettendo |msteams| alla rete pubblica tramite |tvox_pbx|, è possibile gestire chiamate telefoniche con alcuni trattamenti evoluti offerti da TVox stesso, quali ad esempio la consultazione di un calendario o l'attraversamento di un albero IVR.

Attendant Console
-----------------

.. image:: ../../../images/microsoft/teams/teams_arch_02.png

Oltre alla funzione di gateway telefonico appena descritta, |tvox_pbx| può attivare il suo modulo di Attendant Console (Posto Operatore) che consente, con il proprio client, di gestire chiamate provenienti dalla rete pubblica e smistarle verso |msteams|.

Contact Center 
--------------

.. image:: ../../../images/microsoft/teams/teams_arch_03.png

Attivando il modulo di Contact Center Multicanale si può realizzare un'isola di agenti su |tvox|.
Questi possono gestire sessioni telefoniche e multicanale e interagire telefonicamente con gli utenti attestati su |msteams|.


Twin TVox & Microsoft Teams®
-----------------------------

.. image:: ../../../images/microsoft/teams/teams_arch_04.png

L'integrazione tra |msteams| e |tvox_pbx| permette di gestire chiamate dalla PSTN facendo squillare contemporaneamente sia il client |msteams| che il  dispositivo attestato su |tvox_pbx|

Per un utente che necessita di utilizzare sia |msteams| che un dispositivo attestato su |tvox_pbx|, l'integrazione permette di 
gestire le chiamate dirette a lui facendo squillare contemporaneamente sia il client |msteams| sia il  dispositivo utilizzato su |tvox_pbx|. |br| 
Ad esempio, configurandolo in questa modalità, l'utente può usare il client |msteams| finchè si trova alla propria scrivania, e il proprio dispositivo cordless in aree dell'azienda dove |msteams| non è utilizzabile.



.. |msteams| raw:: html 

    <a href="https://teams.microsoft.com/"target="_blank"> Microsoft Teams®</a>


