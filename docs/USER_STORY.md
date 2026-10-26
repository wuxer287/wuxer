# Wuxer - User story

TITOLO: Registrazione/login

USER STORY:
**Come** Visitatore,
**Voglio** registrarmi e accedere con email e password oppure con Google o Apple,
**In modo da** poter usare wuxer con il mio account.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Registrazione con email e password
  - **DATO** che l'utente non ha un account
  - **QUANDO** l'utente inserisce un'email non ancora registrata e una password valida
  - **ALLORA** il sistema invia un codice di verifica all'email e, dopo l'inserimento del codice corretto, crea l'account, salva la password con hash e permette l'accesso

- Scenario 2: Registrazione non consentita
  - **DATO** che l'email è già registrata oppure la password non rispetta i requisiti minimi
  - **QUANDO** l'utente invia il modulo di registrazione
  - **ALLORA** il sistema rifiuta la registrazione e mostra il motivo

- Scenario 3: Registrazione bloccata per età
  - **DATO** che dalla data di nascita indicata l'utente ha meno di 14 anni
  - **QUANDO** l'utente tenta di registrarsi
  - **ALLORA** il sistema blocca la registrazione e mostra un messaggio che ne spiega il motivo e indica i termini di servizio da consultare

- Scenario 4: Data di nascita mancante
  - **DATO** che l'utente sta compilando la registrazione
  - **QUANDO** l'utente invia il modulo senza indicare la data di nascita
  - **ALLORA** il sistema non crea l'account e chiede di indicarla

- Scenario 5: Accesso con email e password
  - **DATO** che l'utente ha un account
  - **QUANDO** l'utente inserisce email e password corrette
  - **ALLORA** il sistema apre il suo account e mantiene la sessione attiva sul dispositivo

- Scenario 6: Credenziali errate
  - **DATO** che l'utente ha un account
  - **QUANDO** l'utente inserisce una password errata
  - **ALLORA** il sistema nega l'accesso con un messaggio generico

- Scenario 7: Blocco dopo tentativi falliti
  - **DATO** che l'utente ha sbagliato la password 3 volte consecutive
  - **QUANDO** l'utente tenta un altro accesso
  - **ALLORA** il sistema blocca l'accesso per 60 minuti e mostra un avviso

- Scenario 8: Accesso con Google o Apple
  - **DATO** che l'utente ha un account Google o Apple
  - **QUANDO** l'utente sceglie di accedere con Google o Apple
  - **ALLORA** il sistema autentica l'utente tramite il provider e apre il suo account

- Scenario 9: Codice di verifica errato
  - **DATO** che l'utente ha ricevuto il codice di verifica via email
  - **QUANDO** l'utente inserisce un codice errato o scaduto
  - **ALLORA** il sistema non crea l'account e permette di richiedere un nuovo codice

- Scenario 10: Scelta dei dati dopo la verifica
  - **DATO** che l'utente ha inserito il codice di verifica corretto
  - **QUANDO** l'utente sceglie nome utente, nome visualizzato e data di nascita
  - **ALLORA** il sistema completa la registrazione e permette di aggiungere foto e biografia in seguito dal profilo

---

TITOLO: Profilo

USER STORY:
**Come** Utente registrato,
**Voglio** modificare le informazioni del mio profilo,
**In modo da** presentarmi agli altri utenti come preferisco.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Modifica delle informazioni del profilo
  - **DATO** che l'utente ha effettuato l'accesso
  - **QUANDO** l'utente modifica la foto, il nome visualizzato, la biografia o i link e salva
  - **ALLORA** il sistema salva le modifiche e le mostra subito sul profilo

- Scenario 2: Cambio del nome utente
  - **DATO** che l'utente ha effettuato l'accesso
  - **QUANDO** l'utente sceglie un nuovo nome utente non usato da altri
  - **ALLORA** il sistema aggiorna il nome utente

- Scenario 3: Nome utente già in uso
  - **DATO** che un altro profilo usa già un certo nome utente
  - **QUANDO** l'utente tenta di scegliere quel nome utente
  - **ALLORA** il sistema rifiuta la modifica e chiede un altro nome utente

- Scenario 4: Visualizzazione di un profilo pubblico
  - **DATO** che un profilo è pubblico
  - **QUANDO** un utente apre quel profilo
  - **ALLORA** il sistema mostra il profilo a tutti

- Scenario 5: Impostazione del profilo come privato
  - **DATO** che l'utente ha effettuato l'accesso
  - **QUANDO** l'utente imposta il proprio profilo come privato
  - **ALLORA** il sistema rende visibili i contenuti del profilo solo ai follower

- Scenario 6: Visualizzazione di un profilo privato da un non follower
  - **DATO** che un profilo è privato e l'utente non lo segue
  - **QUANDO** l'utente apre quel profilo
  - **ALLORA** il sistema non mostra i contenuti del profilo

- Scenario 7: Limiti non rispettati
  - **DATO** che l'utente sta modificando il profilo
  - **QUANDO** l'utente inserisce una biografia di oltre 150 caratteri oppure una foto di oltre 5 MB o non in formato JPG o PNG
  - **ALLORA** il sistema non salva la modifica e indica il limite superato

---

TITOLO: Pubblicazione storie

USER STORY:
**Come** Utente registrato,
**Voglio** pubblicare una storia con immagini e testo,
**In modo da** condividere un momento temporaneo.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Storia pubblicata
  - **DATO** che l'utente ha effettuato l'accesso
  - **QUANDO** l'utente carica un'immagine e/o scrive un testo e pubblica
  - **ALLORA** il sistema pubblica la storia

- Scenario 2: Visibilità con profilo pubblico
  - **DATO** che il profilo dell'autore è pubblico
  - **QUANDO** l'autore pubblica una storia
  - **ALLORA** il sistema la rende visibile a tutti

- Scenario 3: Visibilità con profilo privato
  - **DATO** che il profilo dell'autore è privato
  - **QUANDO** l'autore pubblica una storia
  - **ALLORA** il sistema la rende visibile solo ai follower

- Scenario 4: Scadenza della storia
  - **DATO** che una storia è stata pubblicata da 24 ore
  - **QUANDO** scorrono le 24 ore
  - **ALLORA** il sistema rimuove automaticamente la storia dalla visualizzazione degli altri utenti

- Scenario 5: Archiviazione della storia
  - **DATO** che l'autore ha pubblicato una storia
  - **QUANDO** l'autore sceglie di archiviarla
  - **ALLORA** il sistema la archivia e la rimuove dalla visualizzazione degli altri utenti, come se fosse scaduta

- Scenario 6: Visualizzazioni della storia
  - **DATO** che altri utenti hanno visto la storia
  - **QUANDO** l'autore apre la propria storia
  - **ALLORA** il sistema mostra all'autore chi l'ha vista

- Scenario 7: Storia vuota
  - **DATO** che l'utente è nella schermata di creazione
  - **QUANDO** l'utente tenta di pubblicare senza immagine né testo
  - **ALLORA** il sistema impedisce la pubblicazione e mostra un avviso

---

TITOLO: Pubblicazione post

USER STORY:
**Come** Utente registrato,
**Voglio** pubblicare un post con immagini e descrizione,
**In modo da** condividere contenuti duraturi sul mio profilo.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Post pubblicato
  - **DATO** che l'utente ha effettuato l'accesso
  - **QUANDO** l'utente carica da 1 a 50 immagini (ciascuna fino a 10 MB, in JPG, PNG o WebP) e pubblica
  - **ALLORA** il sistema pubblica il post sul profilo

- Scenario 2: Descrizione facoltativa
  - **DATO** che l'utente sta creando un post con almeno un'immagine
  - **QUANDO** l'utente pubblica senza scrivere la descrizione
  - **ALLORA** il sistema pubblica il post senza descrizione

- Scenario 3: Troppe immagini
  - **DATO** che l'utente sta creando un post
  - **QUANDO** l'utente tenta di caricare più di 50 immagini
  - **ALLORA** il sistema impedisce l'aggiunta e mostra un avviso sul limite

- Scenario 4: Post senza immagini
  - **DATO** che l'utente sta creando un post
  - **QUANDO** l'utente tenta di pubblicare senza alcuna immagine
  - **ALLORA** il sistema impedisce la pubblicazione e mostra un avviso

- Scenario 5: Modifica della descrizione
  - **DATO** che l'utente ha pubblicato un post
  - **QUANDO** l'utente modifica la descrizione e salva
  - **ALLORA** il sistema aggiorna la descrizione, mentre le immagini restano invariate

