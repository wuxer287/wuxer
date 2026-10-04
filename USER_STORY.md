# WUXER - User story

TITOLO: Registrazione/login

USER STORY:
Come Visitatore,
Voglio registrarmi e accedere con credenziali o con OAuth,
In modo da poter usare wuxer con il mio account.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Registrazione riuscita
  - DATO che l'utente non ha un account e ha almeno 13 anni
  - QUANDO l'utente compila il modulo con email, nome utente univoco e password valida
  - ALLORA il sistema crea l'account, salva la password con hash e permette l'accesso

- Scenario 2: Registrazione non consentita
  - DATO che l'utente ha meno di 13 anni oppure il nome utente o l'email sono già in uso
  - QUANDO l'utente invia il modulo di registrazione
  - ALLORA il sistema rifiuta la registrazione e mostra il motivo

- Scenario 3: Login con credenziali errate
  - DATO che esiste un account registrato
  - QUANDO l'utente inserisce una password errata
  - ALLORA il sistema nega l'accesso con un messaggio generico e, dopo ripetuti tentativi falliti, limita temporaneamente l'accesso

- Scenario 4: Accesso con OAuth
  - DATO che l'utente ha un account presso un provider supportato
  - QUANDO l'utente sceglie di accedere con OAuth
  - ALLORA il sistema autentica l'utente e apre il suo account

---

TITOLO: Profilo

USER STORY:
Come Utente registrato,
Voglio modificare le informazioni del mio profilo,
In modo da presentarmi agli altri utenti come preferisco.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Modifica riuscita
  - DATO che l'utente ha effettuato l'accesso
  - QUANDO l'utente modifica foto, nome o biografia e salva
  - ALLORA il sistema salva le modifiche e le mostra subito sul profilo

- Scenario 2: Nome utente già in uso
  - DATO che l'utente è nella pagina di modifica del profilo
  - QUANDO l'utente sceglie un nome utente già usato da un altro profilo
  - ALLORA il sistema rifiuta la modifica e chiede un altro nome utente

---

TITOLO: Pubblicazione storie

USER STORY:
Come Utente registrato,
Voglio pubblicare una storia con immagini e testo,
In modo da condividere un momento temporaneo con i miei follower.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Storia pubblicata
  - DATO che l'utente ha effettuato l'accesso
  - QUANDO l'utente carica un'immagine e/o scrive un testo e pubblica
  - ALLORA il sistema pubblica la storia e la rende visibile ai follower

- Scenario 2: Scadenza della storia
  - DATO che una storia è stata pubblicata da 24 ore
  - QUANDO l'utente scorrono le 24 ore
  - ALLORA il sistema il sistema rimuove automaticamente la storia

- Scenario 3: Storia vuota
  - DATO che l'utente è nella schermata di creazione
  - QUANDO l'utente tenta di pubblicare senza immagine né testo
  - ALLORA il sistema impedisce la pubblicazione e mostra un avviso

---

TITOLO: Pubblicazione post

USER STORY:
Come Utente registrato,
Voglio pubblicare un post con immagini e descrizione,
In modo da condividere contenuti duraturi sul mio profilo.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Post pubblicato
  - DATO che l'utente ha effettuato l'accesso
  - QUANDO l'utente carica una o più immagini, scrive la descrizione e pubblica
  - ALLORA il sistema pubblica il post sul profilo e lo rende disponibile nei feed dei follower

- Scenario 2: Immagine non valida
  - DATO che l'utente sta creando un post
  - QUANDO l'utente carica un file in un formato non supportato o troppo grande
  - ALLORA il sistema rifiuta il file e indica i formati e le dimensioni ammessi

---

TITOLO: Follow

USER STORY:
Come Utente registrato,
Voglio seguire e smettere di seguire altri profili,
In modo da vedere i contenuti dei profili che mi interessano.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Seguire un profilo
  - DATO che l'utente visualizza il profilo di un altro utente che non segue
  - QUANDO l'utente preme "Segui"
  - ALLORA il sistema registra il follow e aggiorna subito il conteggio dei follower

- Scenario 2: Smettere di seguire
  - DATO che l'utente segue già un profilo
  - QUANDO l'utente preme "Non seguire più"
  - ALLORA il sistema rimuove il follow e i contenuti di quel profilo non compaiono più nel feed

