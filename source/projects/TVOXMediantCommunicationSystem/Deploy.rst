======
Deploy
======

Il sistema MCS è distribuita attraverso un appliance in formato ISO che può essere utilizzato per l'installazione su tradizionali hypervisor on premise (VmWare ESXI , Microsoft Hyper-V, Citrix XenServer).

La ISO current release è scaribile dal seguente link:
http://www.teleniasoftware.it/download/tvox/iso.php

.. note::
  Su richiesta è disponibile l'immagine in formato compatibile con le seguenti infrastrutture cloud:

  - Amazon Web Servicse (AWS)
  - Google Cloud Platform (GCP)
  - Microsoft Azure

Il sistema operativo dell'appliance ha già subito un processo di hardening (es. disabilitazione di servizi non necessari, disabilitazione degli algoritmi HTTPS meno sicuri, ecc.).

Si consiglia di cambiare la password di admin immediatamente dopo l'installazione.

.. note::
  La configurazione MCS è delegata ad una apposita utenza che ai fini di sicurezza potrà accedere solo alla sezione MCS e non accedere alla configurazione del sistema.


.. note::
  IPS, IDS e Application control non sono prestazioni erogate dell'appliance MCS

.. note::
  Il servizio HTTPS accetta sono i protocolli TLSv1.0 e superiori.