- Scenario 6: Eliminazione del post
  - **DATO** che l'utente ha pubblicato un post
  - **QUANDO** l'utente sceglie di eliminarlo e conferma
  - **ALLORA** il sistema elimina il post

- Scenario 7: Archiviazione del post
  - **DATO** che l'utente ha pubblicato un post
  - **QUANDO** l'utente sceglie di archiviarlo
  - **ALLORA** il sistema lo archivia e lo rimuove dalla visualizzazione degli altri utenti

- Scenario 8: Ripristino di un post archiviato
  - **DATO** che l'utente ha archiviato un post
  - **QUANDO** l'utente lo ripristina
  - **ALLORA** il sistema lo rende di nuovo visibile agli altri utenti, secondo la visibilità del profilo

- Scenario 9: Limiti non rispettati
  - **DATO** che l'utente sta creando un post
  - **QUANDO** l'utente inserisce una descrizione di oltre 2.000 caratteri oppure un'immagine di oltre 10 MB o in un formato non ammesso
  - **ALLORA** il sistema non pubblica il post e indica il limite superato

---

TITOLO: Follow

USER STORY:
**Come** Utente registrato,
**Voglio** seguire e smettere di seguire altri profili e rimuovere i miei follower,
**In modo da** vedere i contenuti dei profili che mi interessano e controllare chi segue me.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Seguire un profilo pubblico
  - **DATO** che l'utente visualizza un profilo pubblico che non segue
  - **QUANDO** l'utente preme "Segui"
  - **ALLORA** il sistema registra il follow e aggiorna subito il conteggio dei follower

- Scenario 2: Richiesta di follow a un profilo privato
  - **DATO** che l'utente visualizza un profilo privato che non segue
  - **QUANDO** l'utente preme "Segui"
  - **ALLORA** il sistema invia una richiesta di follow al proprietario del profilo, senza dare accesso ai contenuti

- Scenario 3: Approvazione della richiesta
  - **DATO** che un profilo privato ha ricevuto una richiesta di follow
  - **QUANDO** il proprietario approva la richiesta
  - **ALLORA** il sistema registra il follow e rende visibili i contenuti al nuovo follower

- Scenario 4: Rifiuto della richiesta
  - **DATO** che un profilo privato ha ricevuto una richiesta di follow
  - **QUANDO** il proprietario rifiuta la richiesta
  - **ALLORA** il sistema elimina la richiesta e non registra il follow

- Scenario 5: Smettere di seguire
  - **DATO** che l'utente segue un profilo
  - **QUANDO** l'utente sceglie "Non seguire più"
  - **ALLORA** il sistema chiede una conferma

- Scenario 6: Conferma di non seguire più
  - **DATO** che il sistema ha chiesto la conferma per smettere di seguire
  - **QUANDO** l'utente conferma
  - **ALLORA** il sistema rimuove il follow e i contenuti di quel profilo non compaiono più nel feed

- Scenario 7: Rimozione di un follower
  - **DATO** che un altro utente segue il profilo dell'utente
  - **QUANDO** l'utente rimuove quel follower
  - **ALLORA** il sistema elimina il follow e il follower non vede più i contenuti, se il profilo è privato

- Scenario 8: Seguire se stessi
  - **DATO** che l'utente visualizza il proprio profilo
  - **QUANDO** l'utente cerca di seguire se stesso
  - **ALLORA** il sistema non offre l'azione

---

TITOLO: Interazioni storie

USER STORY:
**Come** Utente registrato,
**Voglio** mettere like e commentare le storie,
**In modo da** interagire con chi le pubblica.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Like a una storia
  - **DATO** che l'utente vede una storia non scaduta
  - **QUANDO** l'utente mette like
  - **ALLORA** il sistema registra il like e lo mostra all'autore

- Scenario 2: Rimozione del like
  - **DATO** che l'utente ha già messo like a una storia
  - **QUANDO** l'utente preme di nuovo il like
  - **ALLORA** il sistema rimuove il like senza registrarne un secondo

- Scenario 3: Commento a una storia
  - **DATO** che l'utente vede una storia non scaduta
  - **QUANDO** l'utente scrive un commento fino a 100 caratteri e lo invia
  - **ALLORA** il sistema pubblica il commento e lo rende visibile a tutti

- Scenario 4: Risposta a un commento
  - **DATO** che una storia ha dei commenti
  - **QUANDO** l'utente risponde a un commento
  - **ALLORA** il sistema pubblica la risposta sotto quel commento

- Scenario 5: Commento troppo lungo
  - **DATO** che l'utente sta scrivendo un commento
  - **QUANDO** il testo supera i 100 caratteri
  - **ALLORA** il sistema impedisce l'invio e mostra un avviso sul limite

- Scenario 6: Commento vuoto
  - **DATO** che l'utente sta commentando una storia
  - **QUANDO** l'utente invia un commento senza testo
  - **ALLORA** il sistema non pubblica il commento e mostra un avviso

- Scenario 7: Storia scaduta
  - **DATO** che una storia è scaduta o è stata archiviata
  - **QUANDO** l'utente cerca di interagire con essa
  - **ALLORA** il sistema non la mostra e non accetta interazioni

---

TITOLO: Interazioni post

USER STORY:
**Come** Utente registrato,
**Voglio** mettere like, commentare e condividere i post,
**In modo da** interagire con gli altri utenti.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Like a un post
  - **DATO** che l'utente vede un post
  - **QUANDO** l'utente mette like
  - **ALLORA** il sistema registra il like e il numero di like è visibile a tutti

- Scenario 2: Rimozione del like
  - **DATO** che l'utente ha già messo like a un post
  - **QUANDO** l'utente preme di nuovo il like
  - **ALLORA** il sistema rimuove il like senza registrarne un secondo

- Scenario 3: Commento a un post
  - **DATO** che l'utente vede un post con i commenti attivi
  - **QUANDO** l'utente scrive un commento fino a 800 caratteri e lo invia
  - **ALLORA** il sistema pubblica il commento e lo rende visibile a tutti

- Scenario 4: Risposta a un commento
  - **DATO** che un post ha dei commenti
  - **QUANDO** l'utente risponde a un commento
  - **ALLORA** il sistema pubblica la risposta sotto quel commento

- Scenario 5: Like a un commento
  - **DATO** che un post ha dei commenti
  - **QUANDO** l'utente mette like a un commento
  - **ALLORA** il sistema registra il like al commento

- Scenario 6: Eliminazione del proprio commento
  - **DATO** che l'utente ha commentato un post
  - **QUANDO** l'utente elimina il proprio commento
  - **ALLORA** il sistema lo rimuove dal post; se il commento ha risposte, al suo posto appare "Contenuto eliminato"

- Scenario 7: Eliminazione di un commento da parte dell'autore del post
  - **DATO** che un post ha dei commenti di altri utenti
  - **QUANDO** l'autore del post elimina uno di questi commenti
  - **ALLORA** il sistema rimuove il commento dal post; se il commento ha risposte, al suo posto appare "Contenuto eliminato"

- Scenario 8: Commenti disattivati
  - **DATO** che l'autore ha disattivato i commenti del post
  - **QUANDO** un utente apre il post
  - **ALLORA** il sistema non permette di commentare

- Scenario 9: Commento vuoto
  - **DATO** che l'utente sta scrivendo un commento
  - **QUANDO** l'utente invia un commento senza testo
  - **ALLORA** il sistema impedisce l'invio e mostra un avviso

- Scenario 10: Commento troppo lungo
  - **DATO** che l'utente sta scrivendo un commento
  - **QUANDO** il testo supera gli 800 caratteri
  - **ALLORA** il sistema non lo pubblica e mostra un avviso sul limite

- Scenario 11: Condivisione del post
  - **DATO** che l'utente vede un post
  - **QUANDO** l'utente sceglie di condividerlo
  - **ALLORA** il sistema permette di copiare il link del post o di inviarlo in una chat; il link si apre solo agli utenti con un account e, se il profilo è privato, solo ai follower

---

TITOLO: Feed

USER STORY:
**Come** Utente registrato,
**Voglio** vedere in una pagina i contenuti di altri profili in base alle mie interazioni,
**In modo da** scoprire contenuti che mi interessano.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Feed in base alle interazioni
  - **DATO** che l'utente ha effettuato l'accesso e ha già interagito con alcuni contenuti
  - **QUANDO** l'utente apre il feed
  - **ALLORA** il sistema mostra contenuti di altri profili scelti in base alle sue interazioni, ordinati per rilevanza rispetto alle interazioni e alla data di pubblicazione

