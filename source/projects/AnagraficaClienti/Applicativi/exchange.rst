=====================================
Exchange
=====================================

Per configurare una sorgente dati che recupera i contatti da un server Exchange è necessario 
configurare i seguenti campi:

- **Descrizione**: Descrizione che identifica la sorgente dati
- **Versione**: Versione del server Exchange da cui si vogliono recuperare i contatti (verificare che la versione del proprio server Exchange rientri tra quelle configurabili)
- **Normalizza**: Abilitando la normalizzazione, la sincronizzazione rimuove tutti i caratteri non permessi ammettendo solo le cifre da 0 a 9 ed i caratteri + * e #
- **Host**: Ip del server Exchange al quale si accederà tramite protocollo HTTPS
- **Username**: Username dell'account con il quale si accederà per recuperare i contatti
- **Password**: Password dell'account con il quale si accederà per recuperare i contatti
- **Timeout della connessione**: Indica il numero massimo di secondi che TVox attende per ricevere una risposta dal server Exchange

.. image:: /images/anagraficaClienti/Exchange.png