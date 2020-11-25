================================
Collega la tua soluzione Social
================================

Nel caso in cui la propria soluzione social non sia già presente tra i canali del TVox Omnichannel Contact Center è possibile integrarla mediante un apposito connettore dedicato.
Tale implementazione preventivamente licenziata consente di configurare servizi di contact center che possono far gestire ai propri agenti interazioni sul canale custom così implementato.

Dal punto di vista dell'architettura l'integrazione ai servizi multicanale prevede che sia implementato lato server un connettore tra TVox ed il servizio relativo allo specifico canale di comunicazione su cui si vuole interagire.
Lato client deve invece essere condivisa tra TVox e gestore di terze parti la configurazione dei codici utente e dei codici di servizio per consentire il dialogo con i processi del TVox che si occupano di smistare gli eventi ricevuti agli agenti preposti infunzione delle configurazioni effettuate a livello di skillset e strategia di distribuzione impostata dall'element manager del TVox.
Il connettore di multicanalità disponibile è basato sulle tecnologie SOAP oppure REST/JSON.

Nel caso di connettore SOAP il WSDL è scaricabile al seguente indirizzo:

.. note:: http://IP_TVOX/mc/cxf/soap?wsdl

L'endpoint soap che espone il servizio è:

.. note:: http://IP_TVOX/mc/cxf/soap

Nel caso di connettore basato su REST/JSON il WADL che descrive il servizio è scaricabile al seguente indirizzo:

.. note:: http://IP_TVOX/mc/cxf/rest?_wadl

.. important:: IP_TVOX è l'indirizzo IP del TVox su cui si vuole sviluppare l'integrazione

La struttura dati che viene interessata nel connettore per entrambe le tecnologie disponibili è la seguente:

.. code-block:: java    

    public enum CommandResult {
        SUCCESS,    
        FAILED
    }

    public enum SessionStatus {   
        NEW,    
        QUEUED,    /** Assegnata ad un agente */    
        BOOKED,    /** Un agente ha preso un carico la chiamata */    
        ASSIGNED,    
        CLOSED,    
        UNKNOW;
    }
