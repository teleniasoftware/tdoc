============================================
Generare allarmi e analizzare i log generati
============================================

Quando ci integriamo a sistemi esterni come Database, Webservices etc... è consigliabile generare degli allarmi per dare l'informazione
che qualcosa è andato male. Nell'ambito della generazione degli allarmi, normalmente, è possibile anche configurare l'invio di email al team che gestisce |tvox|.

Oltre alla generazione degli allarmi, è importante scrivere bene i log in modo che l'analisi sia facile, consentendo in breve tempo di correggere eventali
errori commessi nello sviluppo.

Il log si divide in vari livelli:

- **INFO:** Livello base di log, serve per scrivere sul logfile le cose importanti che vogliamo sempre siano riportate
    + Scrivere del log per l'inzio e la fine dello script
    + Scrivere del log ogni volta che abbiamo valorizzato una variabile ed abbiamo bisogno di fare il check del contenuto
    + Scrivere del log per marcare dei passaggi importanti tra una funzione e l'altra, ad esempio se dato un risultato di un webservice vado su un menu piuttosto che un altro.
 
- **DEBUG:** Livello di log utilizzato normalmente per scrivere su logfile informazioni aggiuntive rispetto a quelle di info che ci permettono di analizzare meglio eventuali segnalazioni
    + Risultato di un webservice o query Database
    + Nome della funzione sulla quale stiamo passando
    + Variabili di chiamata impostate
    + Digit degli utenti per navigare il menu

- **TRACE:** Livello di log utilizzato per scrivere informazioni molto dettagliate. Normalmnete i livelli INFO e DEBUG sono adeguati; se però necessitate di un dettaglio ulteriore, questo livello di log vi può aiutare.
    + Oggetti complessi, strutture e variabili settate all'interno dello script

.. raw:: html

    <iframe width="560" height="315" src="https://www.youtube.com/embed/1_8o4bpERDA" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

|
