========
Chiamata
========



Se un cliente desidera parlare con un operatore, possono essere messe a disposizione 3 modalità:


- Chiamata 

- Video chiamata

- Call Back



Chiamata e Video chiamata
=========================



La chiamata e la video chiamata avviano una sessione audio e video tramite protocollo webrtc verso
un operatore di |tvox|.
Come prima cosa viene richiesto al cliente di selezionare i dispositivi audio/video da utilizzare
durante la sessione di chiamata. La widget è in grado di acquisire autonomamente
i dispositivi di default utilizzati dal browser.

.. figure:: /images/widget/CallTest.PNG
  :scale: 70
  :align: center

Successivamente, viene eseguito un test che dura una decina di secondi, nel quale vengono
verificati i dispositivi e la connessione.

.. figure:: /images/widget/echoTest.PNG
  :scale: 70
  :align: center

Se il test va a buon fine, un form richiede al cliente di inserire le informazioni personali necessarie per creare
un contatto su |tvox| (es. nome, cognome, email, numero di telefono).

.. note:: La richiesta di dati personali tramite form può essere disabilitata tramite OCC (di default è abilitata). Per sapere come configurare un form, visionare la sezione :ref:`ConfigurazioneForm`

Se il form non è abilitato, il cliente si presenterà al contact center in forma anonima, sarà cura dell'operatore richiedere queste informazioni al cliente e creare il contatto.

.. figure:: /images/widget/CallForm.PNG
  :scale: 70
  :align: center

Dopo questa fase, è possibile eseguire la chiamata audio/video con l'operatore.


.. figure:: /images/widget/Session.png
  :width: 600
  :align: center

CallBack
=========

Tramite la CallBack il cliente può richiedere di essere contattato. Per effettuare la richiesta, il cliente dovrà compilare un form con le proprie informazioni di contatto, tra cui il numero di telefono ed un 
messaggio che spieghi il motivo della richiesta.

.. figure:: /images/widget/Callback.PNG
  :scale: 70
  :align: center