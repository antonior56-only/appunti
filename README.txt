I MIEI APPUNTI - VERSIONE PWA

Contenuto
- index.html: app
- manifest.webmanifest: dati di installazione
- sw.js: accesso offline
- icons/: icone

Per installare, pubblica l'intera cartella su un sito HTTPS e apri index.html,
oppure avviala in locale con un server su localhost. Aprire index.html con
doppio clic (indirizzo file://) non abilita l'installazione PWA.

Per aggiornare una PWA gia' installata, sostituisci tutti i file della cartella
sullo stesso indirizzo HTTPS usato per l'installazione. Apri l'app con una
connessione, ricarica e riavviala. In Impostazioni verifica che compaia
"Versione PWA 2026-09-26.4".

Esempio con Python, eseguito dentro questa cartella:
    python -m http.server 8000
Poi apri http://localhost:8000/ nel browser.

Il pulsante "Installa" appare nella versione web quando l'app non gira gia'
come app installata. Dove il browser non offre una finestra di installazione,
il pulsante mostra le istruzioni disponibili.

I dati sono salvati nel browser per ogni origine. Se passi da un file locale
o da un altro sito alla PWA, esporta prima il backup JSON dalla vecchia app
e importalo nella nuova. Il backup JSONBin puo' essere collegato nelle
Impostazioni usando la tua chiave e il Bin ID.

L'app funziona offline dopo la prima visita completata; funzioni Gemini,
JSONBin e Google Calendar richiedono invece una connessione.

La dettatura usa il riconoscimento vocale del browser. Se il browser non lo
supporta, il campo di testo resta utilizzabile normalmente. In alcuni browser
il riconoscimento invia l'audio a un servizio online e richiede la connessione.