- Scenario 2: Utente senza interazioni
  - **DATO** che l'utente non ha ancora interazioni
  - **QUANDO** l'utente apre il feed
  - **ALLORA** il sistema mostra i contenuti più popolari del momento dei profili pubblici invece di una pagina vuota

- Scenario 3: Caricamento progressivo
  - **DATO** che l'utente è nel feed
  - **QUANDO** l'utente scorre verso il basso
  - **ALLORA** il sistema carica altri contenuti a blocchi, mostrati a griglia

- Scenario 4: Contenuto rimosso
  - **DATO** che un contenuto è stato rimosso dai moderatori
  - **QUANDO** l'utente apre il feed
  - **ALLORA** il sistema non mostra più quel contenuto

- Scenario 5: Contenuti di profili privati
  - **DATO** che un profilo è privato, anche se l'utente lo segue
  - **QUANDO** l'utente apre il feed
  - **ALLORA** il sistema non mostra mai i contenuti di quel profilo, ma solo quelli dei profili pubblici

---

TITOLO: Segnalazione dei contenuti

USER STORY:
**Come** Utente registrato,
**Voglio** segnalare storie, post, commenti e messaggi indicando un motivo,
**In modo da** contribuire a mantenere sicura la community.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Segnalazione riuscita
  - **DATO** che l'utente vede una storia, un post o un commento inappropriato
  - **QUANDO** l'utente sceglie "Segnala", indica un motivo tra spam, violenza o contenuti pericolosi, molestie, contenuti inappropriati, altro e scrive una descrizione libera
  - **ALLORA** il sistema registra la segnalazione e conferma la ricezione all'utente

- Scenario 2: Segnalazione di un messaggio privato
  - **DATO** che l'utente ha ricevuto un messaggio in una chat privata end-to-end
  - **QUANDO** l'utente segnala quel messaggio
  - **ALLORA** il sistema invia ai moderatori solo il messaggio segnalato, senza compromettere il resto della chat

- Scenario 3: Segnalazioni ripetute
  - **DATO** che l'utente ha già segnalato un contenuto
  - **QUANDO** l'utente lo segnala di nuovo
  - **ALLORA** il sistema registra la nuova segnalazione

- Scenario 4: Esito della segnalazione
  - **DATO** che i moderatori hanno esaminato la segnalazione
  - **QUANDO** l'esame è concluso
  - **ALLORA** il sistema comunica l'esito all'utente che ha segnalato

- Scenario 5: Autore non avvisato
  - **DATO** che un contenuto è stato segnalato
  - **QUANDO** la segnalazione viene registrata
  - **ALLORA** il sistema non avvisa l'autore del contenuto della segnalazione

- Scenario 6: Motivo mancante
  - **DATO** che l'utente sta compilando una segnalazione
  - **QUANDO** l'utente la invia senza indicare un motivo
  - **ALLORA** il sistema non la registra e chiede di indicare un motivo

---

TITOLO: Segnalazione profili

USER STORY:
**Come** Utente registrato,
**Voglio** segnalare un altro profilo indicando un motivo,
**In modo da** contribuire a mantenere sicura la community.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Segnalazione riuscita
  - **DATO** che l'utente visita il profilo di un altro utente
  - **QUANDO** l'utente sceglie "Segnala profilo", indica un motivo tra spam, profilo falso o furto d'identità, molestie, contenuti inappropriati, altro e scrive una descrizione libera
  - **ALLORA** il sistema registra la segnalazione e conferma la ricezione all'utente

- Scenario 2: Profilo segnalato non avvisato
  - **DATO** che un profilo è stato segnalato
  - **QUANDO** la segnalazione viene registrata
  - **ALLORA** il sistema non avvisa il proprietario del profilo

- Scenario 3: Segnalazione del proprio profilo
  - **DATO** che l'utente visita il proprio profilo
  - **QUANDO** l'utente cerca di segnalarlo
  - **ALLORA** il sistema non offre l'opzione di segnalazione

- Scenario 4: Esito della segnalazione
  - **DATO** che i moderatori hanno esaminato la segnalazione del profilo
  - **QUANDO** l'esame è concluso
  - **ALLORA** il sistema comunica l'esito all'utente che ha segnalato

- Scenario 5: Motivo mancante
  - **DATO** che l'utente sta compilando la segnalazione di un profilo
  - **QUANDO** l'utente la invia senza indicare un motivo
  - **ALLORA** il sistema non la registra e chiede di indicare un motivo

---

TITOLO: Moderazione dei contenuti

USER STORY:
**Come** Moderatore,
**Voglio** esaminare le segnalazioni e rimuovere i contenuti,
**In modo da** garantire il rispetto delle regole della community.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Rimozione di un contenuto
  - **DATO** che esiste una segnalazione in attesa
  - **QUANDO** il moderatore la esamina e decide di rimuovere il contenuto
  - **ALLORA** il sistema rimuove il contenuto e segna la segnalazione come gestita

- Scenario 2: Avviso all'autore
  - **DATO** che il moderatore ha rimosso un contenuto
  - **QUANDO** la rimozione è completata
  - **ALLORA** il sistema avvisa l'autore che il contenuto è stato rimosso

- Scenario 3: Sanzione all'autore
  - **DATO** che il moderatore ha rimosso un contenuto
  - **QUANDO** la rimozione è completata
  - **ALLORA** il sistema registra uno strike a carico dell'autore e, al 3° strike, propone la sospensione dell'account e, al 5°, il ban

- Scenario 4: Segnalazione infondata
  - **DATO** che esiste una segnalazione in attesa
  - **QUANDO** il moderatore decide che il contenuto è conforme
  - **ALLORA** il sistema chiude la segnalazione, lascia il contenuto visibile e comunica l'esito a chi ha segnalato

- Scenario 5: Contestazione della decisione
  - **DATO** che a un utente è stato rimosso un contenuto
  - **QUANDO** l'utente contesta la decisione entro 7 giorni
  - **ALLORA** il sistema registra la contestazione e la sottopone a un nuovo esame da parte di un moderatore, anche lo stesso della prima decisione, entro 12 ore

- Scenario 6: Utente non moderatore
  - **DATO** che l'utente non ha il ruolo di moderatore
  - **QUANDO** l'utente tenta di rimuovere un contenuto segnalato
  - **ALLORA** il sistema nega l'azione

---

TITOLO: Sospensione e ban account

USER STORY:
**Come** Moderatore,
**Voglio** sospendere o bannare un account,
**In modo da** impedire l'uso dell'app a chi viola ripetutamente o gravemente le regole.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Sospensione di un account
  - **DATO** che esiste una segnalazione su un profilo oppure l'utente ha raggiunto 3 strike
  - **QUANDO** il moderatore sospende l'account e sceglie la durata tra 7, 30 e 90 giorni
  - **ALLORA** il sistema impedisce all'utente di accedere all'app fino alla scadenza e gli comunica il motivo e la durata della sospensione

- Scenario 2: Ban di un account
  - **DATO** che l'utente ha raggiunto 5 strike oppure ha commesso una violazione grave delle regole
  - **QUANDO** il moderatore banna l'account
  - **ALLORA** il sistema impedisce in modo permanente l'accesso all'app e comunica il motivo all'utente

- Scenario 3: Fine della sospensione
  - **DATO** che l'account dell'utente è sospeso e la durata è scaduta
  - **QUANDO** l'utente tenta di accedere
  - **ALLORA** il sistema riattiva l'account e permette l'accesso

- Scenario 4: Accesso con account sospeso o bannato
  - **DATO** che l'account dell'utente è sospeso o bannato
  - **QUANDO** l'utente tenta di accedere
  - **ALLORA** il sistema nega l'accesso e mostra il motivo

- Scenario 5: Sessione già attiva
  - **DATO** che l'utente ha una sessione attiva su un dispositivo
  - **QUANDO** il moderatore sospende o banna il suo account
  - **ALLORA** il sistema termina la sessione e nega ulteriori accessi

- Scenario 6: Utente non moderatore
  - **DATO** che l'utente non ha il ruolo di moderatore
  - **QUANDO** l'utente tenta di sospendere o bannare un account
  - **ALLORA** il sistema nega l'azione

---

TITOLO: Impostazione: account

USER STORY:
**Come** Utente registrato,
**Voglio** modificare email e password, eliminare il mio account e scaricare i miei dati,
**In modo da** controllare i miei dati e la mia presenza su wuxer.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Cambio password
  - **DATO** che l'utente ha effettuato l'accesso
  - **QUANDO** l'utente inserisce la password attuale e una nuova password valida
  - **ALLORA** il sistema aggiorna la password e la salva con hash

