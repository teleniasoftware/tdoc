========================
Estensione Click to Call
========================

È disponibile un'estensione per il browser Google Chrome che sfrutta le api di click to dial.
Questa estensione permette di effettuare chiamate dal TVox web client semplicemente cliccando su un numero di telefono di una qualsiasi pagina web visitata.

.. warning:: Per il corretto funzionamento dell'estensione TVox Click to Call è necessario disporre di un TVox con versione 10.24.0 o successiva

----

Installazione 
=============

L'estensione può essere installata dal `Chrome Web Store <https://chrome.google.com/webstore/detail/tvox-click-to-call/lcpoakjecdidnegmabgpkjhmbgbakfpd>`_

.. image:: /images/crmGestioneTelefonica/estensioneClickToCall/1.png

----

Configurazione 
==============

Dopo è necessario accedere ad un TVox client. L'estensione utilizzerà automaticamente il dominio dell'ultimo TVox visitato per effettuare le telefonate. Se è già presente una tab del TVox web client sarà necessario ricaricarne la pagina per applicare le impostazioni.

Opzioni estensione
###################

Le opzioni dell'estensione sono raggiungibili dalla lista delle estensioni installate:

.. image:: /images/crmGestioneTelefonica/estensioneClickToCall/2.png
.. image:: /images/crmGestioneTelefonica/estensioneClickToCall/3.png

La pagina delle opzioni proporrà le seguenti configurazioni:

.. image:: /images/crmGestioneTelefonica/estensioneClickToCall/4.png

Impostazioni generali
*********************

    **Indirizzo server TVox**
        Indirizzo del server TVox configurato automaticamente all'apertura di un client

    **Usa sempre l'URL dell'ultimo TVox Client visitato**
        Se disabilitato l'indirizzo del server TVox non verrà sostituito con l'url dell'ultimo client visitato

Cifre numeri di telefono
************************

Configurazione dei numeri di telefono analizzati nelle varie pagine web.

Lista di siti
*************

Da questa sezione è possibile configurare una lista di siti per i quali l'estensione non sarà attiva.

    **Escludi selezionati**
        Se questa opzione è attiva, in tutti i siti web aggiunti l'estensione non sarà attiva

    **Consenti solo selezionati**
        Se questa opzione è attiva, l'estensione sarà attiva solamente nei siti web aggiunti

----

Utilizzo dell'estensione
========================

Navigando su un sito web ( non presente nella lista delle esclusioni ) verranno automaticamente sottolineati e resi cliccabili i numeri di telefono che rispettano le condizioni configurate nelle impostazioni dell'estensione.
Cliccando su uno di questi numeri verrà effettuata una telefonata tramite il TVox Web Client.

È anche possibile selezionare un numero di telefono manualmente ( se questo non viene riconosciuto automaticamente dall'estensione ) e chiamarlo dalla voce proposta dal menu contestuale, raggiungibile con un click sul tasto destro del mouse.

.. image:: /images/crmGestioneTelefonica/estensioneClickToCall/5.png
.. image:: /images/crmGestioneTelefonica/estensioneClickToCall/6.png