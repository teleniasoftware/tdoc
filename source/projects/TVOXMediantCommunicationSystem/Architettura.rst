===============
Architettura
===============

.. |mcs_location| image:: ../../images/MCS/mcs_location.png

| Questa configurazione permette di garantire la sicurezza del TVox che non è mai accessibile da internet. La connessione tra le due piattaforme è stabilita attraverso un tunnel OpenVPN dal TVox verso MCS. 
| È sufficiente garantire al TVox la navigazione su internet senza restrizioni (È anche possibile restringere il perimetro di navigazione del TVox alla sola raggiungibilità dell’MCS e di altri protocolli, :doc:`vedi sezione Networking<Networking>` ).
| La connettività in uscita non deve transitare da un proxy.

| MCS può essere installato ovunque sia garantito un accesso ad Internet opportunamente configurato. Non deve avere alcuna visibilità diretta con TVox (Lan to Lan, va quindi prevista una DMZ qualora il TVox e l’MCS risiedano nella stessa sede). 

.. note:: L'MCS deve disporre di un idirizzo IP pubblico statico in NAT 1:1 o direttamente attestato sulla scheda di rete.

|mcs_location|


----------
DNS e FQDN
----------


E' necessario avere un FQDN risolto come record A sull'IP pubblico utilizzato dall'MCS. Questo FQDN sarà il dominio di management.

.. note:: Il dominio di management verà utilizzato per la configurazione iniziale dell'MCS e per la gestione degli impianti ad esso collegati ed i relativi certificati SSL.

Ogni impianto TVox interconnesso all'MCS deve disporre di un proprio FQDN per l'accesso ai servizi.
Ognuno di questi FQDN dovrà essere risolto pubblicamente come CNAME del dominio di management dell'MCS

.. tip:: Per fruire dei TVoxWebClient e di TVoxTeamApp in house è necessario far si che l'FQDN dell'impianto TVox internamente all'azienda venga risolto con l'IP del TVox stesso. In alternativa tutti gli accessi client e app saranno possibili solo in modalità Smart Working (sottoposto a licenza).
