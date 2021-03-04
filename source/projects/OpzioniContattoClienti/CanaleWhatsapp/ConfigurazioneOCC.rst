.. |AbilitazioneSuServizio| image:: ../../../images/Whatsapp/abilitazione_servizio.png

.. |AggiuntaNumeroSuServizio| image:: ../../../images/Whatsapp/aggiunta_numero_servizio.png

.. |AbilitazioneSuProfilo| image:: ../../../images/Whatsapp/abilitazione_profilo.png

.. |AssegnazioneServizioWidget| image:: ../../../images/Whatsapp/assegnazione_servizio_widget.png

.. |ImpostazioniAvanzate| image:: ../../../images/Whatsapp/impostazioni_avanzate.png


====================================
Configurazione OCC
====================================

L'accesso al canale WhatsApp può essere reso disponibile su sito web attraverso la widget, nella quale viene presentato un QRcode che deve essere scansionato con uno smartphone per essere rediretti al contatto WhatsApp dell'azienda.

In alternativa, sempre su widget, lo stesso canale può essere cliccato per essere redirezionati all'applicazione web di Whatsapp.

Se, invece, l'utente ha già memorizzato in rubrica il numero telefonico dell'account Whatsapp dell'azienda, è possibile avviare una sessione chat direttamente dall'app WhatsApp.

Per esporre il QRcode su widget, è necessario seguire i seguenti step:

- Nella sezione OCC Impostazioni→Avanzate→Canale Chat, abilitare la voce WhatsApp ed inserire nei due campi sottostanti i corrispettivi SID e token di autenticazione forniti da Twilio. Per verificare la correttezza del SID e del token, è possibile eseguire un test di autenticazione premendo sul pulsante "Verifica Account".

|ImpostazioniAvanzate|


- Nella sezione Servizi, va creato un nuovo servizio o selezionato uno già esistente

- Va quindi aggiunto il canale chat al servizio, e abilitata la voce WhatsApp

|AbilitazioneSuServizio|

- Inserire nel campo "Numero di telefono Twilio" il numero aquistato e configurato sulla piattaforma Twilio.

|AggiuntaNumeroSuServizio|

- Nella sezione utenti, selezionare il profilo di uno o più agenti e abilitare la voce relativa al canale WhatsApp dopo aver abilitato il canale Chat. Il parametro "Massime interazioni" definisce il numero di interazioni che l'agente può avere in contemporanea su |client|

|AbilitazioneSuProfilo|

Una volta configurati i profili degli agenti ed i servizi, va associato il servizio alla widget in Impostazioni→Widget→Widget in uso→Canali→WhatsApp

|AssegnazioneServizioWidget|

