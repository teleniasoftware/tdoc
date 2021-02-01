=================================
Import Utenti da Active Directory
=================================

E' possibile importare su |tvox| utenti da Microsoft Active Directory configurando la connessione LDAP da interfaccia TAM.

Accedere all'interfaccia TAM con utenza amministrativa e selezionare "Users" - "LDAP Import" - "Configure"

Procedere con i passaggi: 

#. Selezionare la connessione LDAP (precedentemente configurata) da cui si vuole importare i dati (nell'esempio viene selezionata la connessione contoso).
#. Selezionare la corrispondenza tra i campi utente in |tvox| (TAM Data) e i campi utente in LDAP (LDAP Data).
#. Salvare con il tasto *Save*.
#. Selezionare "Configure LDAP Connection" per configurare i ruoli di default da attribuire agli utenti in fase di import.

.. image:: /images/ActiveDirectory/LDAP_IMPORT_CONFIGURE_STEP1.png

Selezionare i ruoli di default che devono assumere gli utenti che andiamo a importare. Nell'esempio si desidera che gli utenti importati abbiano ruolo "TVox User" e "TVox Agent".
Salvare con il tasto *Save*.

.. image:: /images/ActiveDirectory/LDAP_IMPORT_CONFIGURE_STEP2.png

Tornare all'interfaccia di import e selezionare il tasto "Retrive" per vedere i possibili utenti da importare via LDAP.
Selezionare gli utenti che intendiamo importare e confermiamo con il tasto "Import".

.. image:: /images/ActiveDirectory/LDAP_IMPORT_IMPORT_STEP1.png

Sucessivamente viene presentata la schermata che indica lo stato di avanzamento dell'importazione.

.. image:: /images/ActiveDirectory/LDAP_IMPORT_IMPORT_STEP2.png

A importazione conclusa troveremo gli utenti importati su OCC

.. image:: /images/ActiveDirectory/LDAP_IMPORT_RESULT.png

Se in fase di configurazione LDAP non si configura uno dei ruoli TVox come Default per l'import, l'utente viene importato con il solo ruolo TAM user e sarà visibile solo da interfaccia *Users* di TAM manager.
Tramite TAM Manager si potrà, successivamente, completare la configurazione dei ruoli.

.. image:: /images/ActiveDirectory/LDAP_IMPORT_IMPORT_STEP3.png

.. image:: /images/ActiveDirectory/LDAP_IMPORT_IMPORT_STEP4.png

