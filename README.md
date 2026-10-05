# WUXER

## Requisiti

### Requisiti funzionali

| Requisito | Fonte | Funzionalità collegata |
| :---: | :---: | :---: |
| Il sistema deve permettere all'utente di registrarsi e accedere con credenziali/OAuth | Utenti | Registrazione/login |
| Il sistema deve permettere all'utente di modificare le informazioni del profilo | Utenti | Profilo |
| Il sistema deve permettere all'utente di pubblicare una storia con immagini e testi | Utenti | Pubblicazione storie |
| Il sistema deve permettere all'utente di pubblicare un post con immagini e descrizione | Utenti | Pubblicazione post |
| Il sistema deve permettere all'utente di seguire e di smettere di seguire altri profili | Utenti | Follow |
| Il sistema deve permettere all'utente di mettere like e commentare le storie | Utenti | Interazioni storie |
| Il sistema deve permettere all'utente di mettere like e commentare i post | Utenti | Interazioni post |
| Il sistema deve mostrare all'utente un feed con i contenuti degli altri profili in base alle proprie interazioni | Utenti | Feed |
| Il sistema deve permettere all'utente di segnalare un contenuto inclusi i messaggi privati indicando un motivo | Utenti | Segnalazione dei contenuti |
| Il sistema deve permettere ai moderatori di esaminare le segnalazioni e di rimuovere i contenuti | Moderatori | Moderazione dei contenuti |
| Il sistema deve permettere all'utente di modificare email e password, di disattivare o eliminare il proprio account | Utenti | Impostazione: account |
| Il sistema deve rendere consultabili termini di servizio e informativa sulla privacy e richiedere l'accettazione alla registrazione | Utenti | Impostazione: parte legale |
| Il sistema deve permettere all'utente di inserire hashtag ai post e di visualizzare i post con quell'hashtag | Utenti | Hashtag post |
| Il sistema deve permettere all'utente di cercare altri profili per nome utente | Utenti | Ricerca account |
| Il sistema deve permettere all'utente di cercare i post tramite parole, hashtag e ricerca avanzata (data, keyword) | Utenti | Ricerca post |
| Il sistema deve permettere all'utente di impostare le proprie preferenze (es. lingua, tema, notifiche) | Utenti | Impostazione: preferenze |
| Il sistema deve mostrare all'utente le informazioni sull'app e sul proprio account (es. versione, data di registrazione) | Utenti | Impostazione: informazioni app e account |
| Il sistema deve notificare l'utente di nuovi followers, like, commenti e messaggi | Utenti | Notifiche |
| Il sistema deve permettere a due utenti di scambiarsi messaggi privati | Utenti | Chat private |
| Il sistema deve permettere all'utente di creare chat di gruppo e di gestirne i partecipanti | Utenti | Chat di gruppo |
| Il sistema deve mostrare all'utente i contenuti di tendenza in base alle interazioni | Utenti | Visualizzazione tendenza |
| Il sistema deve permettere all'utente di visualizzare e limitare il tempo di utilizzo dell'app | Utenti | Impostazione: utilizzo del tempo |
| Il sistema deve permettere all'utente di pubblicare un video con titolo e descrizione | Utenti | Pubblicazione video |
| Il sistema deve permettere all'utente di mettere like e commentare i video | Utenti | Interazioni video |
| Il sistema deve permettere a un creator di sottoscrivere a un abbonamento per ottenere vantaggi | Creators | Abbonamenti creators |
| Il sistema deve permettere all'utente di attivare, disattivare e configurare le funzionalità AI | Utenti | Impostazione: configurazione AI |
| Il sistema deve proporre all'utente suggerimenti generati da AI (es. descrizioni, hashtag) nella creazione di post e video | Utenti | Generazione suggerimenti AI nei post e nei video |

---

### Requisiti non funzionali

| Requisito | Categoria | Funzionalità collegata |
| :---: | :---: | :---: |
| Le credenziali devono essere salvate con hash | Sicurezza | Registrazione/login |
| Le password devono rispettare requisiti minimi di complessità e l'accesso deve essere limitato dopo ripetuti tentativi falliti | Sicurezza | Registrazione/login |
| Tutte le comunicazioni tra client e server devono avvenire tramite HTTPS | Sicurezza | Tutte |
| I dati personali devono essere trattati in conformità al GDPR (consenso, esportazione e cancellazione dei dati) | Privacy | Impostazione: account |
| Il feed e le principali pagine devono caricarsi entro 1 secondo in condizioni di rete normali | Prestazioni | Feed |
| Il sistema deve supportare la crescita del numero di utenti senza degradare le prestazioni | Scalabilità | Tutte |
| Il sistema deve garantire una disponibilità di almeno il 97% su base mensile | Affidabilità | Tutte |
| L'interfaccia deve essere utilizzabile da dispositivi mobili e desktop e rispettare le linee guida di accessibilità WCAG 2.1 AA | Usabilità | Tutte |
| I messaggi delle chat devono essere consegnati in tempo reale (< 1s) | Prestazioni | Chat private e di gruppo |
| Le chat private devono essere crittografate end-to-end | Sicurezza | Chat private |
| Le segnalazioni devono essere prese in carico dai moderatori entro 12 ore | Qualità del servizio | Moderazione dei contenuti |

