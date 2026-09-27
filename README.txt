I MIEI APPUNTI - VERSIONE PWA

Contenuto
- index.html: app
- manifest.webmanifest: dati di installazione
- sw.js: accesso offline
- icons/: icone

Per installare, pubblica l'intera cartella su un sito HTTPS e apri index.html,
oppure avviala in locale con un server su localhost. Aprire index.html con
doppio clic (indirizzo file://) non abilita l'installazione PWA.

Per aggiornare una PWA gia' installata, sostituisci i file della cartella
sullo stesso indirizzo HTTPS usato per l'installazione. Apri l'app con una
connessione: apparira' "Aggiorna ora" quando il nuovo service worker e' pronto.
In Impostazioni verifica che compaia "Versione PWA 2026-09-27.7".

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
Puoi scegliere la lingua e annullare l'ultima frase dopo aver fermato la dettatura.
Nei browser compatibili puoi attivare il riconoscimento sul dispositivo;
potrebbe essere necessario scaricare la lingua dal browser.

Le bozze si salvano automaticamente su questo dispositivo. Gli appunti eliminati
vanno nel cestino e sono ripristinabili per 30 giorni. Alla successiva apertura
dopo i 30 giorni, il contenuto viene cancellato; rimane un segnaposto tecnico
per evitare che un altro dispositivo lo reintroduca durante la sincronizzazione.

JSONBin ora confronta gli appunti per ID prima di scrivere. Se due dispositivi
modificano lo stesso appunto, viene creata una copia del conflitto. JSONBin
mantiene un unico bin: la sincronizzazione non sostituisce un vero database
con transazioni atomiche. Esegui anche backup JSON periodici.

Puoi creare appunti di tipo "Lista da spuntare" e segnare le voci completate
direttamente nell'elenco. Le liste esportate da Google Keep diventano liste
spuntabili. Gli eventuali modelli personali salvati in versioni precedenti
restano nei backup e nella sincronizzazione, ma non compaiono nell'interfaccia.
Quando scegli una lista, il campo del titolo diventa compatto e resta
ridimensionabile; le caselle delle voci hanno spazio adeguato per scrivere.

La ricerca trova anche parole scritte con o senza accenti e attende un istante
dopo la digitazione prima di aggiornare l'elenco. Se il salvataggio locale
fallisce, l'app avvisa e lascia il testo nel modulo; esporta un backup prima di
chiudere la pagina.

Importazione Samsung Notes: esporta le singole note da Samsung Notes come
"File di testo" (.txt), poi scegli insieme i file nelle Impostazioni della
PWA. Il nome del file viene usato come titolo; righe con caselle riconoscibili
diventano liste da spuntare. L'importazione non legge .sdocx, PDF o Word e il
formato testo non include immagini, disegni, audio o formattazione.
