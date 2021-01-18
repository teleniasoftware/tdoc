================================================
Trasferire la chiamata ad un servizio specifico
================================================

Si tratta di una delle azioni maggiormente utilizzate nei nodi IVR. Il trasferimento della chiamata a servizio può essere effettuato in due modalità

-   **Carica un servizio**:

    Con questa azione è possibile trasferire il controllo della chiamata ad un altro servizio TVox, di qualunque tipologia

    .. image:: /images/IVR_carica_servizio1.png

    Nel campo *Servizio* va indicato il servizio verso il quale trasferire la chiamata. Il parametro *Attiva registrazione*, se selezionato, indica che la chiamata trasferita al servizio verrà registrata

    .. image:: /images/IVR_carica_servizio2.png


-   **Carica un servizio esteso**:

    Questa azione è analoga alla precedente, ma ne estende le funzionalità con l'aggiunta di  ulteriori paramentri:

    .. image:: /images/IVR_carica_servizio_esteso1.png

    -   **Etichetta aggiuntiva**: è una descrizione aggiuntiva per identificare il servizio. Questo valore viene presentato nel |client| dell'agente cui la chiamata viene proposta, ed è indicato anche nei report
    -   **Priorità del servizio**: identifica la priorità che il servizio assume per la chiamata corrente. La priorità del servizio entra in gioco nel momento in cui condivide lo skillset con altri servizi
    -   **Numero massimo di chiamate gestite dal servizio**: è il limite massimo di chiamate che il servizio può gestire provenienti dal nodo corrente
    -   **Limite chiamate in attesa nel servizio**: è il limite massimo di chiamate provenienti dal nodo corrente che il servizio può mantenere in coda
    -   **Limite proporzionale agli agenti loggati**: sempre per le chiamate che transitano nel nodo corrente, è il limite delle chiamate in coda proporzionale al numero di agenti loggati negli skillset configurati per il servizio
    -   **Registrazione della chiamata su servizio**: analoga al caso precedente
    -   **Skillset [n]**: é possibile indicare gli skillset che dovranno essere interassati dalle chiamate provenienti dal nodo corrente in ordine di priorità. Lo skillset impostato su *Skillset 1* sarà il primo interessato

    .. image:: /images/IVR_carica_servizio_esteso2.png

