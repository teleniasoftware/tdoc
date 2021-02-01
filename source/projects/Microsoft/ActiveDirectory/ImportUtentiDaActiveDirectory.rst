=================================
Import Utenti da Active Directory
=================================

E' possibile importare su |tvox| utenti da Microsoft Active Directory configurando la connessione LDAP da interfaccia TAM.

Accedere ad interfaccia TAM con utenza amministrativa e selezionare "Users" - "LDAP Import" - "Configure"

Selezionare la connessione LDAP da cui si vuole importare i dati (nell'esempio viene selezionata la connessione contoso).
Selezionare quindi la corrispondenza tra i campi utente in |tvox| (TAM Data) e i campi utente in LDAP (LDAP Data).
Salvare con il tasto Save.

.. image:: /images/ActiveDirectory/LDAP_IMPORT_CONFIGURE_STEP1.png

Selezionare "Configure LDAP Connection".
E selezionare i ruoli di default che devono assumere gli utenti che andiamo a importare. Nell'esempio si desidera che gli utenti importati abbiano ruolo "TVox User" e "TVox Agent".
Salvare con il tasto Save.

.. image:: /images/ActiveDirectory/LDAP_IMPORT_CONFIGURE_STEP2.png

Tornare quindi all'interfaccia di import e selezionare il tasto "Retrive" per vedere i possibili utenti da importare da LDAP.
Selezionare successivamente gli utenti che intendiamo importare e confermare con il tasto "Import".

.. image:: /images/ActiveDirectory/LDAP_IMPORT_IMPORT_STEP1.png

Viene presentata quindi la schermata che indica lo stato di avanzamento dell'importazione.

.. image:: /images/ActiveDirectory/LDAP_IMPORT_IMPORT_STEP2.png

A importazione conclusa troveremo gli utenti importati su OCC

.. image:: /images/ActiveDirectory/LDAP_IMPORT_RESULT.png

Se in fase di configurazione LDAP non si configura uno dei ruoli TVox come Default per l'import, l'utente viene importato con il solo ruolo Tam user e sarà visiabile solo da interfaccia Users di TAM manager.
Potrà poi eventualmente essere completato dando gli opportuni ruoli da TAM Manager.

.. image:: /images/ActiveDirectory/LDAP_IMPORT_IMPORT_STEP3.png

.. image:: /images/ActiveDirectory/LDAP_IMPORT_IMPORT_STEP4.png

