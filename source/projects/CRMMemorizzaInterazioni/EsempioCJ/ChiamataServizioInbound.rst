============================
Chiamata di servizio inbound
============================

Per prima cosa configuriamo i servizi di notifica per gestire i seguenti eventi:

.. toctree::
   :maxdepth: 1

   ChiamataServizioInbound/ChiamataRing
   ChiamataServizioInbound/ChiamataServizioRisposta
   ChiamataServizioInbound/ChiamataServizioAbbattuta

--------------------------

Dopo aver loggato l'operatore *op1* e averlo reso pronto sul canale telefonico, chiamiamo il numero di servizio del *Customer Care* dal contatto *Mario Rossi* (numero: *0452224600*).

Nel momento in cui la chiamata viene consegnata all'operatore, riceveremo una notifica di Chiamata in ring e il nostro Web Service produrrà sulla scheda contatto del CRM un risultato di questo tipo:

.. image:: ../../images/notificationService/ChiamataServizioInbound_ring.png

--------------------------

Quando l'operatore risponderà alla chiamata, riceveremo una notifica di Chiamata di servizio, risposta e aggiornando la scheda contatto vedremmo popolarsi la data/ora di risposta:

.. image:: ../../images/notificationService/ChiamataServizioInbound_answer.png

--------------------------

Infine, quando la chiamata verrà abbattuta, riceveremo una notifica di Chiamata di servizio, abbattuta e aggiornando la scheda contatto vedremmo popolarsi anche la data/ora di termine della chiamata:

.. image:: ../../images/notificationService/ChiamataServizioInbound_hangup.png