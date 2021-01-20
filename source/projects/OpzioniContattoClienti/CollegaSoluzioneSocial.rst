================================
Collega la tua soluzione Social
================================

Nel caso in cui la propria soluzione social non sia già presente tra i canali disponibili di |tvox|, è possibile integrarla mediante un apposito connettore dedicato.

Tale implementazione, preventivamente licenziata, consente di configurare il canale personalizzato su servizi di contact center.

Dal punto di vista dell'architettura, l'integrazione ai servizi multicanale prevede che sia implementato lato server un connettore tra |tvox| ed il servizio relativo allo specifico canale di comunicazione su cui si vuole interagire.

Lato client deve invece essere condivisa tra |tvox| e gestore di terze parti la configurazione dei codici utente e dei codici di servizio per consentire il dialogo tra i due sistemi.

Il connettore di multicanalità disponibile è basato su tecnologia SOAP o REST/JSON.

Nel caso di connettore SOAP il WSDL è scaricabile al seguente indirizzo:

.. note:: http://IP_TVOX/mc/cxf/soap?wsdl

L'endpoint soap che espone il servizio è:

.. note:: http://IP_TVOX/mc/cxf/soap

Nel caso di connettore basato su REST/JSON il WADL che descrive il servizio è scaricabile al seguente indirizzo:

.. note:: http://IP_TVOX/mc/cxf/rest?_wadl

.. important:: IP_TVOX è l'indirizzo IP della piattaforma |tvox| su cui si vuole sviluppare l'integrazione

La struttura dati che viene interessata nel connettore, per entrambe le tecnologie, è la seguente:

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

Per dettagli sull'implementazione consultare la |documentation_link|

.. |documentation_link| raw:: html

    <a href="http://documentation.teleniasoftware.com/multichannel_connector/index.html#introduction"target="_blank"> Documentazione tecnica</a>