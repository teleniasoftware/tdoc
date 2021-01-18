=============================
Creare un IVR di navigazione
=============================

Quando il trattamento vocale previsto dal servizio di risposta o Contact Center non è sufficiente e si vogliono realizzare menù vocali interattivi è necessario creare un servizio di tipologia IVR. TVox prevede un’interfaccia WEB con cui realizzare, graficamente, menù di 
navigazione multilivello accessibile da Canali → Telefono → IVR.

La struttura del servizio IVR è organizzata in modo da definire una serie di “nodi” all’interno dei quali viene definita, per passi, la sequenza delle “azioni” da seguire nel nodo. Ogni servizio IVR prevede la definizione del nodo di ingresso/partenza da cui dipendono tutti i nodi che successivamente si intende implementare.

Quando si implementa un servizio IVR, il consiglio è di iniziare con la creazione di tutti i nodi presi singolarmente, configurando su di essi le azioni previste, ma senza procedere contestualmente alla gestione delle interconnesioni tra gli stessi.

Solo successivamente, avendo a disposizione tutti i nodi, sarà possibile creare agevolmente l'alberatura.

Per creare un nodo ex-novo, cliccare sul tasto verde col simbolo  *+* , compilare il campo  *Nome* , infine cliccare su  *Inserisci* :

.. image:: /images/IVR_creazione_nodo.png

Successivamente, è possibile configurare le azioni e/o le opzioni previste per il nodo utilizzando le opportune sezioni di configurazione, come si può notare dalla seguente immagine:

.. image:: /images/IVR_azioni_opzioni.png

Da considerare che, per la configurazione delle opzioni, è necessario aver già creato tutti i nodi previsti dallo schema generale dell'IVR, dal momento che tramite le opzioni si configura la connessione tra i rami.