- Scenario 2: Password attuale errata
  - **DATO** che l'utente è nella pagina delle impostazioni account
  - **QUANDO** l'utente inserisce una password attuale sbagliata
  - **ALLORA** il sistema rifiuta la modifica e mostra un errore

- Scenario 3: Cambio email
  - **DATO** che l'utente ha effettuato l'accesso
  - **QUANDO** l'utente inserisce la password attuale e una nuova email
  - **ALLORA** il sistema chiede di verificare la nuova email e la aggiorna solo dopo la verifica

- Scenario 4: Verifica dell'email non completata
  - **DATO** che l'utente ha chiesto di cambiare email
  - **QUANDO** la verifica della nuova email non viene completata
  - **ALLORA** il sistema mantiene la vecchia email

- Scenario 5: Eliminazione dell'account
  - **DATO** che l'utente ha effettuato l'accesso
  - **QUANDO** l'utente chiede di eliminare l'account e conferma con la password
  - **ALLORA** il sistema elimina l'account in modo irreversibile, non permette più l'accesso e rende subito invisibili agli altri utenti il profilo e i contenuti, conservando i dati per 180 giorni

- Scenario 6: Conservazione dei dati dopo l'eliminazione
  - **DATO** che un account è stato eliminato
  - **QUANDO** sono passati 180 giorni
  - **ALLORA** il sistema elimina definitivamente anche i dati rimasti

- Scenario 7: Conferma dell'eliminazione errata
  - **DATO** che l'utente ha chiesto di eliminare l'account
  - **QUANDO** l'utente inserisce una password errata
  - **ALLORA** il sistema non elimina l'account e mostra un errore

- Scenario 8: Scaricamento dei dati
  - **DATO** che l'utente ha effettuato l'accesso
  - **QUANDO** l'utente chiede una copia dei propri dati
  - **ALLORA** il sistema invia entro 7 giorni un link via email per scaricare un file ZIP con i suoi dati in JSON e i suoi media

---

TITOLO: Impostazione: parte legale

USER STORY:
**Come** Utente registrato,
**Voglio** consultare termini di servizio, informativa sulla privacy e linee guida,
**In modo da** sapere come vengono trattati i miei dati e quali regole valgono su wuxer.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Consultazione dei documenti
  - **DATO** che l'utente ha effettuato l'accesso
  - **QUANDO** l'utente apre la sezione legale nelle impostazioni
  - **ALLORA** il sistema mostra termini di servizio, informativa sulla privacy e linee guida

- Scenario 2: Accettazione alla registrazione
  - **DATO** che un visitatore sta per registrarsi
  - **QUANDO** il visitatore spunta la casella di accettazione di termini di servizio e informativa sulla privacy
  - **ALLORA** il sistema registra l'accettazione e permette di completare la registrazione

- Scenario 3: Registrazione senza accettazione
  - **DATO** che un visitatore sta per registrarsi
  - **QUANDO** il visitatore tenta di completare la registrazione senza accettare i documenti
  - **ALLORA** il sistema impedisce la registrazione e mostra un avviso

- Scenario 4: Aggiornamento dei documenti
  - **DATO** che i termini di servizio o l'informativa sulla privacy sono stati aggiornati
  - **QUANDO** l'utente accede all'app
  - **ALLORA** il sistema chiede di accettare di nuovo i documenti aggiornati prima di proseguire

---

TITOLO: Hashtag post

USER STORY:
**Come** Utente registrato,
**Voglio** inserire hashtag nei miei post e vedere i post con un certo hashtag,
**In modo da** rendere i miei contenuti più facili da trovare.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Hashtag nella descrizione
  - **DATO** che l'utente sta scrivendo la descrizione di un post
  - **QUANDO** l'utente inserisce nel testo fino a 10 hashtag, cioè parole precedute da # con lettere, numeri e underscore (ad esempio #vinciamo #contro), e pubblica
  - **ALLORA** il sistema riconosce gli hashtag e li rende cliccabili

- Scenario 2: Pagina dell'hashtag
  - **DATO** che esistono post con un certo hashtag
  - **QUANDO** l'utente clicca sull'hashtag
  - **ALLORA** il sistema mostra i post di profili pubblici con quell'hashtag, dal più recente

- Scenario 3: Modifica degli hashtag
  - **DATO** che l'utente ha pubblicato un post con degli hashtag
  - **QUANDO** l'utente modifica la descrizione aggiungendo o togliendo hashtag
  - **ALLORA** il sistema aggiorna gli hashtag del post

- Scenario 4: Hashtag senza post
  - **DATO** che nessun post usa un certo hashtag
  - **QUANDO** l'utente apre la pagina di quell'hashtag
  - **ALLORA** il sistema mostra un messaggio che non ci sono contenuti

- Scenario 5: Post di profili privati
  - **DATO** che un post appartiene a un profilo privato
  - **QUANDO** l'utente apre la pagina di un hashtag usato in quel post
  - **ALLORA** il sistema non mostra il post

- Scenario 6: Troppi hashtag
  - **DATO** che l'utente sta scrivendo la descrizione di un post
  - **QUANDO** l'utente inserisce più di 10 hashtag
  - **ALLORA** il sistema impedisce la pubblicazione e mostra un avviso sul limite

---

TITOLO: Ricerca account

USER STORY:
**Come** Utente registrato,
**Voglio** cercare altri profili per nome utente e nome visualizzato,
**In modo da** trovare e seguire le persone che mi interessano.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Ricerca riuscita
  - **DATO** che esiste un profilo con nome utente o nome visualizzato corrispondente
  - **QUANDO** l'utente inserisce il nome nella ricerca
  - **ALLORA** il sistema mostra 20 profili per volta, con altri caricati scorrendo, ordinati per somiglianza con il testo cercato; a parità di somiglianza compaiono prima i profili seguiti e poi i più popolari

- Scenario 2: Ricerca con testo parziale
  - **DATO** che esiste un profilo con nome utente "mario"
  - **QUANDO** l'utente cerca "mar"
  - **ALLORA** il sistema mostra tra i risultati anche il profilo "mario"

- Scenario 3: Profili privati nei risultati
  - **DATO** che esiste un profilo privato corrispondente alla ricerca
  - **QUANDO** l'utente avvia la ricerca
  - **ALLORA** il sistema mostra il profilo tra i risultati, senza i suoi contenuti

- Scenario 4: Nessun risultato
  - **DATO** che nessun profilo corrisponde al testo cercato
  - **QUANDO** l'utente avvia la ricerca
  - **ALLORA** il sistema mostra un messaggio di nessun risultato

---

TITOLO: Ricerca post

USER STORY:
**Come** Utente registrato,
**Voglio** cercare post tramite parole, hashtag e ricerca avanzata,
**In modo da** trovare i contenuti che mi interessano.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Ricerca per parole
  - **DATO** che esistono post semanticamente simili alle parole cercate
  - **QUANDO** l'utente cerca delle parole
  - **ALLORA** il sistema mostra i post con significato simile, anche se non contengono esattamente quelle parole

- Scenario 2: Ricerca per hashtag
  - **DATO** che esistono post con un certo hashtag
  - **QUANDO** l'utente cerca quell'hashtag
  - **ALLORA** il sistema mostra i post con quell'hashtag

- Scenario 3: Ricerca avanzata
  - **DATO** che l'utente apre la ricerca avanzata
  - **QUANDO** l'utente imposta un intervallo di date e una keyword specifica
  - **ALLORA** il sistema mostra solo i post compresi nell'intervallo che contengono esattamente quella keyword

- Scenario 4: Ordine dei risultati
  - **DATO** che la ricerca ha trovato più post
  - **QUANDO** il sistema mostra i risultati
  - **ALLORA** i post sono ordinati per popolarità e per quanto sono recenti

- Scenario 5: Post di profili privati
  - **DATO** che un post appartiene a un profilo privato
  - **QUANDO** l'utente avvia una ricerca che lo troverebbe
  - **ALLORA** il sistema non mostra il post

- Scenario 6: Cronologia delle ricerche
  - **DATO** che l'utente ha effettuato delle ricerche
  - **QUANDO** l'utente riapre la ricerca
  - **ALLORA** il sistema mostra le ricerche recenti, conservate per 30 giorni

- Scenario 7: Nessun risultato
  - **DATO** che nessun post corrisponde ai criteri
  - **QUANDO** l'utente avvia la ricerca
  - **ALLORA** il sistema mostra un messaggio di nessun risultato

---

TITOLO: Impostazione: preferenze

USER STORY:
**Come** Utente registrato,
**Voglio** impostare lingua, tema e preferenze di notifica,
**In modo da** adattare l'app alle mie abitudini.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Cambio della lingua
  - **DATO** che l'utente ha effettuato l'accesso
  - **QUANDO** l'utente sceglie una lingua tra quelle disponibili e salva
  - **ALLORA** il sistema applica subito la lingua scelta

