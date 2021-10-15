==========================
Autenticazione TVox WebAPI
==========================

L'autenticazione verso le TVox WebAPI è necessaria al fine di utilizzare 
i vari metodi che si andranno ad integrare.

Il login viene effettuato mediante la sequenza dei metodi **getVersion** e **login**, 
chiamati tramite jsonrpc verso l'indirizzo **https://<tvox_url>/tvox/webapi** 
( dove <tvox_url> corrisponde al dominio o all'indirizzo IP in cui risiede il TVox )

----

getVersion
##########
Il metodo getVersion è necessario al fine di ottenere la versione del server TVox
in cui si effettuerà l'accesso.
Il metodo non richiede parametri. 

Il risultato conterrà la versione del server TVox in uso e la versione delle WebAPI. |br|
Il valore da utilizzare è il secondo, ovvero la versione delle WebAPI (nell'esempio sottostante "10.26.0).

Richiesta di esempio
--------------------

.. code-block:: JSON

    {
        "id": 0,
        "jsonrpc": "2.0", 
        "method": "getVersion", 
        "params": []
    }

Risposta di esempio
--------------------

.. code-block:: JSON

    {
        "id": 1,
        "jsonrpc": "2.0",
        "result": [ "10.26.32", "10.26.0" ]
    }

----

login
######

Il metodo login va utilizzato per autenticarsi sulle TVox WebAPI ed avere l'accesso a tutti i metodi che richiedono autenticazione.

.. note:: È necessario che l'utente con il quale si va ad accedere disponga dei permessi di Superuser o Supervisor

Le successive richieste alle TVox WebAPI che richiedono autenticazione dovranno avere un cookie contenente il `sessionId` generato dalla richiesta di login. |br|
Il cookie dovrà avere questa forma:

.. code-block:: console

    Set-Cookie: JSESSIONID=lmjfmm378du718big0jwv4bjg; path=/tvox;

ovvero chiave `JSESSIONID`, valore `sessionId` (ottenuto dalla risposta della login) e path `/tvox`.

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
        "id": 2
        "jsonrpc": "2.0", 
        "method": "login", 
        "params": [
            "10.26.0",
            "admin", 
            "admin"
        ]
    }

Risposta di esempio
--------------------

.. code-block:: JSON

    {
        "jsonrpc": "2.0",
        "id": 2,
        "result": {
            "username": "admin",
            "surname": "Admin",
            "name": "",
            "publicUsername": "admin",
            "accessToken": "c53aaeb3734191788f45b413da1ef24",
            "sessionId": "lmjfmm378du718big0jwv4bjg",
            "status": "LOGGED",
            "language": null,
            "anonymous": false,
            "pwdChangeable": false,
            "chatUserId": null,
            "chatAuthToken": null,
            "chatUri": null,
            "profileRoles": [
                "TVOX_SUPERVISOR",
                "TVOX_AGENT",
                "TVOX_USER",
                "SYSTEM_USER"
            ],
            "userPermissions": [
                "IVR",
                "SUPERVISOR"
            ],
            "logged": true
        }
    }