- Scenario 3: Seguire se stessi
  - DATO che l'utente visualizza il proprio profilo
  - QUANDO l'utente cerca di seguire se stesso
  - ALLORA il sistema non offre l'azione o la rifiuta

---

TITOLO: Interazioni storie

USER STORY:
Come Utente registrato,
Voglio mettere like e commentare le storie,
In modo da interagire con chi le pubblica.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Like e commento
  - DATO che una storia è visibile e non scaduta
  - QUANDO l'utente l'utente mette like e scrive un commento
  - ALLORA il sistema registra il like e il commento e li mostra all'autore

- Scenario 2: Like duplicato
  - DATO che l'utente ha già messo like a una storia
  - QUANDO l'utente preme di nuovo il like
  - ALLORA il sistema rimuove il like senza registrarne uno secondo

- Scenario 3: Storia scaduta
  - DATO che una storia è scaduta
  - QUANDO l'utente l'utente cerca di interagire con essa
  - ALLORA il sistema la storia non è più disponibile e non accetta interazioni

---

TITOLO: Interazioni post

USER STORY:
Come Utente registrato,
Voglio mettere like e commentare i post,
In modo da interagire con gli altri utenti.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Like e commento
  - DATO che un post è visibile
  - QUANDO l'utente l'utente mette like e scrive un commento
  - ALLORA il sistema registra le interazioni e le mostra sotto il post

- Scenario 2: Like duplicato
  - DATO che l'utente ha già messo like a un post
  - QUANDO l'utente preme di nuovo il like
  - ALLORA il sistema rimuove il like senza registrarne uno secondo

- Scenario 3: Commento vuoto
  - DATO che l'utente sta commentando un post
  - QUANDO l'utente invia un commento senza testo
  - ALLORA il sistema non pubblica il commento e mostra un avviso

---

TITOLO: Feed

USER STORY:
Come Utente registrato,
Voglio vedere un feed con i contenuti degli altri profili in base alle mie interazioni,
In modo da scoprire contenuti che mi interessano.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Feed personalizzato
  - DATO che l'utente ha effettuato l'accesso e ha già interagito con alcuni contenuti
  - QUANDO l'utente apre il feed
  - ALLORA il sistema mostra i contenuti ordinati in base alle sue interazioni, caricandoli progressivamente

- Scenario 2: Nessuna interazione precedente
  - DATO che l'utente è nuovo e non ha interazioni
  - QUANDO l'utente apre il feed
  - ALLORA il sistema mostra comunque contenuti di default invece di una pagina vuota

- Scenario 3: Contenuto rimosso
  - DATO che un contenuto è stato rimosso dai moderatori
  - QUANDO l'utente l'utente apre il feed
  - ALLORA il sistema non mostra più quel contenuto

---

TITOLO: Segnalazione dei contenuti

USER STORY:
Come Utente registrato,
Voglio segnalare un contenuto, inclusi i messaggi privati ricevuti, indicando un motivo,
In modo da aiutare a mantenere sicura la community.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Segnalazione riuscita
  - DATO che l'utente sta visualizzando un contenuto inappropriato
  - QUANDO l'utente sceglie "Segnala" e indica un motivo
  - ALLORA il sistema registra la segnalazione e conferma la ricezione all'utente

- Scenario 2: Segnalazione di un messaggio privato
  - DATO che l'utente ha ricevuto un messaggio in una chat privata end-to-end
  - QUANDO l'utente segnala quel messaggio
  - ALLORA il sistema invia ai moderatori solo il messaggio segnalato, senza compromettere il resto della chat

- Scenario 3: Motivo mancante
  - DATO che l'utente sta compilando una segnalazione
  - QUANDO l'utente la invia senza indicare un motivo
  - ALLORA il sistema non la registra e chiede di indicare un motivo

---

TITOLO: Moderazione dei contenuti

USER STORY:
Come Moderatore,
Voglio esaminare le segnalazioni e rimuovere i contenuti,
In modo da garantire il rispetto delle regole della community.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Rimozione di un contenuto
  - DATO che esiste una segnalazione in attesa
  - QUANDO l'utente il moderatore la esamina e decide di rimuovere il contenuto
  - ALLORA il sistema rimuove il contenuto e segna la segnalazione come gestita

