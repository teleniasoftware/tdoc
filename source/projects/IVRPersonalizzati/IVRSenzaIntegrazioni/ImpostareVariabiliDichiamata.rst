================================
Impostare variabili di chiamata
================================

Con questa azione è possibile definire una variabile per le chiamate che vengono processate dal nodo, ed utilizzarla per memorizzare dei valori:

.. image:: /images/IVR_imposta_variabile1.png

Oltre ad impostare il nome, è possibile impostare il valore da assegnare alla variabile e decidere se renderla disponibile nei report tramite un apposito flag:

.. image:: /images/IVR_imposta_variabile2.png

La variabile viene memorizzata su database nelle tabelle storiche ast_calls_yyyymm in corrispondenza del campo *popupinfo* ed il formato con cui viene riportato il valore è *TIVR_[nome variabile]=[valore]*.