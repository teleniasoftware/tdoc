====================
Creazione App Google
====================

1. L'amministratore effettua il login sul portale Google Cloud Console: https://console.cloud.google.com/
2. Accettare i termini e le condizioni per l'utilizzo del servizio

|accept-terms|

3. Premere su ``Seleziona un progetto``.

|select-project|


4. Premere su ``Nuovo progetto``.

|new-project-button|


4. Dare un nome all'applicazione, premere ``Crea`` e attendere la creazione.

|new-project-informations|


5. Dal menu sulla sinistra, accedere alla sezione ``API e servizi > Schermata di consenso OAuth``.

|oauth-page-button|


6. Selezionare ``Esterno`` come tipologia di consenso.

|oauth-page-type|


7. Inserire il nome dell'applicazione e l'indirizzo email per l'assistenza.

|oauth-page-informations-1|


8. Procedere alla sezione ``Utenti di prova``.


9. Aggiungere eventuali utenti di prova con i quali si potrà accedere fino a che l'applicazione non sarà verificata da parte di Google e salvare.

|oauth-page-test-users|


10. Premere il pulsante ``Crea credenziali``.

|credentials-button|


11. Selezionare la tipologia ``ID client OAuth``.

|credentials-button-type|


12. Selezionare "Applicazione web" sotto la voce ``Tipo di applicazione``.


13. Copiare l'indirizzo di reindirizzamento fornito da OCC in fase di creazione di una nuova applicazione Google e incollarlo sotto la voce ``URI di reindirizzamento autorizzati``.

|credentials-page-informations|


14. Dalla schermata di successo copiare i valori di ``Client ID`` e ``CLient secret`` e salvarli in un luogo sicuro.

|credentials-page-success|


15. Da OCC, inserire i valori precedentemente salvati in fase di creazione di una nuova applicazione.

|credentials-occ-config|


Abilitazione al canale Support
==============================

Se lato OCC si abilita il canale support, abilitare le API di Gmail dalla configurazione dell'applicazione google seguendo i seguenti punti: 

1. Accedere alla sezione ``Dashboard`` dal menu a sinistra.

2. Premere il pulsante ``Abilita API e servizi``.

|support-enable-api|

3. Cercare "Gmail" nella casella di testo proposta.

4. Selezionare il risultato ``Gmail API`` e  cliccare il pulsante ``Abilita``.

|support-add-gmail|


Verifica e pubblicazione dell'applicazione
==========================================

1. Accedere alla sezione ``Schemata consenso OAuth`` dal menu a sinistra.

2. Premere il pulsante ``Pubblica l'app``.

|publish-app-button|

3. Se richiesto, fornire tutte le informazioni necessarie al fine di verificare l'app. Potrebbe essere richiesto l'invio di un video di presentazione che dimostra l'utilizzo dell'applicazione.


.. |accept-terms| image:: /images/Google/AppPermissions/1.png

.. |select-project| image:: /images/Google/AppPermissions/2.png

.. |new-project-button| image:: /images/Google/AppPermissions/3.png
.. |new-project-informations| image:: /images/Google/AppPermissions/4.png

.. |oauth-page-button| image:: /images/Google/AppPermissions/5.png
.. |oauth-page-type| image:: /images/Google/AppPermissions/6.png
.. |oauth-page-informations-1| image:: /images/Google/AppPermissions/7.png
.. |oauth-page-informations-2| image:: /images/Google/AppPermissions/8.png
.. |oauth-page-authorizations| image:: /images/Google/AppPermissions/9.png
.. |oauth-page-test-users| image:: /images/Google/AppPermissions/10.png

.. |credentials-button| image:: /images/Google/AppPermissions/11.png
.. |credentials-button-type| image:: /images/Google/AppPermissions/12.png
.. |credentials-page-informations| image:: /images/Google/AppPermissions/13.png
.. |credentials-page-success| image:: /images/Google/AppPermissions/14.png
.. |credentials-occ-config| image:: /images/Google/AppPermissions/15.png

.. |support-enable-api| image:: /images/Google/AppPermissions/16.png
.. |support-add-gmail| image:: /images/Google/AppPermissions/17.png

.. |publish-app-button| image:: /images/Google/AppPermissions/18.png







