=======================
Creazione app Microsoft
=======================

#. L'amministratore effettua il login sul portale Azure: https://portal.azure.com
#. Selezionare lo strumento ``Registrazioni per l'App`` o andare all'indirizzo `App Registration`_

|01-azure-portal|

3. Premere su "Nuova registrazione".

|02-new-registration|

4. Dare un nome all'applicazione e premere ``Registra`` e attendere la creazione.


|03-app-name|


5. Dai dettagli dell'App copiare il valore ``ID applicazione`` (App ID) e salvarselo. Questo valore dovrà essere successivamente inserito in OCC.

.. note:: L'App ID può essere recuperato in qualsiasi momento.

|04-app-id-save|


6. Dal menu laterale selezionare ``Certificati e segreti``.

7. Nella sezione ``Segreti client`` premere ``Nuovo segreto client``

|05-app-secret|

8. Dare un nome qualsiasi al segreto e come ``Scadenza`` selezionare ``Mai``. Premere ``Aggiungi``.

|06-app-secret-create|


9. Copiare e salvare in un posto sicuro il valore del segreto (App Secret). 

.. attention:: **Non sarà più possibile recuperare il valore del segreto in futuro**. In caso di smarrimento del segreto sarà necessario crearne uno nuovo e riconfigurare le credenziali su OCC.

|07-app-secret-save|



10. Entrare nella sezione ``Autorizzazione API``.

|08-app-authorization-enter|

12. Premere su ``Aggiungi un'autorizzazione``.

|09-app-authorization-add|

13. Selezionare le API ``Microsoft Graph`` dall'elenco.

|10-app-authorization-select-microsoft-graph|

14. Scegliere le autorizzazioni di tipo ``Autorizzazioni delegate``.

|11-app-authorization-select-delegated-permissions|

15. Nella input box di ricerca inserire ``offline_access``, selezionare la checkbox corrispondente al permesso ``offline_access`` nell'elenco in basso.

|12-app-authorization-offline_access|

16. Cercare e aggiungere anche i permessi:

    * openid
    * Presence.Read.All
    * User.ReadBasic.All


17. Premere ``Aggiungi autorizzazioni``

#. L'elenco autorizzazioni si presenterà come nella prossima immagine.
#. Premere il pulsante ``Concedi consenso amministratore per 'Nome Azienda'`` per attivare i permessi.

|13-app-authorization-list|

18. A questo punto se è tutto corretto la lista dei permessi indicherà che sono stati concessi dall'amministratore.

|14-app-authorization-list-ok|

19. Dal menu a sinistra, navigare verso la sezione ``Autenticazione``

|19-autenticazione|

20. Cliccare quindi il pulsante ``Aggiungi una piattaforma``
21. Dal menu proposto selezionare quindi la tipologia ``Web``
22. Copiare l’indirizzo di reindirizzamento fornito da OCC in fase di creazione di una nuova applicazione Microsoft e incollarlo sotto la voce ``URI di reindirizzamento dell'applicazione`` e cliccare infine sul tasto ``Configura``.

|22-callback-url|


23. I valori di ``App ID`` e ``App Secret`` ora possono essere utilizzati in OCC per creare le credenziali



.. _Microsoft Graph API: https://docs.microsoft.com/en-us/graph/overview?view=graph-rest-1.0

.. _App Registration: https://portal.azure.com/?l=it.it-it#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade



.. |01-azure-portal| image:: /images/MicrosoftTeams/AppPermissions/01-azure-portal.png
.. |02-new-registration| image:: /images/MicrosoftTeams/AppPermissions/02-new-registration.png
.. |03-app-name| image:: /images/MicrosoftTeams/AppPermissions/03-app-name.png

.. |04-app-id-save| image:: /images/MicrosoftTeams/AppPermissions/04-app-id-save.png
.. |05-app-secret| image:: /images/MicrosoftTeams/AppPermissions/05-app-secret.png
.. |06-app-secret-create| image:: /images/MicrosoftTeams/AppPermissions/06-app-secret-create.png
.. |07-app-secret-save| image:: /images/MicrosoftTeams/AppPermissions/07-app-secret-save.png

.. |08-app-authorization-enter| image:: /images/MicrosoftTeams/AppPermissions/08-app-authorization-enter.png
.. |09-app-authorization-add| image:: /images/MicrosoftTeams/AppPermissions/09-app-authorization-add.png
.. |10-app-authorization-select-microsoft-graph| image:: /images/MicrosoftTeams/AppPermissions/10-app-authorization-select-microsoft-graph.png
.. |11-app-authorization-select-delegated-permissions| image:: /images/MicrosoftTeams/AppPermissions/11-app-authorization-select-delegated-permissions.png
.. |12-app-authorization-offline_access| image:: /images/MicrosoftTeams/AppPermissions/12-app-authorization-offline_access.png
.. |13-app-authorization-list| image:: /images/MicrosoftTeams/AppPermissions/13-app-authorization-list.png
.. |14-app-authorization-list-ok| image:: /images/MicrosoftTeams/AppPermissions/14-app-authorization-list-ok.png
.. |19-autenticazione| image:: /images/MicrosoftTeams/AppPermissions/19-autenticazione.png
.. |22-callback-url| image:: /images/MicrosoftTeams/AppPermissions/22-callback-url.gif







