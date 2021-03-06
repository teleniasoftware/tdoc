=====================================
VTE
=====================================

Per configurare una sorgente dati che recupera i contatti da VTE è necessario 
configurare i seguenti campi:

- **Descrizione**: Descrizione che identifica la sorgente dati
- **Versione**: Versione di VTE da cui si vogliono recuperare i contatti (verificare che la versione del proprio sistema VTE rientri tra quelle configurabili)
- **Normalizza**: Abilitando la normalizzazione, la sincronizzazione rimuove tutti i caratteri non permessi ammettendo solo le cifre da 0 a 9 ed i caratteri + * e #
- **Host**: Ip di VTE al quale si accederà tramite protocollo **HTTP**
- **Username**: Indica l'username dell'utente amministrativo usato per il recupero contatti
- **Password**: Indica la password dell'utente amministrativo usato per il recupero contatti
- **Risorsa della sorgente**: Lista di porzioni di rubrica esposte da VTE da selezionare per dichiarare quali contatti importare

.. image:: /images/anagraficaClienti/VTE.png