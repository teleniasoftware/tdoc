=========================
Generazione URL su Server
=========================

La generazione dell'URL avviene tramite la definizione di una funzione javascript che restituisca un oggetto JSON di questo tipo:

.. code-block:: javascript

 {
    **onRing**: *null*,
    **onAnswer**: *null*,
    **onHangup**: *null*,
    **onDemand**: *null*,
    **webClientOpenNewTab**: *false*,
    **webClientTabName**: *null*
 }


**onRing**

*type*: string |br|
*default*: null

Se diverso da null verrà aperto questo link in fase di ring.

**onAnswer**

 *type*: string |br|
 *default*: null

Se diverso da null verrà aperto questo link alla risposta da parte dell'operatore.

**onHangup**

 *type*: string |br|
 *default*: null

Se diverso da null verrà aperto questo link alla chiusura della chiamata (chat, whatsapp, video call...).

**onDemand**

 *type*: string |br|
 *default*: null

Se diverso da null verrà aperto questo link su richiesta dell'operatore tramite la pressione su un apposito pulsante presente tra i pulsanti di gestione dell'interazione.

**webClientOpenNewTab**

 *type*: boolean |br|
 *default*: null

Se valorizzato a true il link verrà aperto in un una nuova tab, altrimenti in iframe.

**webClientTabName**

 *type*: string |br|
 *default*: null

Se valorizzato verrà utilizzata sempre la stessa tab, altrimenti verrà aperta una nuova tab ogni volta.


In generale va prestata attenzione ai seguenti aspetti:

- una nuova tab prende sempre il focus
- se viene ricaricata una tab esistente, questa non prende il focus

Di seguito l'elenco delle variabili legate alla chiamata che possono essere utilizzate dalla funzione:

**Variabili di chiamata, modalità d'utilizzo: NOME_VARIABILE**

- CALL_SERVIZIO: Codice del servizio dove applicare la logica di popup
- CALL_CLI: Numero del chiamante
- CALL_DNIS: Numero del chiamato
- CALL_POPUPINFO[]: Informazioni opzionali da aggiungere al popup
- CALL_SKILLSET: Skillset associato al servizio
- CALL_TIPOCHIAMATA: Tipo di chiamata: inbound, outbound, etc...
- CALL_IDLASTCALL: Id dell'ultima chiamata ricvuta
- CALL_SITOORIGINE: Identificativo del sito TVOX dove la chiamata è stata ricevuta (sito remoto)
- CALL_SITODISTRIBUZIONE: Identificativo del sito TVOX dove la chiamata è distribuita agli agenti (sito locale)
- CALL_CHANNELID: Identificativo del canale su cui si riceve la chiamata
- CALL_CHANNELSESSIONID: Id della sessione della chiamata nel canale
- CALL_CHANNELDATA: Informazioni aggiuntive che vogliamo presentare nella chiamata del canale
- CALL_CHANNELDESCRIPTION: Descrizione del canale che si vuole presentare

Di seguito l'elenco delle variabili legate all'agente che possono essere utilizzate dalla funzione:

**Variabili di agente, modalità d'utilizzo: {$NOME_VARIABILE}**

- USERNAME: Username dell'utente che sta ricevendo la chiamata
- SYSTEM_USERNAME: Username del sistema opertivo in utilizzo
- USER_PASSWORD: Password dell'utente
- ACCESS_TOKEN: Access token della sessione utente autenticata sul TVOX