- Scenario 2: Lingua predefinita
  - **DATO** che l'utente non ha scelto alcuna lingua
  - **QUANDO** l'utente usa l'app
  - **ALLORA** il sistema mostra l'app in inglese

- Scenario 3: Cambio del tema
  - **DATO** che l'utente ha effettuato l'accesso
  - **QUANDO** l'utente sceglie il tema chiaro o scuro
  - **ALLORA** il sistema applica subito il tema scelto

- Scenario 4: Notifiche per tipo
  - **DATO** che l'utente apre le preferenze di notifica
  - **QUANDO** l'utente disattiva un tipo di notifica (follower, like, commenti o messaggi)
  - **ALLORA** il sistema non invia più notifiche di quel tipo e continua a inviare le altre

- Scenario 5: Preferenze su tutti i dispositivi
  - **DATO** che l'utente ha salvato le sue preferenze
  - **QUANDO** l'utente accede da un altro dispositivo
  - **ALLORA** il sistema applica le stesse preferenze

---

TITOLO: Impostazione: informazioni app e account

USER STORY:
**Come** Utente registrato,
**Voglio** consultare le informazioni sull'app e sugli account,
**In modo da** conoscere la versione dell'app e i dati di un profilo.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Informazioni sull'app
  - **DATO** che l'utente ha effettuato l'accesso
  - **QUANDO** l'utente apre le informazioni sull'app
  - **ALLORA** il sistema mostra la versione dell'app

- Scenario 2: Informazioni sull'account
  - **DATO** che l'utente ha effettuato l'accesso
  - **QUANDO** l'utente apre le informazioni di un account
  - **ALLORA** il sistema mostra l'anno di creazione dell'account e lo stato in cui è stato creato

- Scenario 3: Account pubblici e privati
  - **DATO** che un account ha il profilo privato
  - **QUANDO** un altro utente registrato ne apre le informazioni
  - **ALLORA** il sistema le mostra comunque, come per un profilo pubblico

- Scenario 4: Visitatore senza account
  - **DATO** che il visitatore non ha un account
  - **QUANDO** il visitatore apre l'app
  - **ALLORA** il sistema mostra solo la homepage e il login

- Scenario 5: Informazioni non modificabili
  - **DATO** che l'utente sta consultando le informazioni sull'app o sull'account
  - **QUANDO** l'utente cerca di modificarle da quella sezione
  - **ALLORA** il sistema non offre alcuna modifica

---

TITOLO: Notifiche