---

### Requisiti di dominio

| Requisito | Origine | Funzionalità collegata |
| :---: | :---: | :---: |
| Le storie devono scadere e sparire automaticamente dopo 24 ore | Convenzione social network | Pubblicazione storie |
| Per registrarsi l'utente deve avere almeno 13 anni (età minima del consenso digitale) | Normativa | Registrazione/login |
| Il nome utente deve essere univoco | Convenzione social network | Profilo |
| Un utente non può seguire se stesso | Convenzione social network | Follow |
| Un profilo bloccato o sospeso non può accedere all'applicazione | Politica di moderazione | - |
| Un contenuto segnalato può essere rimosso solo da un moderatore | Politica di moderazione | Moderazione dei contenuti |
| Un utente può mettere un solo like per contenuto | Convenzione social network | Interazioni storie, post e video |
| I contenuti generati da AI devono essere chiaramente identificabili come tali | Normativa | Pubblicazione storie, post e video |
| I vantaggi di un abbonamento sono fruibili dagli abbonati attivi | Regola di business | Abbonamenti creators |

## Analisi SWOT

|  | Positivo | Negativo |
| :---: | :---: | :---: |
| Interni | [**Punti di forza**](./docs/swot/STRENGTHS.md) | [**Punti di debolezza**](./docs/swot/WEAKNESSES.md) |
| Esterni | [**Opportunità**](./docs/swot/OPPORTUNITIES.md) | [**Minacce**](./docs/swot/THREATS.md) |

## Piano di sviluppo

### CRITERI

- **Priorità di esecuzione**: funzionalità suddivise in fasi
- **Dipendenze**: da cosa dipende una funzionalità
- **Complessità**: quanto è complesso e oneroso lo sviluppo della funzionalità
- **Rischio**: livello di rischio (legale, di sicurezza e di privacy) se una funzionalità manca o è gestita male

> **Stato di avanzamento di una funzionalità**
> | Stato | Descrizione |
> | :---: | :---: |
> | ✅ | Completato |
> | 🔄 | In corso |
> | ⬜ | Da fare |
> | ⚠️ | Da rivedere |

---

### Fase 1 - Funzionalità essenziali

| Funzionalità | Dipendenze | Complessità | Rischio | Stato avanzamento |
| :---: | :---: | :---: | :---: | :---: |
| Registrazione/login | - | Media | Alto | ⬜ |
| Profilo | Registrazione/login | Bassa | Basso | ⬜ |
| Pubblicazione storie | Profilo | Media | Basso | ⬜ |
| Pubblicazione post | Profilo | Media | Basso | ⬜ |
| Follow | Profilo | Bassa | Basso | ⬜ |
| Interazioni storie | Pubblicazione storie | Bassa | Medio | ⬜ |
| Interazioni post | Pubblicazione post | Bassa | Medio | ⬜ |
| Feed | Pubblicazione post | Alta | Medio | ⬜ |
| Segnalazione dei contenuti | Pubblicazione post | Bassa | Alto | ⬜ |
| Moderazione dei contenuti | Segnalazione dei contenuti | Alta | Alto | ⬜ |
| Impostazione: account | Registrazione/login | Bassa | Medio | ⬜ |
| Impostazione: parte legale | Registrazione/login | Bassa | Alto | ⬜ |

---

### Fase 2 - Engagement

| Funzionalità | Dipendenze | Complessità | Rischio | Stato avanzamento |
| :---: | :---: | :---: | :---: | :---: |
| Hashtag post | Pubblicazione post | Bassa | Basso | ⬜ |
| Ricerca account | Profilo | Media | Basso | ⬜ |
| Ricerca post | Hashtag post | Media | Basso | ⬜ |
| Impostazione: preferenze | Registrazione/login | Bassa | Basso | ⬜ |
| Impostazione: informazioni app e account | Registrazione/login | Bassa | Basso | ⬜ |
| Notifiche | Registrazione/login | Media | Basso | ⬜ |
| Chat private | Profilo, Follow | Alta | Alto | ⬜ |

---

### Fase 3 - Funzionalità avanzate

| Funzionalità | Dipendenze | Complessità | Rischio | Stato avanzamento |
| :---: | :---: | :---: | :---: | :---: |
| Visualizzazione tendenza | Interazioni post/video | Alta | Basso | ⬜ |
| Impostazione: utilizzo del tempo | Registrazione/login | Alta | Basso | ⬜ |
| Chat di gruppo | Chat private | Alta | Alto | ⬜ |
| Pubblicazione video | Profilo | Alta | Medio | ⬜ |
| Interazioni video | Pubblicazione video | Bassa | Medio | ⬜ |

---

### Fase 4 - Monetizzazione e funzionalità AI

| Funzionalità | Dipendenze | Complessità | Rischio | Stato avanzamento |
| :---: | :---: | :---: | :---: | :---: |
| Abbonamenti creators | Profilo | Alta | Alto | ⬜ |
| Impostazione: configurazione AI | Impostazione: preferenze | Media | Medio | ⬜ |
| Generazione suggerimenti AI nei post e nei video | Pubblicazione post/video | Alta | Alto | ⬜ |
