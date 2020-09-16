=====================================
ORACLE
=====================================

Per configurare una sorgente dati che recupera i contatti facendo una query su un database Oracle è necessario 
configurare i seguenti campi:

- **Versione**: Versione del database Oracle da cui si vogliono recuperare i contatti

- **Host**: Ip del database Oracle

- **Porta**: Porta su cui accedere al database Oracle

- **Username**: Indica l'username dell'utente Oracle usato per l'esecuzione della query

- **Password**: Indica la password dell'utente Oracle usato per l'esecuzione della query

- **Normalizza**: Abilitando la normalizzazione, la sincronizzazione pulisce i numeri di telefono ammettendo solo le cifre da 0 a 9, +, * e #. 

- **Query**: Indica la query personalizzata per recuperare i contatti dal proprio database Oracle. (**Esempio**: *SELECT codice_utente AS uid, firstname AS name, lastname AS surname, "CELL" AS tel_type_1, cellulare as tel_type_1 FROM myContact WHERE codice_utente IS NOT NULL*). Il risultato della query deve avere come nome delle colonne questi valori:
   
    - uid: dove il valore deve essere univoco
    - nome: in cui il valore non deve essere nullo
    - surname
    - othername
    - company
    - department
    - Street
    - city
    - region
    - postcode
    - country
    - tel_type_1: con i valori possibili: 'FAX','HOME','CELL','WORK','CELL_WORK','FAX_WORK','CELL_HOME','MAIN','OTHER'
    - ...
    - tel_type_10
    - tel_value_1
    - ...
    - tel_value_10
    - mail_type_1: con i valori possibili: 'INTERNET_WORK', 'INTERNET_HOME'
    - ...
    - mail_type_10
    - mail_value_1
    - ...
    - mail_value_10
    - web_type_1 con i valori possibili: 'WORK','HOME'
    - ...
    - web_type_3:
    - web_value_1
    - ...
    - web_value_3
    - vip
    - category
    - note

.. image:: /images/anagraficaClienti/Oracle.png