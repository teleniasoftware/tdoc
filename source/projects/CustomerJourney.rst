.. |customer_journey_header| image:: ../images/customerJourney/customer_journey_header.png
    :scale: 100%

.. |customer_journey_body_1| image:: ../images/customerJourney/customer_journey_body_1.png

.. |customer_journey_body_2| image:: ../images/customerJourney/customer_journey_body_2.png

=================
Customer Journey
=================

| Il customer journey fornisce una panoramica delle interazioni che un cliente ha avuto con il contact center, migliorando la customer experience e la produttività degli agenti.

---------

La prestazione è legata ai moduli di licenza abilitati su |tvox|.
Il modulo principale è **Customer Journey**, che abilita la cronologia di interazioni multichannel, riportando di base soltanto le chiamate telefoniche.
Per abilitare la visualizzazione di altri tipi di interazione sono necessari i seguenti moduli:

- **Support** ( Per le interazioni di tipo Ticket )
- **Sondaggi** ( Per abilitare l\'NPS )
- **Web Widget** ( Per le interazioni di tipo Chat )
- **Whatsapp** ( Per le interazioni dal canale whatsapp )

| Il modulo **Customer Journey** abilita i processi lato server a collezionanare le informazioni relative ai diversi tipi di interazione e abilita il TVox web client alla visualizzazione del customer journey.
| **Il customer journey necessita la presenza di un server dedicato ( Fisico o Virtuale )**

---------

| Il Customer Journey mette a disposizione due informazioni principali riguardanti il cliente:

- NPS (Net promoter score)
- Storico di **tutte** le interazioni che il cliente ha avuto con il contact center

| L'NPS è una valutazione che fornisce il cliente attraverso un servizio IVR, e rappresenta il grado di soddisfazione che esso ha raggiunto nell'ultima interazione che ha avuto con il servizio. Questa valutazione aiuta gli agenti a prepararsi in maniera adeguata quando il cliente ingaggia nuovamente il sistema.
| L'NPS è riportato in alto a sinistra nella vista del customer journey, e insieme ad esso, è possibile capire quante interazioni sono state generate da questo cliente nell'arco temporale di 30 giorni. É anche riportato il numero totale di ticket che sono attualmente attivi sul customer visualizzato.


.. raw:: html

    <div style="display: flex; align-items: center; justify-content: center">

|customer_journey_header|


.. raw:: html

    </div>

| Lo storico invece, consiste in una linea temporale che riporta, insieme ad alcuni dettagli, tutte le interazioni che il cliente ha avuto con il contact center, su qualsiasi canale a cui il sistema è abilitato.
| Ogni interazione è rappresentata dalla propria icona e le informazioni riportate nei suoi dettagli variano in base al tipo di interazinone. Ad esempio una chiamata riporterà informazioni relativamente diverse rispetto ad un ticket, dal momento che il sistema di ingaggio dei due servizi è molto diverso.


.. raw:: html

    <div style="display: flex; align-items: center; justify-content: center; flex-direction: row">

|customer_journey_body_1|

|customer_journey_body_2|


.. raw:: html

    </div>

| Le interazioni all'interno del customer journey dipendono anche dalle competenze dell'agente: tutti gli agenti possono visualizzare il customer journey di un certo customer, ma le interazioni visualizzate in esso dipendono dai servizi di cui l'agente fa parte.

| Sono disponibili nel seguente elenco dei video-corso che illustrano e spiegano il funzionamento del Customer Journey

 .. toctree::
   :maxdepth: 1

   CustomerJourneyVideoCorso/Intro
   CustomerJourneyVideoCorso/WebClient
   CustomerJourneyVideoCorso/NPS
   CustomerJourneyVideoCorso/Cronologia
   CustomerJourneyVideoCorso/Demo
   CustomerJourneyVideoCorso/Requisiti