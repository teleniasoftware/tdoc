.. _PopupSchedaTicket:

=======================
Pop - up scheda ticket
=======================

All’arrivo di un’interazione apri automaticamente la scheda ticket nel tuo CRM in modo da tracciare tutte le richieste  ottimizzando la produttività del tuo Customer Care. Se l’interazione viene trasferita da un operatore all’altro anche il ticket nel crm viene automaticamente trasferito tra gli agenti di contact center eliminando i tempi di ricerca.

Come visto nelle sezioni precedenti, è possibile creare un IVR che si integra con sistemi esterni come webservice, database o simili attraverso l'implementazione di uno script php.

In questo caso parliamo di un caso d'uso interessante, che consiste non solo nell'interrogare un sistema esterno ma anche nell'interagire direttamente con le sue funzionalità operative.

Nei sistemi CTI complessi, infatti, diventa sempre più frequente l'integrazione tra sistemi che implementano canali di comunicazione diversi quali, ad esempio, canale telefonico e canale ticket: tipicamente, alla ricezione di una chiamata di contact center, si desidera che sul pc dell'operatore che risponde alla chiamata venga aperta, tramite azione di screen popup, anche la pagina relativa al ticket che il CTI ha creato sul sistema di ticketing di terze parti in relazione alla chiamata stessa.

Questo si concretizza, di fatto, nell'implementare uno script php che deve essere caricato su un servizio IVR posizionato a monte dei servizi di
contact center: tale script, prima di inoltrare la chiamata al servizio corretto, ha il compito di inviare al sistema di ticketing esterno una richiesta di creazione ticket sulla base del clid della chiamata, in modo tale che sul sistema di ticketing venga creato un ticket relativo al contatto associato al clid stesso.

A creazione ticket avvenuta, il sistema di ticketing può rispondere a TVox inviando l'id del ticket creato: tale id è salvato da TVox in una variabile per poterlo rendere disponibile, se necessario, in una fase successiva della chiamata.

All'atto dell'apertura, inoltre, se il sistema di ticketing lo prevede, è possibile fare in modo che lo script php gestisca la popolazione sul ticket di campi personalizzati con, ad esempio, informazioni raccolte dall'ivr. Vediamo un caso pratico di esempio:

#. Su CTI arriva una chiamata dal signor Mario Rossi che viene gestita dallo script php tramite IVR opportuno
#. Lo script prevede che Mario Rossi effettui delle scelte all'interno di un percorso predefinito, scelte ad esempio atte ad identificare il servizio di contact center adatto a gestire la richiesta del customer (assistenza, informazioni commerciali, amministrazione..)
#. A seconda della scelta operata da customer (ad esempio Assistenza), lo script salva "Assistenza" all'interno di una variabile
#. Lo script triggera al sistema di ticketing la richiesta per la creazione del ticket, passando come parametri il clid (numero dal quale il customer sta chiamando) e "assistenza" come identificativo della tipologia del ticket da creare (nell'ipotesi che sul sistema di ticketing esista un campo che caratterizzi la tipologia del ticket)
#. Sul sistema di ticketing viene creato il ticket con id = 1025874 relativo alla chiamata in corso, associato al customer "Mario Rossi", identificato dal sistema di ticketing tramite numero di telefono, e con campo "Tipo Ticket" = "Assistenza"
#. Il sistema di ticketing risponde a TVox comunicando l'id del ticket associato alla chiamata, TVox salva tale id in una variabile denominata **CALLDATA**
#. Lo script inoltra la chiamata al servizio di Contact Center "Assistenza", e questa viene consegnata all'agente Luca Verdi.
#. Appena Luca Verdi risponde, sul suo pc viene aperta in screen popup la pagina web del sistema di ticketing relativa al ticket con id = 1025874, Luca Verdi può quindi parlare con Mario Rossi e al contempo lavorare il ticket

Questo tipo di integrazione, oltre a quanto descritto, può prevedere un'ulteriore casistica: il trasferimento della chiamata ad altra coda, cui risponde un altro agente, con conseguente trasferimento del ticket.

Questo è possibile perchè TVox lega l'id univoco della chiamata all'id del ticket che è stato generato in relazione ad essa.


