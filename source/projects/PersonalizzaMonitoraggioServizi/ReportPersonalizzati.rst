==============================
Realizza report personalizzati
==============================

Quando il monitoraggio attraverso una rappresentazione grafica non è sufficiente, ma si ha la necessità di generare un report analitico che descriva nel dettaglio i dati raccolti, esistono diversi strumenti che possono integrarsi con le API di |dm|.


.. figure:: /images/datamodel/MicrosoftExcel.jpg
    :align: left
    :figwidth: 120px


**Microsoft Excel**, sia nella sua versione desktop che cloud (Microsoft Office 365), è uno degli standard del settore per l'analisi e il reporting dei dati attraverso la creazione di fogli di calcolo. |br|
Sfruttando la funzionalità *Power Query* (disponibile nella versione desktop a partire da Microsoft Excel 2016) è possibile integrare sorgenti dati Web, come nel caso dell'API TVox Data Model. |br|
Maggiori dettagli sulle modalità d'integrazione con gli strumenti di reportistica Microsoft potete trovarli nella |documentation_integration_microsoft_link|.

--------------------------

.. figure:: /images/datamodel/GoogleSheets.png
    :align: left
    :figwidth: 120px

**Google Sheets** è un software cloud in cui è possibile creare e modificare fogli di calcolo direttamente nel browser Web. Più persone possono lavorare contemporaneamente, visualizzare le modifiche mentre vengono apportate ed ogni modifica viene salvata automaticamente. |br|
Google Sheets non consente nativamente di elaborare dati in formato JSON recuperati da una fonte Web (come nel caso dell'API |dm|), ma è possibile integrare funzioni personalizzate (attraverso codice Javascript) in grado di farlo. |br|
È disponibile una gruida relativa alla configurazione di un report con Google Sheets alla seguente pagina: `Configurazione Google Sheets <ConfigurazioneGoogleSheets.html>`__. |br|
Maggiori dettagli sulle modalità d'integrazione potete trovarli nella |documentation_integration_google_link|.




.. |documentation_integration_microsoft_link| raw:: html

    <a href="http://documentation.teleniasoftware.com/datamodel/index.html#microsoft-excel-amp-power-bi" target="_blank"> documentazione tecnica</a>


.. |documentation_integration_google_link| raw:: html

    <a href="http://documentation.teleniasoftware.com/datamodel/index.html#google-sheets" target="_blank"> documentazione tecnica</a>


.. |br| raw:: html

   <br />