USER STORY:
**Come** Utente registrato,
**Voglio** ricevere notifiche sulle attività che mi riguardano,
**In modo da** non perdere le interazioni con i miei contenuti.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Notifica di un evento
  - **DATO** che l'utente ha attivato quel tipo di notifica
  - **QUANDO** accade un evento che lo riguarda (nuovo follower, richiesta di follow, like, commento, risposta, messaggio, rimozione di un contenuto o messaggio generato dall'applicazione)
  - **ALLORA** il sistema invia una notifica nell'app e sul telefono

- Scenario 2: Notifica disattivata
  - **DATO** che l'utente ha disattivato un tipo di notifica
  - **QUANDO** accade un evento di quel tipo
  - **ALLORA** il sistema non invia alcuna notifica

- Scenario 3: Raggruppamento
  - **DATO** che più utenti hanno interagito con lo stesso contenuto
  - **QUANDO** il sistema invia le notifiche
  - **ALLORA** il sistema può raggrupparle in un'unica notifica

- Scenario 4: Lettura della notifica
  - **DATO** che l'utente ha notifiche non lette
  - **QUANDO** l'utente apre una notifica
  - **ALLORA** il sistema la segna come letta, mostra il contenuto collegato e aggiorna il contatore delle non lette

- Scenario 5: Conservazione delle notifiche
  - **DATO** che una notifica è stata inviata da 180 giorni
  - **QUANDO** scorrono i 180 giorni
  - **ALLORA** il sistema la elimina

---

TITOLO: Blocco utenti

USER STORY:
**Come** Utente registrato,
**Voglio** bloccare un altro utente,
**In modo da** impedirgli di contattarmi e di vedere i miei contenuti.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Blocco di un utente
  - **DATO** che l'utente visita il profilo di un altro utente
  - **QUANDO** l'utente sceglie "Blocca" e conferma
  - **ALLORA** il sistema blocca l'utente, annulla i follow tra i due profili e non avvisa l'utente bloccato

- Scenario 2: Contenuti non visibili
  - **DATO** che l'utente A ha bloccato l'utente B
  - **QUANDO** B cerca il profilo o i contenuti di A
  - **ALLORA** il sistema non mostra a B i contenuti di A

- Scenario 3: Messaggi non consentiti
  - **DATO** che l'utente A ha bloccato l'utente B
  - **QUANDO** B tenta di scrivere ad A
  - **ALLORA** il sistema impedisce l'invio dei messaggi; la chat esistente resta visibile ma non permette di scrivere

- Scenario 4: Sblocco di un utente
  - **DATO** che l'utente ha bloccato un altro utente
  - **QUANDO** l'utente lo sblocca dall'elenco dei bloccati nelle impostazioni dell'account
  - **ALLORA** il sistema ripristina la visibilità e la possibilità di scrivere

- Scenario 5: Blocco di se stessi
  - **DATO** che l'utente visita il proprio profilo
  - **QUANDO** l'utente cerca di bloccarsi
  - **ALLORA** il sistema non offre l'opzione di blocco

---

TITOLO: Feed profili seguiti

USER STORY:
**Come** Utente registrato,
**Voglio** vedere un feed con i soli contenuti dei profili che seguo, compresi quelli privati,
**In modo da** non perdere i contenuti delle persone a cui sono interessato.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Visualizzazione del feed dei seguiti
  - **DATO** che l'utente segue alcuni profili
  - **QUANDO** l'utente apre il feed dei profili seguiti
  - **ALLORA** il sistema mostra i post e i video dei soli profili seguiti, in ordine cronologico dal più recente; le storie restano fuori dal feed

- Scenario 2: Contenuti di profili privati
  - **DATO** che l'utente segue un profilo privato con richiesta approvata
  - **QUANDO** l'utente apre il feed dei profili seguiti
  - **ALLORA** il sistema include anche i contenuti di quel profilo

- Scenario 3: Interruzione del follow
  - **DATO** che l'utente smette di seguire un profilo
  - **QUANDO** l'utente riapre il feed dei profili seguiti
  - **ALLORA** il sistema non mostra più i contenuti di quel profilo

- Scenario 4: Profili bloccati
  - **DATO** che l'utente ha bloccato un profilo che seguiva
  - **QUANDO** l'utente apre il feed dei profili seguiti
  - **ALLORA** il sistema non mostra i contenuti di quel profilo

- Scenario 5: Nessun profilo seguito
  - **DATO** che l'utente non segue nessun profilo
  - **QUANDO** l'utente apre il feed dei profili seguiti
  - **ALLORA** il sistema mostra un messaggio che invita a seguire dei profili

---

TITOLO: Chat private

USER STORY:
**Come** Utente registrato,
**Voglio** scambiare messaggi privati con un altro utente,
**In modo da** comunicare in modo riservato.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Invio di un messaggio
  - **DATO** che l'utente può scrivere a un altro utente
  - **QUANDO** l'utente invia un messaggio di testo
  - **ALLORA** il sistema lo cifra end-to-end e lo consegna al destinatario in meno di 1 secondo

- Scenario 2: Stato del messaggio
  - **DATO** che l'utente ha inviato un messaggio
  - **QUANDO** il messaggio viene consegnato e poi letto dal destinatario
  - **ALLORA** il sistema mostra al mittente che il messaggio è stato consegnato e poi letto

- Scenario 3: Eliminazione di un proprio messaggio
  - **DATO** che l'utente ha inviato un messaggio
  - **QUANDO** l'utente elimina quel messaggio
  - **ALLORA** il sistema lo rimuove dalla chat di entrambi, senza limite di tempo; al suo posto appare "Messaggio eliminato"

- Scenario 4: Eliminazione del messaggio di un altro
  - **DATO** che l'altro utente ha inviato un messaggio
  - **QUANDO** l'utente cerca di eliminarlo per tutti
  - **ALLORA** il sistema non permette l'eliminazione

- Scenario 5: Impostazioni del destinatario
  - **DATO** che il destinatario ha impostato nelle impostazioni di ricevere messaggi solo dai profili che segue o da nessuno, e non segue l'utente
  - **QUANDO** l'utente tenta di scrivergli
  - **ALLORA** il sistema impedisce l'invio e mostra un avviso

- Scenario 6: Messaggio vuoto
  - **DATO** che l'utente è in una chat
  - **QUANDO** l'utente tenta di inviare un messaggio vuoto
  - **ALLORA** il sistema non lo invia

---

TITOLO: Visualizzazione tendenza

USER STORY:
**Come** Utente registrato,
**Voglio** vedere i post e i video di tendenza,
**In modo da** scoprire ciò che è popolare su wuxer.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Contenuti di tendenza
  - **DATO** che esistono post e video con molte interazioni
  - **QUANDO** l'utente apre la sezione tendenza
  - **ALLORA** il sistema mostra i post e i video più popolari in base alle interazioni, dove un like vale 1, un commento 2 e una condivisione 3

- Scenario 2: Periodo di calcolo
  - **DATO** che la tendenza si calcola sull'ultima settimana
  - **QUANDO** l'utente apre la sezione tendenza
  - **ALLORA** il sistema mostra solo contenuti con interazioni in quel periodo

- Scenario 3: Stessa tendenza per tutti
  - **DATO** che due utenti diversi aprono la sezione tendenza nello stesso momento
  - **QUANDO** il sistema mostra i contenuti di tendenza
  - **ALLORA** il sistema mostra a entrambi gli stessi contenuti, a differenza del feed

- Scenario 4: Profili privati e contenuti rimossi
  - **DATO** che un contenuto appartiene a un profilo privato oppure è stato rimosso dai moderatori
  - **QUANDO** l'utente apre la sezione tendenza
  - **ALLORA** il sistema non mostra quel contenuto

- Scenario 5: Nessun contenuto di tendenza
  - **DATO** che non ci sono contenuti con interazioni nel periodo
  - **QUANDO** l'utente apre la sezione tendenza
  - **ALLORA** il sistema mostra un messaggio che non ci sono contenuti

---

TITOLO: Impostazione: utilizzo del tempo

USER STORY:
**Come** Utente registrato,
**Voglio** visualizzare e limitare il tempo di utilizzo dell'app,
**In modo da** usare wuxer in modo consapevole.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Visualizzazione del tempo
  - **DATO** che l'utente ha effettuato l'accesso
  - **QUANDO** l'utente apre la sezione utilizzo del tempo
  - **ALLORA** il sistema mostra il tempo trascorso sull'app in modo giornaliero, settimanale e mensile, sommando tutti i dispositivi dell'account

- Scenario 2: Limite predefinito
  - **DATO** che l'utente non ha impostato alcun limite
  - **QUANDO** l'utente usa l'app
  - **ALLORA** il sistema applica il limite giornaliero predefinito di 2 ore

- Scenario 3: Modifica del limite
  - **DATO** che l'utente apre la sezione utilizzo del tempo
  - **QUANDO** l'utente cambia il limite giornaliero e salva
  - **ALLORA** il sistema applica il nuovo limite

- Scenario 4: Avvisi al raggiungimento del limite
  - **DATO** che l'utente sta raggiungendo o ha raggiunto il limite giornaliero
  - **QUANDO** il limite viene raggiunto
  - **ALLORA** il sistema avvisa l'utente due volte, all'80% e al 100% del limite

- Scenario 5: Blocco dell'app
  - **DATO** che l'utente ha ricevuto tutti gli avvisi previsti
  - **QUANDO** l'utente continua a usare l'app
  - **ALLORA** il sistema blocca l'uso dell'app

- Scenario 6: Tempo aggiuntivo
  - **DATO** che l'app è bloccata per il limite raggiunto
  - **QUANDO** l'utente richiede un tempo aggiuntivo
  - **ALLORA** il sistema concede 15 minuti in più, richiedibili senza limite di volte, e poi blocca di nuovo l'app

- Scenario 7: Uscita dall'app
  - **DATO** che l'app è bloccata per il limite raggiunto
  - **QUANDO** l'utente esce dall'app
  - **ALLORA** il sistema permette di riutilizzarla il giorno dopo

---

TITOLO: Chat di gruppo

USER STORY:
**Come** Utente registrato,
**Voglio** creare chat di gruppo e gestirne i partecipanti,
**In modo da** parlare con più persone insieme.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Creazione del gruppo
  - **DATO** che l'utente ha effettuato l'accesso
  - **QUANDO** l'utente crea un gruppo e aggiunge dei partecipanti
  - **ALLORA** il sistema crea la chat e ne rende il creatore amministratore capo

- Scenario 2: Aggiunta di un partecipante
  - **DATO** che l'utente è amministratore del gruppo
  - **QUANDO** l'utente aggiunge un partecipante
  - **ALLORA** il sistema lo inserisce nel gruppo e gli mostra anche i messaggi precedenti

- Scenario 3: Limite di partecipanti
  - **DATO** che il gruppo ha 50 partecipanti
  - **QUANDO** un amministratore tenta di aggiungerne un altro
  - **ALLORA** il sistema impedisce l'aggiunta e mostra un avviso sul limite

- Scenario 4: Aggiunta senza permessi
  - **DATO** che l'utente non è amministratore
  - **QUANDO** l'utente tenta di aggiungere o rimuovere un partecipante
  - **ALLORA** il sistema nega l'azione

- Scenario 5: Nomina di un amministratore
  - **DATO** che l'utente è amministratore capo del gruppo
  - **QUANDO** l'utente nomina un altro partecipante amministratore
  - **ALLORA** il sistema gli assegna il ruolo, mentre l'utente resta amministratore capo

- Scenario 6: Ruolo di amministratore capo
  - **DATO** che l'utente è amministratore capo
  - **QUANDO** l'utente tenta di cedere il ruolo di amministratore capo
  - **ALLORA** il sistema non permette il passaggio del ruolo

- Scenario 7: Uscita dal gruppo
  - **DATO** che l'utente è partecipante del gruppo
  - **QUANDO** l'utente esce dal gruppo
  - **ALLORA** il sistema non gli mostra più la chat, mentre i suoi messaggi restano visibili agli altri partecipanti

- Scenario 8: Uscita dell'amministratore capo
  - **DATO** che l'utente è amministratore capo e nel gruppo ci sono altri partecipanti
  - **QUANDO** l'utente tenta di uscire dal gruppo
  - **ALLORA** il sistema non glielo permette, perché può uscire solo se è l'unico nel gruppo

- Scenario 9: Eliminazione di un messaggio
  - **DATO** che l'utente ha inviato un messaggio nel gruppo
  - **QUANDO** l'utente elimina quel messaggio
  - **ALLORA** il sistema lo rimuove dalla chat, con la stessa regola delle chat private; al suo posto appare "Messaggio eliminato"

- Scenario 10: Gruppo senza partecipanti
  - **DATO** che nel gruppo non è rimasto nessun partecipante
  - **QUANDO** l'ultimo partecipante esce
  - **ALLORA** il sistema fa sparire il gruppo e conserva i dati per 180 giorni, poi li elimina

- Scenario 11: Messaggio nel gruppo
  - **DATO** che l'utente è partecipante del gruppo
  - **QUANDO** l'utente invia un messaggio
  - **ALLORA** il sistema lo consegna a tutti i partecipanti in meno di 1 secondo, senza cifratura end-to-end

---

TITOLO: Pubblicazione video

USER STORY:
**Come** Utente registrato,
**Voglio** pubblicare un video con descrizione e hashtag,
**In modo da** condividere contenuti in movimento.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Video pubblicato
  - **DATO** che l'utente ha effettuato l'accesso
  - **QUANDO** l'utente carica un video di durata fino a 60 secondi, scrive la descrizione con eventuali hashtag e pubblica
  - **ALLORA** il sistema pubblica il video sul profilo

- Scenario 2: Video troppo lungo
  - **DATO** che l'utente sta caricando un video
  - **QUANDO** il video dura più di 60 secondi
  - **ALLORA** il sistema rifiuta il caricamento e indica la durata massima

- Scenario 3: Video non valido
  - **DATO** che l'utente sta caricando un video
  - **QUANDO** il file non è in formato MP4 o MOV oppure supera i 200 MB
  - **ALLORA** il sistema rifiuta il file e indica i formati e le dimensioni ammessi

- Scenario 4: Copertina scelta dall'utente
  - **DATO** che l'utente sta pubblicando un video
  - **QUANDO** l'utente imposta una copertina
  - **ALLORA** il sistema usa la copertina scelta

- Scenario 5: Copertina automatica
  - **DATO** che l'utente non ha impostato una copertina
  - **QUANDO** l'utente pubblica il video
  - **ALLORA** il sistema ne sceglie una automaticamente

- Scenario 6: Visibilità del video
  - **DATO** che l'utente ha pubblicato un video
  - **QUANDO** altri utenti cercano di vederlo
  - **ALLORA** il sistema lo mostra a tutti se il profilo è pubblico e solo ai follower se è privato

- Scenario 7: Gestione del video pubblicato
  - **DATO** che l'utente ha pubblicato un video
  - **QUANDO** l'utente modifica la descrizione, lo elimina o lo archivia
  - **ALLORA** il sistema applica la modifica, e un video archiviato non è più visibile agli altri utenti

- Scenario 8: Nessun download
  - **DATO** che un utente guarda il video di un altro utente
  - **QUANDO** l'utente cerca di scaricarlo
  - **ALLORA** il sistema non offre lo scaricamento

---

TITOLO: Interazioni video

USER STORY:
**Come** Utente registrato,
**Voglio** mettere like, commentare e condividere i video,
**In modo da** interagire con i creator.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Like a un video
  - **DATO** che l'utente guarda un video
  - **QUANDO** l'utente mette like
  - **ALLORA** il sistema registra il like e il numero di like è visibile a tutti

- Scenario 2: Rimozione del like
  - **DATO** che l'utente ha già messo like a un video
  - **QUANDO** l'utente preme di nuovo il like
  - **ALLORA** il sistema rimuove il like senza registrarne un secondo

- Scenario 3: Commento a un video
  - **DATO** che l'utente guarda un video con i commenti attivi
  - **QUANDO** l'utente scrive un commento fino a 800 caratteri e lo invia
  - **ALLORA** il sistema pubblica il commento e lo rende visibile a tutti

- Scenario 4: Risposta e like a un commento
  - **DATO** che un video ha dei commenti
  - **QUANDO** l'utente risponde a un commento oppure mette like a un commento
  - **ALLORA** il sistema pubblica la risposta sotto quel commento oppure registra il like al commento

- Scenario 5: Eliminazione di un commento
  - **DATO** che un video ha dei commenti
  - **QUANDO** l'autore del commento elimina il proprio commento oppure l'autore del video elimina un commento ricevuto
  - **ALLORA** il sistema rimuove il commento; se il commento ha risposte, al suo posto appare "Contenuto eliminato"

- Scenario 6: Commenti disattivati
  - **DATO** che l'autore ha disattivato i commenti del video
  - **QUANDO** un utente guarda il video
  - **ALLORA** il sistema non permette di commentare

- Scenario 7: Visualizzazioni
  - **DATO** che un utente guarda un video
  - **QUANDO** la visualizzazione viene registrata
  - **ALLORA** il sistema aggiorna il conteggio delle visualizzazioni, visibile a tutti

- Scenario 8: Condivisione del video
  - **DATO** che l'utente guarda un video che può essere condiviso
  - **QUANDO** l'utente sceglie di condividerlo
  - **ALLORA** il sistema permette di copiare il link del video o di inviarlo in una chat; il link si apre solo agli utenti con un account e, se il profilo è privato, solo ai follower

- Scenario 9: Commento vuoto
  - **DATO** che l'utente sta scrivendo un commento
  - **QUANDO** l'utente invia un commento senza testo
  - **ALLORA** il sistema impedisce l'invio e mostra un avviso

- Scenario 10: Commento troppo lungo
  - **DATO** che l'utente sta scrivendo un commento
  - **QUANDO** il testo supera gli 800 caratteri
  - **ALLORA** il sistema non lo pubblica e mostra un avviso sul limite

---

TITOLO: Abbonamenti creators

USER STORY:
**Come** Creator,
**Voglio** sottoscrivere un abbonamento a wuxer,
**In modo da** ottenere vantaggi dedicati.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Sottoscrizione di un abbonamento
  - **DATO** che l'utente ha effettuato l'accesso
  - **QUANDO** l'utente sceglie un piano (wuxer pro o wuxer max, mensile o annuale) e completa il pagamento tramite il provider di pagamento
  - **ALLORA** il sistema attiva l'abbonamento e rende fruibili i vantaggi del piano

- Scenario 2: Pagamento non riuscito
  - **DATO** che l'utente sta sottoscrivendo un abbonamento
  - **QUANDO** il pagamento fallisce
  - **ALLORA** il sistema non attiva l'abbonamento e mostra l'errore

- Scenario 3: Rinnovo automatico
  - **DATO** che l'utente ha un abbonamento attivo
  - **QUANDO** l'abbonamento arriva a scadenza
  - **ALLORA** il sistema lo rinnova automaticamente e addebita il pagamento

- Scenario 4: Disdetta
  - **DATO** che l'utente ha un abbonamento attivo
  - **QUANDO** l'utente disdice l'abbonamento
  - **ALLORA** il sistema mantiene i vantaggi fino alla scadenza e poi non rinnova

- Scenario 5: Scadenza dell'abbonamento
  - **DATO** che l'abbonamento dell'utente è scaduto
  - **QUANDO** l'utente cerca di usare un vantaggio
  - **ALLORA** il sistema non lo rende più fruibile

- Scenario 6: Pagamento del rinnovo non riuscito
  - **DATO** che il pagamento del rinnovo è fallito
  - **QUANDO** il sistema rileva il mancato pagamento
  - **ALLORA** il sistema avvisa l'utente e gli lascia 48 ore per pagare

- Scenario 7: Mancato pagamento entro 48 ore
  - **DATO** che l'utente ha ricevuto l'avviso di mancato pagamento
  - **QUANDO** passano 48 ore senza che l'utente paghi
  - **ALLORA** il sistema fa decadere l'abbonamento e l'utente perde i vantaggi

- Scenario 8: Cambio di piano
  - **DATO** che l'utente ha un abbonamento attivo
  - **QUANDO** l'utente passa a un piano superiore
  - **ALLORA** il sistema attiva subito il nuovo piano e addebita solo la differenza di prezzo, ad esempio 20 € per passare da wuxer pro (4,99 €) a wuxer max (24,99 €)

- Scenario 9: Nessun rimborso
  - **DATO** che il rinnovo dell'abbonamento è già stato addebitato
  - **QUANDO** l'utente chiede un rimborso
  - **ALLORA** il sistema non rimborsa il rinnovo già addebitato

---

TITOLO: Impostazione: configurazione AI

USER STORY:
**Come** Utente registrato,
**Voglio** attivare, disattivare e configurare le funzionalità AI una per una,
**In modo da** decidere se e come usarle.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Funzionalità AI disattivate di default
  - **DATO** che l'utente ha appena creato l'account
  - **QUANDO** l'utente apre le impostazioni AI
  - **ALLORA** il sistema mostra tutte le funzionalità AI disattivate

- Scenario 2: Attivazione di una funzionalità
  - **DATO** che una funzionalità AI è disattivata
  - **QUANDO** l'utente la attiva e salva
  - **ALLORA** il sistema rende disponibile solo quella funzionalità

- Scenario 3: Disattivazione di una funzionalità
  - **DATO** che una funzionalità AI è attiva
  - **QUANDO** l'utente la disattiva
  - **ALLORA** il sistema non mostra più i suggerimenti di quella funzionalità e lascia attive le altre

- Scenario 4: Disponibilità per tutti
  - **DATO** che l'utente non ha alcun abbonamento
  - **QUANDO** l'utente apre le impostazioni AI
  - **ALLORA** il sistema gli permette di configurare le funzionalità AI come a tutti gli altri

- Scenario 5: Stile dei suggerimenti non configurabile
  - **DATO** che i suggerimenti si basano sul contenuto
  - **QUANDO** l'utente apre le impostazioni AI
  - **ALLORA** il sistema non offre opzioni di tono o stile

---

TITOLO: Generazione suggerimenti AI nei post e nei video

USER STORY:
**Come** Utente registrato,
**Voglio** ricevere suggerimenti AI per descrizione e hashtag mentre creo un post o un video,
**In modo da** creare contenuti migliori più rapidamente.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Richiesta di un suggerimento
  - **DATO** che l'utente ha attivato la funzionalità AI e sta creando un post o un video
  - **QUANDO** l'utente richiede un suggerimento
  - **ALLORA** il sistema propone una descrizione e degli hashtag basati sul contenuto e su ciò che l'utente ha già scritto nella descrizione

- Scenario 2: Suggerimento accettato
  - **DATO** che il sistema ha proposto un suggerimento
  - **QUANDO** l'utente lo accetta
  - **ALLORA** il sistema sostituisce il testo esistente con il suggerimento

- Scenario 3: Suggerimento rifiutato
  - **DATO** che il sistema ha proposto un suggerimento
  - **QUANDO** l'utente lo ignora
  - **ALLORA** il sistema lascia il testo invariato

- Scenario 4: Rigenerazione del suggerimento
  - **DATO** che il sistema ha proposto un suggerimento
  - **QUANDO** l'utente chiede di rigenerarlo
  - **ALLORA** il sistema propone un nuovo suggerimento, uno alla volta

- Scenario 5: Funzionalità AI disattivata
  - **DATO** che l'utente ha disattivato la funzionalità AI
  - **QUANDO** l'utente crea un post o un video
  - **ALLORA** il sistema non offre alcun suggerimento

- Scenario 6: Servizio non disponibile
  - **DATO** che l'utente richiede un suggerimento
  - **QUANDO** il servizio AI non risponde
  - **ALLORA** il sistema mostra un avviso che il servizio non è al momento disponibile e permette di continuare senza suggerimenti

- Scenario 7: Contenuto generato da AI
  - **DATO** che l'utente pubblica un contenuto generato da AI o che contiene contenuti AI
  - **QUANDO** l'utente attiva l'opzione apposita
  - **ALLORA** il sistema indica il contenuto come generato da AI

- Scenario 8: Nessun dato conservato
  - **DATO** che l'utente ha richiesto dei suggerimenti
  - **QUANDO** la richiesta è conclusa
  - **ALLORA** il sistema non salva i contenuti elaborati dall'AI

---

TITOLO: Rilevamento automatico dei contenuti AI

USER STORY:
**Come** Utente registrato,
**Voglio** che il sistema rilevi se un contenuto pubblicato è stato generato da AI,
**In modo da** sapere se ciò che guardo è reale o generato.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Contenuto non rilevato come AI
  - **DATO** che l'utente pubblica una storia, un post o un video
  - **QUANDO** il sistema non rileva alcun segno di generazione da AI
  - **ALLORA** il sistema lo pubblica senza alcuna indicazione

- Scenario 2: Dichiarazione dell'autore
  - **DATO** che l'autore ha dichiarato il contenuto come generato da AI
  - **QUANDO** il sistema pubblica il contenuto
  - **ALLORA** il sistema lo indica come generato da AI anche se il rilevamento non lo ha riconosciuto

- Scenario 3: Rilevamento non disponibile
  - **DATO** che il servizio di rilevamento non risponde
  - **QUANDO** l'utente pubblica un contenuto
  - **ALLORA** il sistema pubblica il contenuto e ripete il rilevamento appena possibile

- Scenario 4: Contenuto AI non dichiarato
  - **DATO** che l'autore non ha spuntato l'opzione che indica un contenuto generato da AI o che contiene contenuti AI
  - **QUANDO** il sistema rileva che il contenuto è stato generato da AI o contiene contenuti AI
  - **ALLORA** il sistema lo indica come generato da AI, avvisa l'autore, registra uno strike a suo carico e applica le sanzioni previste

- Scenario 5: Contestazione del rilevamento
  - **DATO** che il sistema ha indicato un contenuto come generato da AI
  - **QUANDO** l'autore ritiene che il rilevamento sia sbagliato e lo contesta
  - **ALLORA** il sistema registra la contestazione e la sottopone a un moderatore con la stessa procedura delle contestazioni sulle rimozioni

- Scenario 6: Contestazione accolta
  - **DATO** che il moderatore accoglie la contestazione dell'autore
  - **QUANDO** la decisione viene registrata
  - **ALLORA** il sistema toglie l'etichetta di contenuto generato da AI e annulla lo strike

---

TITOLO: Categorie di utenti per le storie

USER STORY:
**Come** Utente registrato,
**Voglio** scegliere quali categorie di utenti possono vedere una mia storia,
**In modo da** controllare chi vede ciò che pubblico.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Scelta della categoria
  - **DATO** che l'utente sta pubblicando una storia
  - **QUANDO** l'utente sceglie una categoria di utenti (tutti, follower o amici stretti) e pubblica
  - **ALLORA** il sistema mostra la storia solo a quella categoria

- Scenario 2: Utente fuori dalla categoria
  - **DATO** che una storia è visibile solo a una categoria di utenti
  - **QUANDO** un utente non appartenente alla categoria cerca di vederla
  - **ALLORA** il sistema non gliela mostra

- Scenario 3: Categoria predefinita
  - **DATO** che l'utente non sceglie alcuna categoria
  - **QUANDO** l'utente pubblica la storia
  - **ALLORA** il sistema applica la visibilità del profilo, pubblico o privato

- Scenario 4: Creazione della lista degli amici stretti
  - **DATO** che l'utente ha dei follower
  - **QUANDO** l'utente aggiunge o toglie dei follower dalla lista degli amici stretti
  - **ALLORA** il sistema aggiorna la lista e la usa per le storie riservate agli amici stretti

- Scenario 5: Indicatore degli amici stretti
  - **DATO** che una storia è riservata agli amici stretti
  - **QUANDO** un amico stretto la guarda
  - **ALLORA** il sistema mostra un indicatore sulla storia, che nessun altro utente vede

- Scenario 6: Profilo privato
  - **DATO** che il profilo dell'utente è privato
  - **QUANDO** l'utente sceglie la categoria della storia
  - **ALLORA** il sistema offre solo le categorie follower e amici stretti

---

TITOLO: Video nelle storie

USER STORY:
**Come** Utente registrato,
**Voglio** pubblicare una storia con un video,
**In modo da** condividere momenti temporanei in movimento.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Storia con video
  - **DATO** che l'utente ha effettuato l'accesso
  - **QUANDO** l'utente carica un video fino a 15 secondi, in formato MP4 o MOV e fino a 100 MB, e pubblica la storia
  - **ALLORA** il sistema pubblica la storia con il video

- Scenario 2: Scadenza della storia video
  - **DATO** che esiste una storia con video
  - **QUANDO** passano 24 ore dalla pubblicazione
  - **ALLORA** il sistema la fa sparire come le altre storie; l'autore può anche archiviarla, come le altre storie

- Scenario 3: Video non valido
  - **DATO** che l'utente sta caricando un video per una storia
  - **QUANDO** il video dura più di 15 secondi, non è in formato MP4 o MOV oppure supera i 100 MB
  - **ALLORA** il sistema rifiuta il caricamento e indica i limiti

---

TITOLO: Impostazione: chi può commentare le storie

USER STORY:
**Come** Utente registrato,
**Voglio** scegliere chi può commentare le mie storie,
**In modo da** evitare commenti indesiderati.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Scelta di chi può commentare
  - **DATO** che l'utente apre le impostazioni delle storie
  - **QUANDO** l'utente sceglie chi può commentare (tutti, solo i follower o nessuno) e salva
  - **ALLORA** il sistema applica la scelta alle sue storie

- Scenario 2: Commento non consentito
  - **DATO** che l'autore ha limitato i commenti a una categoria
  - **QUANDO** un utente non autorizzato cerca di commentare la storia
  - **ALLORA** il sistema non permette di commentare

- Scenario 3: Impostazione predefinita
  - **DATO** che l'utente non ha cambiato l'impostazione
  - **QUANDO** un utente vede una sua storia
  - **ALLORA** il sistema permette di commentare a tutti quelli che la vedono

---

TITOLO: Allegati nelle chat private

USER STORY:
**Come** Utente registrato,
**Voglio** inviare immagini nelle chat private,
**In modo da** comunicare con gli altri utenti in modo più completo.

CRITERI DI ACCETTAZIONE:
- Scenario 1: Invio di un allegato
  - **DATO** che l'utente è in una chat privata
  - **QUANDO** l'utente invia un'immagine
  - **ALLORA** il sistema lo cifra end-to-end e lo consegna al destinatario

- Scenario 2: Allegato non valido
  - **DATO** che l'utente sta inviando un allegato
  - **QUANDO** il file non è un'immagine oppure supera i 10 MB
  - **ALLORA** il sistema non lo invia e indica i limiti

- Scenario 3: Eliminazione di un allegato
  - **DATO** che l'utente ha inviato un allegato
  - **QUANDO** l'utente lo elimina
  - **ALLORA** il sistema lo rimuove dalla chat di entrambi; al suo posto appare "Messaggio eliminato"

- Scenario 4: Segnalazione di un allegato
  - **DATO** che l'utente ha ricevuto un allegato inappropriato
  - **QUANDO** l'utente lo segnala
  - **ALLORA** il sistema invia ai moderatori solo l'allegato segnalato, senza compromettere il resto della chat
