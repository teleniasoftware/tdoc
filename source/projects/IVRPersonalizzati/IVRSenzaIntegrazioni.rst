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

        -   **File audio**: è un messaggio necessario per richiedere al chiamante la digitazione di una o più cifre che si intende siano salvate sul database TVox Communication. Il file va selezionato tra quelli disponibili nel TVox Communication che sono stati definiti in Gestione ⇒ Messaggi vocali.
        -   **Numero di digit**: il numero massimo di digit che sono accettabili nel nodo corrente
        -   **Variabile di riferimento**: identifica la variabile nella quale vengono memorizzati i digit inseriti dal chiamante.
        -   **Tempo di attesa**: va indicato il tempo massimo di attesa in secondi affinchè il chiamante possa indicare tutte i digit richiesti. Trascorso questo timeout la chiamata prosegue al passo successivo del nodo corrente.
        -   **Lookup  personalizzato**: il contenuto della variabile qui collezionata può essere utilizzato per effettuare una lookup sul TVox Client del contatto sulla base di un campo custom presente nella rubrica. Se non viene selezionato alcun valore si intende che il lookup del contatto avviene in modalità standard ovvero su base clid. Altrimenti il match tra valore della variabile e contenuto del campo custom ottiene il contatto desiderato. Ad esempio è possibile identificare un contatto che chiama il servizio IVR sulla base del suo codice utente se quest'ultimo è stato salvato in rubrica in uno dei campi custom disponibili.
        -   **Modalità di ricerca per lookup**: qualora sia stata configurata una lookup personalizzata è necessario definire la modalità in cui viene ricercato il match tra variabile corrente e campo custom della rubrica. Tale valore non assume rilevanza se il parametro precedente non è stato configurato.

    .. image:: /images/IVR_colleziona_digit2.png

* Riprodurre i digits recuperati
    Questa azione permette di riprodurre i digit inviati (vedi voce precedente) e memorizzati su una variabile.
    
    .. image:: /images/IVR_riproduci_digit1.png
    
    Va impostato il nome della variabile precedentemente definita, il cui contenuto numerico viene riprodotto dal sistema.

    .. image:: /images/IVR_riproduci_digit2.png
        

* Impostare variabili di chiamata
    Con questa azione è possibile definire una variabile per le chiamate che vengono processate dal nodo, ed utilizzarla per memorizzare dei valori:

    .. image:: /images/IVR_imposta_variabile1.png

    Oltre ad impostare il nome, è possibile impostare il valore da assegnare alla variabile e decidere se renderla disponibile nei report tramite un apposito flag:

    .. image:: /images/IVR_imposta_variabile2.png

    La variabile viene memorizzata su database nelle tabelle storiche ast_calls_yyyymm in corrispondenza del campo *popupinfo* ed il formato con cui viene riportato il valore è *TIVR_[nome variabile]=[valore]*.

* Chiamare un numero interno
    Con questa azione è possibile trasferire la chiamata ad un numero interno.

    .. image:: /images/IVR_chiama_interno1.png

    Nel box va impostato il numero verso il quale passare a chiamata:

    .. image:: /images/IVR_chiama_interno2.png



* Chiamare un numero esterno
    Analogamente all'azione precedente, questa consente il trasferimento verso un numero esterno a TVox:

    .. image:: /images/IVR_chiama_esterno1.png


    I parametri previsti consentono di impostare:

    -   **Numero da chiamare**: il numero esterno cui la chiamata deve essere trasferita
    -   **Tempo di ring**: il tempo massimo di ring in secondi
    -   **Tentativi**: il numero massimo di tentativi in attesa  della risposta da parte del numero chiamato. Superato tale numero senza risposta, la chiamata passa al nodo successivo dell'ivr.
    -   **Abilitazione**: va scelta l'abilitazione da utilizzare per il trasferimento. Il numero da chiamare, impostato nel primo campo, deve contenerere eventuali access code previsti dall'abilitazione.
    -   **Registrazione della chiamata**: Tramite questo flag è possibile registrare la chiamata trasferita esternamente

    .. image:: /images/IVR_chiama_esterno2.png

* Trasferire la chiamata ad un servizio specifico
    Si tratta di una delle azioni maggiormente utilizzate nei nodi IVR. Il trasferimento della chiamata a servizio può essere effettuato in due modalità

    -   **Carica un servizio**:

        Con questa azione è possibile trasferire il controllo della chiamata ad un altro servizio TVox, di qualunque tipologia

        .. image:: /images/IVR_carica_servizio1.png

        Nel campo *Servizio* va indicato il servizio verso il quale trasferire la chiamata. Il parametro *Attiva registrazione*, se selezionato, indica che la chiamata trasferita al servizio verrà registrata

        .. image:: /images/IVR_carica_servizio2.png

    
    -   **Carica un servizio esteso**:

        Questa azione è analoga alla precedente, ma ne estende le funzionalità con l'aggiunta di  ulteriori paramentri:

        .. image:: /images/IVR_carica_servizio_esteso1.png

        -   *Etichetta aggiuntiva*: è una descrizione aggiuntiva per identificare il servizio. Questo valore viene presentato nel TVox Client dell'agente cui la chiamata viene proposta, ed è indicato anche nei report
        -   *Priorità del servizio*: identifica la priorità che il servizio assume per la chiamata corrente. La priorità del servizio entra in gioco nel momento in cui condivide lo skillset con altri servizi
        -   *Numero massimo di chiamate gestite dal servizio*: è il limite massimo di chiamate che il servizio può gestire provenienti dal nodo corrente
        -   *Limite chiamate in attesa nel servizio*: è il limite massimo di chiamate provenienti dal nodo corrente che il servizio può mantenere in coda
        -   *Limite proporzionale agli agenti loggati*: sempre per le chiamate che transitano nel nodo corrente, è il limite delle chiamate in coda proporzionale al numero di agenti loggati negli skillset configurati per il servizio
        -   *Registrazione della chiamata su servizio*: analoga al caso precedente
        -   *Skillset [n]*: é possibile indicare gli skillset che dovranno essere interassati dalle chiamate provenienti dal nodo corrente in ordine di priorità. Lo skillset impostato su *Skillset 1* sarà il primo interessato

        .. image:: /images/IVR_carica_servizio_esteso2.png




* Mandare la chiamata in casella vocale
    E' possibile inoltrare la chiamata alla casella vocale del servizio IVR tramite questa azione:

    .. image:: /images/IVR_casella_vocale1.png

    Il messaggio vocale che viene lascaito dal chiamante è registrato e la registrazione viene inviata come allegato all'indirizzo email specificato in fase di configurazione dell'azione nel campo *email*:

    .. image:: /images/IVR_casella_vocale2.png

    E' possibile in alternativa utilizzare la casella vocale del servizio ivr stesso ponendo la spunta sulla voce *Utilizza la casella vocale del servizio ivr*. In questo caso, la configurazione deve essere completata nella sezione *Generale*:

    .. image:: /images/IVR_casella_vocale3.png


