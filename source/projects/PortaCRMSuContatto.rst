.. _PortaCRMSuContatto:

=======================
Porta il CRM sul contatto TVOX
=======================

A partire dalla release TVox 22.0.17, entrando sulla scheda anagrafica di un contatto, azienda o utente, è possibile avere a disposizione una tab che al suo interno contiene un iframe verso il tuo CRM mostrando la pagina con le informazioni del tuo contatto.
In alternativa, qualora l'applicativo non permetta di essere aperto all'interno di un'iframe, è possibile avere a dispozione un pulsante, sul dettaglio del contatto, che aprirà una nuova scheda sul browser

E' possibile abilitare e configurare gli URL da aprire e la modalità accedendo all'OCC del TVOX, nella sezione Impostazioni --> Avanzate --> TVox Client --> Integrazione con CRM.

Requisiti sulla macchina che ospita il CRM
============================================

- sul file /etc/apache2/apache2.conf (o qualora sia configurato l'override in .htcaccess), per la cartella che contiene l'applicativo tra le varie opzioni aggiungere:

.. code-block:: javascript

  Header set Access-Control-Allow-Credential true 
  Header set Access-Control-Allow-Origin <dominio/ip> dal quale permettere accesso (nel nostro caso, del TVox che fa le richieste)

Questo per permettere il settaggio dei cookies necessari per l'autenticazione


In Generale (sull'applicativo CRM da integrare al TVox)
===============================================

- Per poter utilizzare la modalità iframe, il sistema deve poter essere predisposto ad essere visualizzato in iframe (es google.com non lo è)
- Il sistema deve permettere richieste cross-origin
- il sistema deve prevedere un processo di autenticazione custom che utilizza l'accessToken del TVox per autenticare un utente nel CRM (facoltativo)