- Scenario 2: Segnalazione infondata
  - DATO che esiste una segnalazione in attesa
  - QUANDO l'utente il moderatore decide che il contenuto è conforme
  - ALLORA il sistema chiude la segnalazione e lascia il contenuto visibile

- Scenario 3: Utente non moderatore
  - DATO che l'utente non ha il ruolo di moderatore
  - QUANDO l'utente cerca di rimuovere un contenuto segnalato
  - ALLORA il sistema il sistema nega l'azione

---

TITOLO: Impostazione: account

USER STORY:
Come Utente registrato,
Voglio modificare email e password e disattivare o eliminare il mio account,
In modo da controllare i miei dati e la mia presenza su wuxer.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Cambio password
  - DATO che l'utente ha effettuato l'accesso
  - QUANDO l'utente inserisce la password attuale e una nuova password valida
  - ALLORA il sistema aggiorna la password e la salva con hash

- Scenario 2: Password attuale errata
  - DATO che l'utente è nella pagina delle impostazioni account
  - QUANDO l'utente inserisce una password attuale sbagliata
  - ALLORA il sistema rifiuta la modifica e mostra un errore

- Scenario 3: Eliminazione account
  - DATO che l'utente ha effettuato l'accesso
  - QUANDO l'utente conferma l'eliminazione del proprio account
  - ALLORA il sistema elimina l'account e i dati personali associati

---

TITOLO: Impostazione: parte legale

USER STORY:
Come Utente registrato,
Voglio consultare termini di servizio e informativa sulla privacy,
In modo da sapere come vengono trattati i miei dati.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Consultazione dei documenti
  - DATO che l'utente ha effettuato l'accesso
  - QUANDO l'utente apre la sezione legale delle impostazioni
  - ALLORA il sistema mostra termini di servizio e informativa sulla privacy

- Scenario 2: Accettazione alla registrazione
  - DATO che un visitatore sta per registrarsi
  - QUANDO l'utente tenta di completare la registrazione senza accettare i documenti
  - ALLORA il sistema impedisce la registrazione finché non accetta

---

TITOLO: Hashtag post

USER STORY:
Come Utente registrato,
Voglio inserire hashtag nei miei post e vedere i post con un certo hashtag,
In modo da rendere i miei contenuti facili da trovare.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Hashtag nel post
  - DATO che l'utente sta scrivendo la descrizione di un post
  - QUANDO l'utente inserisce #viaggi e pubblica
  - ALLORA il sistema riconosce l'hashtag e lo rende cliccabile

- Scenario 2: Pagina dell'hashtag
  - DATO che esistono post con l'hashtag #viaggi
  - QUANDO l'utente l'utente clicca sull'hashtag
  - ALLORA il sistema mostra l'elenco dei post con quell'hashtag

- Scenario 3: Hashtag senza post
  - DATO che nessun post usa un certo hashtag
  - QUANDO l'utente l'utente lo apre
  - ALLORA il sistema mostra un messaggio che non ci sono contenuti

---

TITOLO: Ricerca account

USER STORY:
Come Utente registrato,
Voglio cercare altri profili per nome utente,
In modo da trovare e seguire le persone che conosco.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Ricerca riuscita
  - DATO che esiste un profilo con nome utente "mario"
  - QUANDO l'utente l'utente cerca "mar"
  - ALLORA il sistema mostra i profili corrispondenti, tra cui "mario"

- Scenario 2: Nessun risultato
  - DATO che nessun profilo corrisponde al testo cercato
  - QUANDO l'utente l'utente avvia la ricerca
  - ALLORA il sistema mostra un messaggio di nessun risultato

---

TITOLO: Ricerca post

USER STORY:
Come Utente registrato,
Voglio cercare post tramite parole, hashtag e ricerca avanzata (data, keyword),
In modo da trovare i contenuti che mi interessano.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Ricerca per parola o hashtag
  - DATO che esistono post con la parola "mare"
  - QUANDO l'utente l'utente cerca "mare"
  - ALLORA il sistema mostra i post che la contengono

- Scenario 2: Ricerca avanzata
  - DATO che l'utente apre la ricerca avanzata
  - QUANDO l'utente imposta un intervallo di date e una keyword
  - ALLORA il sistema mostra solo i post compresi nell'intervallo che contengono la keyword

