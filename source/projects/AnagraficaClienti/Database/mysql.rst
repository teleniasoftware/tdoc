=====================================
MySQL
=====================================

Per configurare una sorgente dati che recupera i contatti facendo una query su un database MySQL è necessario 
configurare i seguenti campi:

- **Descrizione**: Descrizione che identifica la sorgente dati

- **Host**: Ip del database MySQL

- **Porta**: Porta su cui accedere al database MySQL

- **Username**: Indica l'username dell'utente MySQL usato per l'esecuzione della query

- **Password**: Indica la password dell'utente MySQL usato per l'esecuzione della query

- **Normalizza**: Abilitando la normalizzazione, la sincronizzazione rimuove tutti i caratteri non permessi ammettendo solo le cifre da 0 a 9 ed i caratteri + * e #

- **Query**: Indica la query personalizzata per recuperare i contatti dal proprio database MySQL. Di seguito un esempio:
        
        *SELECT codice_utente AS uid, firstname AS name, lastname AS surname, "CELL" AS tel_type_1, cellulare as tel_type_1 FROM myContact WHERE codice_utente IS NOT NULL*
   
    
.. image:: /images/anagraficaClienti/MySQL.png