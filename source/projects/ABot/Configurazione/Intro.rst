.. _WaveNet: https://cloud.google.com/text-to-speech/docs/wavenet
.. _Google cloud tts: https://cloud.google.com/text-to-speech/pricing
.. _Google cloud stt: https://cloud.google.com/speech-to-text/pricing

=====================
Configurazione TVox Attendant Bot
=====================

| Il TVox Attendant Bot è un **posto operatore** automatico che consente all'interlocutore di selezionare vocalmente con chi mettersi in contatto.
| Al chiamante verrà chiesto di pronunciare il nome dell'agente o del servizio che vuole chiamare, e nel caso quest'ultimo non sia disponibile o non si disturbabile, consente la dettatura di un messaggio che verrà trascritto e inviato via chat all'agente richiesto.

| L'utilizzo del TVox Attendant Bot richiede la configurazione di un account Google abilitato ai servizi di
| riconoscimento vocale presenti su **Google Cloud Service** ( Google speech service ) la configurazione di un servizio IVR sul TVox.

.. warning:: La configurazione di un IVR con TVox Attendant Bot **RICHIEDE** la presenza di un servizio google abilitato al Text-to-Speech e Speech-to-Text

| Il **Google Speech Service** si divide in due servizi di riconoscimento e sintetizzazione vocale, ed entrambi richiedono diversi piani di fatturazione:

**TTS** ( Text-To-Speech ):

+------------------------------+--------------------------------+-----------------------------------------------+
|          Funzionalità        |         Gratuità mensile       |  Prezzo dopo aver raggiunto la quota gratuita |
+------------------------------+--------------------------------+-----------------------------------------------+
|  Voci standard (Non WaveNet) |  Da 0 a 4 milioni di caratteri |  $ 4,00 per milione di caratteri              |
+------------------------------+--------------------------------+-----------------------------------------------+
|  Voci WaveNet                |  Da 0 a 1 milione di caratteri |  $ 16,00 per milione di caratteri             |
+------------------------------+--------------------------------+-----------------------------------------------+

**STT** ( Speech-To-Text ):

+------------------------------------+----------------------------------------------------------+----------------------------------------------------------+
|                   Funzionalità     |                       Modelli standard                   |                       Modelli avanzati                   |
+------------------------------------+---------------+------------------------------------------+---------------+------------------------------------------+
|                                    |  0-60 minuti  |  Oltre 60 minuti fino ad 1 mln di minuti |  0-60 minuti  |  Oltre 60 minuti fino ad 1 mln di minuti |
+------------------------------------+---------------+------------------------------------------+---------------+------------------------------------------+
|  Riconoscimento senza log dei dati |  Nessun costo |  $ 0,006 ogni 15 secondi                 |  Nessun costo |  $ 0,009 ogni 15 secondi                 |
+------------------------------------+---------------+------------------------------------------+---------------+------------------------------------------+
|  Riconoscimento con log dei dati   |  Nessun costo |  $ 0,004 ogni 15 secondi                 |  Nessun costo |  $ 0,006 ogni 15 secondi                 |
+------------------------------------+---------------+------------------------------------------+---------------+------------------------------------------+

Risorse: `Google cloud tts`_ e `Google cloud stt`_

 .. toctree::
    :maxdepth: 1

    ConfigurazioneGoogle
    ConfigurazioneTVox