- Scenario 3: Nessun risultato
  - DATO che nessun post corrisponde ai criteri
  - QUANDO l'utente l'utente avvia la ricerca
  - ALLORA il sistema mostra un messaggio di nessun risultato

---

TITOLO: Impostazione: preferenze

USER STORY:
Come Utente registrato,
Voglio impostare lingua, tema e preferenze di notifica,
In modo da adattare l'app alle mie abitudini.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Modifica delle preferenze
  - DATO che l'utente ha effettuato l'accesso
  - QUANDO l'utente cambia lingua e tema e salva
  - ALLORA il sistema applica subito le preferenze e le mantiene ai login successivi

- Scenario 2: Notifiche disattivate
  - DATO che l'utente ha disattivato un tipo di notifica
  - QUANDO l'utente accade un evento di quel tipo
  - ALLORA il sistema il sistema non invia la notifica

---

TITOLO: Impostazione: informazioni app e account

USER STORY:
Come Utente registrato,
Voglio vedere le informazioni sull'app e sul mio account,
In modo da conoscere la versione dell'app e i dati del mio profilo.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Visualizzazione informazioni
  - DATO che l'utente ha effettuato l'accesso
  - QUANDO l'utente apre la sezione informazioni
  - ALLORA il sistema mostra la versione dell'app e la data di registrazione

---

TITOLO: Notifiche

USER STORY:
Come Utente registrato,
Voglio ricevere notifiche su nuovi follower, like, commenti e messaggi,
In modo da non perdere le interazioni con i miei contenuti.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Notifica di un'interazione
  - DATO che l'utente ha le notifiche attive
  - QUANDO l'utente un altro utente lo segue, mette like o commenta
  - ALLORA il sistema invia una notifica all'utente

- Scenario 2: Lettura della notifica
  - DATO che l'utente ha notifiche non lette
  - QUANDO l'utente apre la notifica
  - ALLORA il sistema la segna come letta e mostra il contenuto collegato

- Scenario 3: Notifiche disattivate
  - DATO che l'utente ha disattivato le notifiche
  - QUANDO l'utente accade un evento
  - ALLORA il sistema non invia nessuna notifica

---

TITOLO: Chat private

USER STORY:
Come Utente registrato,
Voglio scambiare messaggi privati con un altro utente,
In modo da comunicare in modo riservato.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Invio di un messaggio
  - DATO che l'utente ha una chat con un altro utente
  - QUANDO l'utente invia un messaggio
  - ALLORA il sistema lo cifra end-to-end e lo consegna al destinatario in meno di 1 secondo

- Scenario 2: Messaggio vuoto
  - DATO che l'utente è in una chat
  - QUANDO l'utente tenta di inviare un messaggio vuoto
  - ALLORA il sistema non lo invia

---

TITOLO: Visualizzazione tendenza

USER STORY:
Come Utente registrato,
Voglio vedere i contenuti di tendenza,
In modo da scoprire ciò che è popolare su wuxer.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Contenuti di tendenza
  - DATO che esistono contenuti con molte interazioni
  - QUANDO l'utente l'utente apre la sezione tendenza
  - ALLORA il sistema mostra i contenuti più popolari in base alle interazioni

- Scenario 2: Contenuto rimosso
  - DATO che un contenuto di tendenza viene rimosso dai moderatori
  - QUANDO l'utente l'utente apre la sezione tendenza
  - ALLORA il sistema non lo mostra più

---

TITOLO: Impostazione: utilizzo del tempo

USER STORY:
Come Utente registrato,
Voglio visualizzare e limitare il tempo di utilizzo dell'app,
In modo da usare wuxer in modo consapevole.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Visualizzazione del tempo
  - DATO che l'utente ha effettuato l'accesso
  - QUANDO l'utente apre la sezione utilizzo del tempo
  - ALLORA il sistema mostra il tempo trascorso sull'app

- Scenario 2: Limite raggiunto
  - DATO che l'utente ha impostato un limite giornaliero
  - QUANDO l'utente raggiunge il limite
  - ALLORA il sistema mostra un avviso che il tempo è esaurito

---

TITOLO: Chat di gruppo

USER STORY:
Come Utente registrato,
Voglio creare chat di gruppo e gestirne i partecipanti,
In modo da parlare con più persone insieme.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Creazione del gruppo
  - DATO che l'utente ha almeno un contatto
  - QUANDO l'utente crea un gruppo e aggiunge dei partecipanti
  - ALLORA il sistema crea la chat e ne rende il creatore amministratore

