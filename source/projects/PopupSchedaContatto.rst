.. _PopupSchedaContatto:

=========================
Pop - up scheda contatto
=========================

All’arrivo di un’interazione apri automaticamente la scheda contatto del tuo crm in modo da fornire all’operatore di contact center tutte le informazioni utili alla gestione della richiesta, ottimizzando la produttività del Customer Care.

---------

La sezione popup manager serve per configurare la funzione di screen popup invocata a fronte di chiamate di servizio.

La funzionalità di screen popup per gli agenti di Contact Center può essere invocata:

- in fase di ring
- alla risposta
- alla chiusura della chiamata 
- on demand

Mentre per gli utenti di risposta può essere invocata solo on demand.

----------

E' possibile avere due tipi di generazione url:

- Generazione URL su server
- Legacy (Windows BAT)

La generazione di URL lato server consente di implemetare screen popup al client WEB:

- il popup su TVox Client può essere configurato per eseguire URL sia su Browser sia su WebView singola o multitab;
- il popup su WebClient può anch'esso essere eseguito all'interno della sua pagina principale (IFRAME) oppure su una tab aggiuntiva a seconda delle esigenze implementative che l'integrazione richiede;
 

L'invocazione del popup può avvenire per tutti i canali per i quali si è abilitati:
 
 - *canale telefonico*
 - *canale video*
 - *Web Chat*
 - *Whatsapp*
 - *Canai custom*

Nel tag "servizi associati" è possibile andare ad abilitare o meno l'invocazione del  popup per i vari servizi e canali

-------

Per poter utilizzare lo screen popup su client è necessario scrivere una funzione, utilizzando il linguaggio Javascript, che ritorni un oggetto JSON di questo tipo:

 {
    **onRing**: *null*,

    **onAnswer**: *null*,

    **onHangup**: *null*,

    **onDemand**: *null*,

    **webClientOpenNewTab**: *false*,

    **webClientTabName**: *null*
 }

**onRing**

 *type*: string 
 *default*: null

Se diverso da null verrà aperto questo link al ring.

**onAnswer**

 *type*: string 
 *default*: null

Se diverso da null verrà aperto questo link alla risposta.

**onHangup**

 *type*: string
 *default*: null

Se diverso da null verrà aperto questo link al alla chiusura.

**onDemand**

 *type*: string
 *default*: null

Se diverso da null verrà aperto questo link su richiesta dell'agente.

**webClientOpenNewTab**

 *type*: boolean
 *default*: null

Se valorizzato a true il link verrà aperto in un una nuova tab, altrimenti in iframe.

**webClientTabName**

 *type*: string
 *default*: null

Se valorizzato verrà utilizzata sempre la stessa tab, altrimenti verrà aperta una nuova tab ogni volta.

Attenzione che:

- una nuova tab prende sempre il focus
- il riciclo di una tab esistente viene sempre caricata in background

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

**Variabili di agente, modalità d'utilizzo: {$NOME_VARIABILE}**

- USERNAME: Username dell'utente che sta ricevendo la chiamata
- SYSTEM_USERNAME: Username del sistema opertivo in utilizzo
- USER_PASSWORD: Password dell'utente
- ACCESS_TOKEN: Access token della sessione utente autenticata sul TVOX

-----------------------------------------------------------------------------------------------------------------------

Nel tag Legacy (Windows BAT) si è mantenuta la possibilità di configurare il winpopup come si configurarava nelle versioni più vecchie. 

Le linee guida da seguire per configurare l'invocazione dello screen popup tramite file batch si trovano nella Guida TVox al paragrafo 5.5
