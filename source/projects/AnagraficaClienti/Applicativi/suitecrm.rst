=====================================
SuiteCRM
=====================================

Per configurare una sorgente dati che recupera i contatti da SuiteCRM è necessario 
configurare i seguenti campi:

- **Descrizione**: Descrizione che identifica la sorgente dati
- **Versione**: Versione di SuiteCRM da cui si vogliono recuperare i contatti (verificare che la versione del proprio sistema SuiteCRM rientri tra quelle configurabili)
- **Normalizza**: Abilitando la normalizzazione, la sincronizzazione rimuove tutti i caratteri non permessi ammettendo solo le cifre da 0 a 9 ed i caratteri + * e #
- **Host**: Dominio di SuiteCRM al quale si accederà tramite protocollo HTTPS (ES: \https://192.168.6.2/SuiteCRM)
- **Credemziali del client**: Indica il *client_id* usato per l'autenticazione delle richieste di recupero contatti
- **Password del client**: Indica il *client_secret* usato per l'autenticazione delle richieste di recupero contatti
- **Risorsa della sorgente**: Lista di porzioni di rubrica esposte da SuiteCRM da selezionare per dichiarare quali contatti importare

.. image:: /images/anagraficaClienti/SuiteCRM.png