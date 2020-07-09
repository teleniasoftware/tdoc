===========================================================================
Migliora il supporto e la conversione dei clienti digitali sul tuo sito web
===========================================================================



Per offrire ai tuoi clienti un miglior supporto rapido, è possibile attivare 
sul tuo sito web una widget che permette di comunicare con gli agenti del
tuo contact center tramite chiamata, mail o chat.



.. figure:: /images/widget/widget_engcahin.png



La widget è connessa al TVox e accoda e distribuisce le interazioni che provengono da questi canali
all'agente più competente seguendo le regole aziendali, configurate a livello di skillset e priorità,
esattamente come avviene per il tradizionale canale telefonico.



Chiamata
========



Se un cliente desidera parlare con un operatore, possono essere messe a disposizione 3 modalità:


- Chiamata 

- Video chiamata

- Call Back



Chiamata e Video chiamata
-------------------------



La chiamata e la Video chiamata avviano una sessione audio e video tramite protocollo webrtc verso
un operatore TVox.
Come prima cosa viene richiesto al cliente di selezionare i dispositivi audio/video da utilizzare
durante la sessione di chiamta/video chiamata. La widget comunque è in grado di acquisire autonomamente
i dispositivi di default utilizzati dal browser.





Successivamente viene eseguito un test dei dispositivi che dura una decina di secondi, nel quale vengono
testati i dispositivi e la connessione.





Se il test va a buon fine vengono richieste al cliente tramite una form le informazioni personali necessarie per creare
un contatto sul TVox (es. nome, cognome, email, numero di telefono)
La form non è obbligatoria, può essere anche avviata la sessione in forma anonima e spetterà poi all'operatore che gestisce
l'iterazione richiedere se necessario queste informazioni al cliente e creare il contatto.
La form è configurabile tramite pannello di configurazione TVox, visionare la sessione FORM per 
imparare a configurare una form.

Dopo l'inserimento delle informazioni richieste sì può eseguire la vera e propria chiamata audio/video
ad un operatore.


.. figure:: /images/widget/Session.png
  :width: 600
  :align: center

Call Back
---------

Tramite la call back il cliente può richiedere di essere richiamto. Perchè la richiesta possa essere eseguita vengono
richieste tramite form (anche questa configurabile) le informazioni del cliente, tra cui il numero di telefono ed un 
eventuale messaggio che spiega il motivo della richiesta di chiamata.

Mail
====

Il canale Mail permette al cliente di generare un ticket sul TVox. Come per gli altri canali la generazione del ticket
avviene tramite una form configurabile.

Chat
====

Il canale Chat infine avvia una sessione di chat con un opertaore. All'avvio della sessione il cliente viene messo in una
coda in attesa che un operatore sia disponibile per chattare. Al termine della chat se sul TVox è configurato anche il canale
Mail si può rendere disponibile al cliente l'invio dello storico della chat tramite Mail.


Attiva la Widget
================

Il pannello di impostazioni TVox contiene una sezione dedicata alla configurazione e attivazione della widget.
Dopo la configurazione e attivazione viene generato uno script javascript da importare nel proprio sito web.
Il seguente video mostra come attivare la widget.

.. raw:: html

    <iframe width="560" height="315" src="https://www.youtube.com/embed/mlTQT4i0fck" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
 
|



Integra il tuo chatBOT in TVox Chat
===================================

.. figure:: /images/bot.png
    :align: right
    :figwidth: 150px


Se sul tuo website possiedi già un chat bot che interagisce con i tuoi clienti fornendogli informazioni 
sulle richieste più frequenti, è possibile collegare la nostra libreria widget al chat bot per 
far intervenire un operatore nel momento in cui il bot non fosse più in grado di soddisfare le 
richieste del cliente.

Con i metodi messi a disposizione dalla libreria Widget per il canale di chat è possibile monitorare lo stato
dei servizi e quindi configurare il proprio bot affinchè avvii una sessione di chat verso un agente Tvox solo se disponibile.

Nella documentazione tecnica della widget è presente una |demo_link| che mostra come instaurare una sessione di chat.
La demo implementa anche un semplicissimo bot che trasferisce la sessione di chat ad un agente disponibile.

**Libreria WIDGET** 

La libreria widget di Telenia è una libreria javascript che espone tutti i metodi per realizzare la propria applicazione widget.

Al seguente link trovate la |documentation_link| delle funzionalità della widget.




.. |documentation_link| raw:: html

    <a href="http://documentation.teleniasoftware.com/widget/version_2.0.html"target="_blank"> documentazione tecnica</a>


.. |demo_link| raw:: html

    <a href="http://documentation.teleniasoftware.com/widget/version_2.0.html"target="_blank"> demo</a>