- Scenario 2: Rimozione di un partecipante
  - DATO che l'utente è amministratore del gruppo
  - QUANDO l'utente rimuove un partecipante
  - ALLORA il sistema il partecipante non può più leggere né scrivere nel gruppo

- Scenario 3: Gestione senza permessi
  - DATO che l'utente non è amministratore
  - QUANDO l'utente cerca di rimuovere un partecipante
  - ALLORA il sistema il sistema nega l'azione

---

TITOLO: Pubblicazione video

USER STORY:
Come Utente registrato,
Voglio pubblicare un video con titolo e descrizione,
In modo da condividere contenuti video.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Video pubblicato
  - DATO che l'utente ha effettuato l'accesso
  - QUANDO l'utente carica un video, inserisce titolo e descrizione e pubblica
  - ALLORA il sistema pubblica il video e lo rende visibile

- Scenario 2: Video non valido
  - DATO che l'utente sta caricando un video
  - QUANDO l'utente sceglie un file di formato non supportato o troppo grande
  - ALLORA il sistema rifiuta il file e indica i limiti ammessi

---

TITOLO: Interazioni video

USER STORY:
Come Utente registrato,
Voglio mettere like e commentare i video,
In modo da interagire con i creator.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Like e commento
  - DATO che un video è visibile
  - QUANDO l'utente l'utente mette like e scrive un commento
  - ALLORA il sistema registra le interazioni e le mostra sotto il video

- Scenario 2: Like duplicato
  - DATO che l'utente ha già messo like a un video
  - QUANDO l'utente preme di nuovo il like
  - ALLORA il sistema rimuove il like senza registrarne uno secondo

---

TITOLO: Abbonamenti creators

USER STORY:
Come Creator,
Voglio sottoscrivere un abbonamento a wuxer,
In modo da ottenere vantaggi dedicati ai creator.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Abbonamento attivato
  - DATO che il creator ha effettuato l'accesso
  - QUANDO l'utente sceglie un abbonamento e completa il pagamento
  - ALLORA il sistema attiva l'abbonamento e rende fruibili i vantaggi

- Scenario 2: Pagamento non riuscito
  - DATO che il creator sta sottoscrivendo un abbonamento
  - QUANDO l'utente il pagamento fallisce
  - ALLORA il sistema non attiva l'abbonamento e mostra l'errore

- Scenario 3: Abbonamento scaduto
  - DATO che l'abbonamento del creator è scaduto
  - QUANDO l'utente il creator cerca di usare un vantaggio
  - ALLORA il sistema il sistema nega l'accesso al vantaggio

---

TITOLO: Impostazione: configurazione AI

USER STORY:
Come Utente registrato,
Voglio attivare, disattivare e configurare le funzionalità AI,
In modo da decidere se e come usarle.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Attivazione
  - DATO che l'utente ha le funzionalità AI disattivate
  - QUANDO l'utente le attiva e salva
  - ALLORA il sistema salva l'impostazione e rende disponibili le funzionalità AI

- Scenario 2: Disattivazione
  - DATO che l'utente ha le funzionalità AI attive
  - QUANDO l'utente le disattiva
  - ALLORA il sistema non mostra più alcun suggerimento AI

---

TITOLO: Generazione suggerimenti AI nei post e nei video

USER STORY:
Come Utente registrato,
Voglio ricevere suggerimenti AI per descrizioni e hashtag mentre creo un post o un video,
In modo da creare contenuti migliori più rapidamente.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Suggerimento accettato
  - DATO che l'utente ha le funzionalità AI attive e sta creando un post
  - QUANDO l'utente richiede un suggerimento e lo accetta
  - ALLORA il sistema inserisce il suggerimento nel contenuto indicandolo come generato da AI

- Scenario 2: Suggerimento ignorato
  - DATO che l'utente ha ricevuto un suggerimento
  - QUANDO l'utente lo ignora
  - ALLORA il sistema non modifica il contenuto

- Scenario 3: AI disattivata
  - DATO che l'utente ha le funzionalità AI disattivate
  - QUANDO l'utente crea un post o un video
  - ALLORA il sistema non mostra alcun suggerimento

