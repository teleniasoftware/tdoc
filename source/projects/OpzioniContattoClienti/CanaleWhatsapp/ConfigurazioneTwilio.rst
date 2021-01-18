
.. |TwilioDashboard| image:: ../../../images/WhatsApp/twilio_dashboard.png
.. |TwilioWhatsAppSenders| image:: ../../../images/WhatsApp/twilio_WhatsApp_senders.png
.. |TwilioWhatsAppNumbersList| image:: ../../../images/WhatsApp/twilio_WhatsApp_numbers_list.png

.. _twilio: https://www.twilio.com/
.. _documentazione: https://www.twilio.com/docs/whatsapp/tutorial/connect-number-business-profile

====================================
Configurazione Account Twilio
====================================


Twilio è un servizio che fornisce un insieme di API necessarie a |tvox| per inviare e ricevere messagi da WhatsApp.
Per configurare un account twilio, recarsi sul sito ufficiale twilio_ e premere il pulsante "Sign up" in alto a destra per iniziare la registrazione.


Una volta creato l'account ed effettuato il login, verrà visualizzata la Dashboard dell'account Twilio appena creato, da cui si possono recuperare l'account SID e il token di autenticazione dell'account.

|TwilioDashboard| 
 
| La numerazione telefonica di WhatsApp Business deve essere richiesta seguendo gli step indicati nella documentazione_ Twilio. 
| Una volta ottenuto il numero di WhatsApp, aprire il menù laterale della Dashboard, e selezionare la voce Programmable SMS → Senders → WhatsApp Senders. 

Se è già stata richiesta la numerazione telefonica, essa apparirà in questa lista.

|TwilioWhatsAppNumbersList|

| Per effettuare le configurazioni necessarie alla comunicazione tra TVox e Twilio ( e quindi WhatsApp ), basta selezionare il numero da configurare e modificare gli endpoint URL in questo modo:

| **Webhook URL for incoming messages**:  http://<tvox_url>/customerproxy/whatsapp/twilio
| **Webhook method for incoming messages URL**: HTTP Post
| **Status callback URL**: http://<tvox_url>/customerproxy/whatsapp/twilio_status
| **Webhook method for status callback URL**: HTTP Post

|TwilioWhatsAppSenders|