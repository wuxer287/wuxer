# WUXER

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
| Feed | Pubblicazione post/video | Alta | Media | ⬜ |
| Segnalazione dei contenuti | Pubblicazione post/video | Bassa | Alto | ⬜ |
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
| Notifiche | - | Media | Basso | ⬜ |
| Chat privati | Profilo, Follow | Alta | Alto | ⬜ |

---

### Fase 3 - Funzionalità avanzate

| Funzionalità | Dipendenze | Complessità | Rischio | Stato avanzamento |
| :---: | :---: | :---: | :---: | :---: |
| Visualizzazione tendenza | Interazioni post/video | Alta | Basso | ⬜ |
| Impostazione: utilizzo del tempo | - | Alta | Basso | ⬜ |
| Chat di gruppo | Chat privati | Alta | Alto | ⬜ |
| Pubblicazione video | Profilo | Alta | Medio | ⬜ |
| Interazioni video | Pubblicazione video | Bassa | Medio | ⬜ |

---

### Fase 4 - Monetizzazione e funzionalità AI

| Funzionalità | Dipendenze | Complessità | Rischio | Stato avanzamento |
| :---: | :---: | :---: | :---: | :---: |
| Abbonamenti creators | Profilo | Alta | Alto | ⬜ |
| Impostazioni: configurazione AI | Preferenze | Media | Medio | ⬜ |
| Generazione suggerimenti AI nei post e nei video | Pubblicazione post/video | Alta | Alto | ⬜ |
