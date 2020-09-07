================================
Collezionare digits da tastiera
================================

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