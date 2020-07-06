============================================
Generare allarmi e analizzare i log generati
============================================

Quando ci integriamo a sistemi esterni come Database, Webservices etc... è consigliabile generare degli allarmi per dare l'informazione
che qualcosa è andato male. La generazione degli allarmi, normalmente invia anche email al team di gestione del TVox.

Oltre alla generazione degli allarmi, è importante scrivere bene i log in modo che l'analisi sia facile e quindi in breve tempo possiamo correggere eventali
errori commessi nello sviluppo.

Il log si divide in vari livelli:

- **INFO:** Livello base di log, serve per scrivere sul file di log le cose importanti che vogliamo sempre trovare all'interno del logfile
    + Scrivere del log per l'inzio e la fine dello script
    + Scrivere del log ogni volta che abbiamo valorizzato una variabile ed abbiamo bisogno di fare il check del contenuto
    + Scrivere del log per marcare dei passaggi importanti tra una funzione e l'altra, ad esempio se dato un risultato di un webservice vado su un menu piuttosto che un altro.
 
- **DEBUG:** Livello di log utilizzato normalmente per scrivere su file di log informazioni aggiuntive rispetto a quelle di info che ci permettono di analizzare meglio il log
    + Risultato di un webservice o query Database
    + Nome della funzione sulla quale stiamo passando
    + Variabili di chiamata impostate
    + Digit degli utenti per navigare il menu

- **TRACE:** Livello di log utilizzato per scrivere informazioni molto dettagliate, normalmnete per gli IVR bastano INFO e DEBUG, ma se necessitate di un dettaglio ulteriore, questo livello di log vi può aiutare.
    + Oggetti complessi, strutture e variabili settate all'interno dello script

.. raw:: html

    <iframe width="560" height="315" src="https://www.youtube.com/embed/1_8o4bpERDA" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
|
