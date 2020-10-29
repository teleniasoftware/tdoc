==========================
Autenticazione TVox WebAPI
==========================

L'autenticazione verso le TVox WebAPI è necessaria al fine di utilizzare 
i vari metodi che si andranno ad integrare.

Il login viene effettuato mediante la sequenza dei metodi **getVersion** e **login**, 
chiamati tramite jsonrpc verso l'indirizzo **http://<tvox_url>/tvox/webapi** 
( dove <tvox_url> corrisponde al dominio o all'indirizzo IP in cui risiede il TVox )

----

getVersion
##########
Il metodo getVersion è necessario al fine di ottenere la versione del server TVox
in cui si effettuerà l'accesso.
Il metodo non richiede parametri. 

Richiesta di esempio
--------------------

.. code-block:: JSON

    {
    "jsonrpc": "2.0", 
    "method": "getVersion", 
    "params": [], 
    "id": 0
    }

Il risultato conterrà la versione del server TVox in uso.

----

login
######

Il metodo login va utilizzato per autenticarsi sulle TVox WebAPI ed avere l'accesso a tutti i metodi che richiedono autenticazione.

.. note:: È necessario che l'utente con il quale si va ad accedere disponga dei permessi di Superuser o Supervisor

Parametri richiesti
-------------------

version
*******
*String*    Versione del server TVox ottenuta tramite il metodo getVersion **Campo obbligatorio**

username
***********
*String*    Nome utente **Campo obbligatorio**

password
***********
*String*    Password **Campo obbligatorio**


Richiesta di esempio
--------------------

.. code-block:: JSON

    {
    "jsonrpc": "2.0", 
    "method": "login", 
    "params": [
        "10.26.24",
        "admin", 
        "admin"
    ], 
    "id": 1
    }