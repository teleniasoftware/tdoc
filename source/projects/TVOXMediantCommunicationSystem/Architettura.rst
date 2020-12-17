===============
Architettura
===============

.. |mcs_location| image:: ../../images/MCS/mcs_location.png

| Questa configurazione permette di garantire la sicurezza del TVox che non è mai accessibile da internet. La connessione tra le due piattaforme è stabilita attraverso un tunnel OpenVPN dal TVox verso MCS. 
| È sufficiente garantire al TVox la navigazione su internet senza restrizioni (È anche possibile restringere il perimetro di navigazione del TVox alla sola raggiungibilità dell’MCS e di altri protocolli, :doc:`vedi sezione Networking<Networking>` ).
| La connettività in uscita non deve transitare da un proxy.

| MCS può essere installato ovunque sia garantito un accesso ad Internet opportunamente configurato. Non deve avere alcuna visibilità diretta con TVox (Lan to Lan, va quindi prevista una DMZ qualora il TVox e l’MCS risiedano nella stessa sede). 

|mcs_location|