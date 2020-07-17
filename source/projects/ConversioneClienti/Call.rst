========
Chiamata
========



Se un cliente desidera parlare con un operatore, possono essere messe a disposizione 3 modalità:


- Chiamata 

- Video chiamata

- Call Back



Chiamata e Video chiamata
=========================



La chiamata e la Video chiamata avviano una sessione audio e video tramite protocollo webrtc verso
un operatore TVox.
Come prima cosa viene richiesto al cliente di selezionare i dispositivi audio/video da utilizzare
durante la sessione di chiamta/video chiamata. La widget comunque è in grado di acquisire autonomamente
i dispositivi di default utilizzati dal browser.

.. figure:: /images/widget/CallTest.PNG
  :scale: 70
  :align: center

Successivamente viene eseguito un test dei dispositivi che dura una decina di secondi, nel quale vengono
testati i dispositivi e la connessione.

.. figure:: /images/widget/echoTest.PNG
  :scale: 70
  :align: center

Se il test va a buon fine vengono richieste al cliente tramite una form le informazioni personali necessarie per creare
un contatto sul TVox (es. nome, cognome, email, numero di telefono)
La form non è obbligatoria, può essere anche avviata la sessione in forma anonima e spetterà poi all'operatore che gestisce
l'iterazione richiedere se necessario queste informazioni al cliente e creare il contatto.
La form è configurabile tramite pannello di configurazione TVox, visionare la sessione FORM per 
imparare a configurare una form.

.. figure:: /images/widget/CallForm.PNG
  :scale: 70
  :align: center

Dopo l'inserimento delle informazioni richieste sì può eseguire la vera e propria chiamata audio/video
ad un operatore.


.. figure:: /images/widget/Session.png
  :width: 600
  :align: center

Call Back
=========

Tramite la call back il cliente può richiedere di essere richiamato. Perchè la richiesta possa essere eseguita vengono
richieste tramite form (anche questa configurabile) le informazioni del cliente, tra cui il numero di telefono ed un 
eventuale messaggio che spiega il motivo della richiesta di chiamata.

.. figure:: /images/widget/Callback.PNG
  :align: center