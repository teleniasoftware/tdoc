========================================
IVR senza integrazioni a sistemi esterni
========================================

Se dovete realizzare un IVR che non necessita di integrazioni a sistemi esterni, potete 
farlo tramite il TVox OCC nella sezione **Canali → Telefono → IVR**

Cosa è possibile configurare
-----------------------------

* Prerequisiti
    Prima di procedere alla configurazione di un IVR è necessario aver progettato lo schema che si intende realizzare, averlo cioè disegnato.
    Questo permette di aver chiari i passaggi necessari per la configurazione stessa.
    Uno schema adeguato deve rappresentare tutti i nodi che compongono l'alberatura IVR che si vuole realizzare ed i collegamenti logici tra i nodi stessi.

    Di seguito un'immagine a titolo di esenpio:

    .. image:: /images/IVR_esempio_schema.png

* Creare un IVR di navigazione
    Quando il trattamento vocale previsto dal servizio di risposta o Contact Center non è sufficiente e si vogliono realizzare menù vocali interattivi è necessario creare un servizio di tipologia IVR. TVox prevede un’interfaccia WEB con cui realizzare, graficamente, menù di 
    navigazione multilivello accessibile da Canali → Telefono → IVR.

    La struttura del servizio IVR è organizzata in modo da definire una serie di “nodi” all’interno dei quali viene definita, per passi, la sequenza delle “azioni” da seguire nel nodo. Ogni servizio IVR prevede la definizione del nodo di ingresso/partenza da cui dipendono tutti i nodi che successivamente si intende implementare.

    Nell'immagine di esempio, le caselle con bordo rosso costituiscono i nodi, le caselle con bordo azzurro costituiscono delle azioni.

    Quando si implementa un servizio IVR, il consiglio è di iniziare con la creazione di tutti i nodi presi singolarmente, configurando su di essi le azioni previste, ma senza procedere contestualmente alla gestione delle interconnesioni tra gli stessi.

    Solo successivamente, avendo a disposizione tutti i nodi, sarà possibile creare agevolmente l'alberatura.

    Per creare un nodo ex-novo, cliccare sul tasto verde col simbolo + e compilare il campo Nome, infine cliccare su Inserisci:

    .. image:: /images/IVR_creazione_nodo.png

    Successivamente, è possibile configurare le azioni e/o le opzioni previste per il nodo utilizzando le opportune sezioni di configurazione, come si può notare dalla seguente immagine:

    .. image:: /images/IVR_azioni_opzioni.png

    Da considerare che, per la configurazione delle opzioni, è necessario aver già creato tutti i nodi previsti dallo schema generale dell'IVR, dal momento che tramite le opzioni si configura la connessione tra i rami.


* Riprodurre Messaggi Audio
    Per poter riprodurre un messaggio audio, quando si configura un nodo va selezionata l'azione **Esegui file audio**.
    
    .. image:: /images/IVR_play_audio1.png
    
    Selezionando tale azione, verrà proposto un menu a scelta con l'elenco di tutti i messaggi audio caricati su TVox. 
    Nel caso in cui l'audio precede una scelta tra più opzioni, è opportuno selezionare anche il flag *Interrompibile* che consente di selezionare tramite DTMF l'opzione desiderata anche prima che la riproduzione del messaggio audio termini.

    .. image:: /images/IVR_play_audio2.png



* Collezionare digits da tastiera
    Questa azione consente all'utente di inviare tramite DTMF dei digit che vengono memorizzati su una variabile di sistema salvata su database:

    .. image:: /images/IVR_colleziona_digit1.png

    L'azione consente di impostare:

        -   Un file audio proposto per richiedere al chiamante la digitazione di una o più cifre che si intende siano salvate sul database TVox Communication. Il file va selezionato tra quelli disponibili nel TVox Communication che sono stati definiti in Gestione ⇒ Messaggi vocali.
        -   Numero di digit: il numero massimo di digit che sono accettabili nel nodo corrente
        -   Variabile di riferimento: identifica la variabile nella quale vengono memorizzati i digit inseriti dal chiamante.La variabile viene salvata in corrispondenza del campo popupinfo della tabella ast_calls_'yyyymm' nel formato 'nome variabile'='digit inserite'.
        -   Tempo di attesa: va indicato il tempo massimo di attesa in secondi affinchè il chiamante possa indicare tutte i digit richiesti. Trascorso questo timeout la chiamata prosegue al passo successivo del nodo corrente.
        -   Lookup  personalizzato: il contenuto della variabile qui collezionata può essere utilizzato per effettuare una lookup sul TVox Client del contatto sulla base di un campo custom presente nella rubrica. Se non viene selezionato alcun valore si intende che il lookup del contatto avviene in modalità standard ovvero su base clid. Altrimenti il match tra valore della variabile e contenuto del campo custom ottiene il contatto desiderato. Ad esempio è possibile identificare un contatto che chiama il servizio IVR sulla base del suo codice utente se quest'ultimo è stato salvato in rubrica in uno dei campi custom disponibili.
        -   Modalità di ricerca per lookup: qualora sia stata configurata una lookup personalizzata è necessario definire la modalità in cui viene ricercato il match tra variabile corrente e campo custom della rubrica. Tale valore non assume rilevanza se il parametro precedente non è stato configurato.

.. image:: /images/IVR_colleziona_digit2.png

* Riprodurre i digits recuperati
* Impostare variabili di chiamata
* Chiamare un numero interno
* Chiamare un numero esterno
* Trasferire la chiamata ad un servizio specifico
* Mandare la chiamata in casella vocale
