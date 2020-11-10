===============================================
Esempio: Popola il Customer Journey del tuo CRM
===============================================

.. note:: In questa sezione utilizzeremo un esempio pratico di integrazione tra il CRM e il TVox per capirne meglio le opportunità e le modalità.

Ipotizziamo di avere un CRM per la gestione del Customer Care di un e-commerce in cui ogni scheda contatto, oltre la sua anagrafica, mostra all'operatore un *Customer Journey*.

Questo riporta già le diverse interazioni che il contatto ha avuto con la vostra azienda in termini di ordini e resi, mancano le interazioni telefoniche.

Nelle prossime sezioni vedremo come configurare i servizi di notifica del TVox per fare in modo che il nostro Web Service aggiunga al Customer Journey del CRM le seguenti informazioni:

- Chiamata di servizio inbound
    - Data e ora in cui la chiamata è stata consegnata all'operatore
    - Operatore a cui è stata consegnata la chiamata
    - Servizio su cui è stata ricevuta la chiamata
    - Data e ora in cui l'operatore ha risposto alla chiamata ricevuta
    - Data e ora in cui la chiamata ricevuta e risposta è terminata
- Chiamata outbound
    - Data e ora in cui è stata effettuata la chiamata
    - Operatore che ha effettuato la chiamata
    - Data e ora in cui la chiamata è stata risposta
    - Data e ora in cui la chiamata è terminata

Tratteremo poi un caso particolare delle chiamate di servizio inbound, ovvero la trasferta ad altro operatore, aggiungendo al Customer Journey le seguenti informazioni:

- Chiamata trasferita ad altro operatore
    - Data e ora in cui la chiamata è stata trasferita
    - Operatore a cui è stata trasferita la chiamata

.. toctree::
   :maxdepth: 2

   Prerequisiti 
   ChiamataServizioInbound
   ChiamataOutbound
   ChiamataTrasferita