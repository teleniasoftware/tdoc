=====================================
LDAP
=====================================

Per configurare una sorgente dati che recupera i contatti da una server LDAP è necessario 
configurare i seguenti campi:

- **Dominio**: Nome di dominio univoco senza underscore (_), utilizzato per identificare il server LDAP esterno

- **Username**: Nome distinto (DN) o nome utente con privilegi di lettura sul ramo LDAP contenente i contatti da sincronizzare

- **Password**: Password dell'utente con privilegi di lettura sul ramo LDAP contenente i contatti da sincronizzare

- **Host**: Ip del server LDAP al quale si accederà tramite protocollo **HTTP**

- **Porta**: Gateway per il server LDAP (il valore predefinito per plain / starttls è 389, il valore predefinito è 636 per ssl).

- **Modalità di connessione**: Modalità di connessione al server LDAP esterno:

    - *PLAIN*: la connessione non è sicura (la porta di accesso 389 è l'impostazione predefinita) 
    - *SSL*: connessione protetta tramite SSL (Secure Socket Layer) (il gateway predefinito è 636) 
    - *STARTTLS*: connessione sicura tramite TLS (Transport Layer Security). TLS viene inizializzato dopo una normale connessione non crittografata (il valore predefinito del gateway è 389).

- **Directory filter**: Filtro da applicare agli utenti forniti dal server LDAP. Il parametro facoltativo è richiesto se nel DN Base ci sono anche oggetti che non sono utenti.

- **Dn Base User**: DN LDAP del ramo su cui effettuare la ricerca degli utenti.

- **User filter**: Filtro da applicare agli utenti forniti dal server LDAP. Il parametro facoltativo è richiesto se nel DN Base ci sono anche oggetti che non sono utenti.

- **Normalizza**: Abilitando la normalizzazione, la sincronizzazione pulisce i numeri di telefono ammettendo solo le cifre da 0 a 9 + * e # 

- **Keiro**: L'importazione dei contatti da un'origine LDAP richiede che fornisca una mappatura precisa tra gli attributi specificati sul server LDAP e i valori per T4you Address Book. NB: Va notato che è essenziale garantire la disponibilità degli attributi che identificano cognome e uid per ciascun contatto. Quando aggiungi un campo di telefono, posta o web, puoi selezionarne il valore e / o il tipo, se manca il tipo, "WORK" è impostato come predefinito. Un tipo è correlato a un valore, ad esempio tel_type_1 è correlato a tel_value_1. Possono essere mappati dieci campi personalizzati

- **Risorsa della sorgente**: Lista di porzioni di rubrica esposte da LDAP da selezionare per dichiarare quali contatti importare

- **Associazione campi rubrica t4you con campi rubrica LDAP**: Permette di rimappare i campi di un contatto LDAP sui campi del contatto della rubrica TVox

    - *Campo della rubrica T4you*: Campo della rubrica T4you a cui associare un campo LDAP
    - *Campo della rubrica Ldap*: Campo della rubrica LDAP da associare ad un campo della rubrica T4you

.. image:: /images/anagraficaClienti/Ldap.png