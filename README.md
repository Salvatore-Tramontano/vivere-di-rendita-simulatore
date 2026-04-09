# Vivere di Rendita — Il Simulatore

Strumento di simulazione per pianificare la gestione di un capitale nel tempo, con calcolo fiscale italiano (ETF ad accumulazione, imposta di bollo e tassazione sulle plusvalenze).

> **Nota sul file:** il simulatore si chiama `Simulatori_9.html` perché è la nona versione di sviluppo. Puoi rinominarlo come preferisci senza perdere nulla.

---

## Cos'è

Un singolo file HTML: scarichi, apri nel browser, usi. Nessun account, nessun server, nessun dato inviato a nessuno — tutto gira localmente sul tuo dispositivo.

Il simulatore ha due modalità di calcolo indipendenti:

- **Reverse** (tema blu) — sai *quanto vuoi ricevere ogni mese* e vuoi scoprire *quanto capitale devi accumulare*
- **Direct** (tema verde) — hai *già un capitale* e vuoi sapere *quanto puoi prelevare ogni mese*

Puoi passare da una all'altra con i pulsanti in alto.

---

## Come aprirlo

1. Scarica il file `Simulatori_9.html`
2. Aprilo trascinandolo nel browser, oppure fai doppio clic

Nessuna installazione richiesta.

> **Connessione internet:** al primo avvio il simulatore scarica font, icone e la libreria per i grafici da internet (CDN). Se sei offline, alcune parti visive potrebbero non caricarsi correttamente. I calcoli rimangono comunque funzionanti.

---

## Dashboard Reverse — "Quanto capitale mi serve?"

Usa questa modalità quando sai già *quante risorse mensili ti bastano* e vuoi calcolare l'obiettivo di accumulo.

### Parametri da inserire

| Campo | Cosa inserire |
|---|---|
| **Il tuo bonifico mensile** | La quota che vuoi ricevere tu personalmente ogni mese, al netto di tasse e inflazione |
| **Anni di autonomia** | Per quanti anni il capitale deve durare (es. 30 anni) |
| **Rendimento annuo lordo** | La stima di rendimento del portafoglio prima delle tasse (es. 4% per un ETF azionario prudente) |
| **Inflazione media** | L'aumento atteso del costo della vita (es. 2%). Influisce solo se attivi la rata crescente |
| **Tassazione ETF** | L'aliquota sulle plusvalenze (26% per ETF azionari in Italia) |

#### Opzione: Proteggi dall'inflazione (toggle)

Quando attivo, il tuo prelievo mensile aumenta automaticamente ogni anno in linea con l'inflazione inserita. Così il tuo **potere d'acquisto reale rimane costante** nel tempo anche se i prezzi salgono.

**Attenzione:** attivando questa opzione il capitale richiesto aumenta significativamente, e la curva del grafico assumerà una forma a campana — il capitale sale nei primi anni (quando i prelievi sono ancora piccoli) e scende nella seconda metà. Questo è il comportamento corretto, non un errore.

#### Opzione: Giorno Zero — uscite immediate

Se nel momento in cui investi vuoi subito destinare una parte del capitale a donazioni, beneficenza o regali una tantum, inseriscili qui. Questi importi vengono sottratti prima ancora che il contatore degli anni parta.

#### Opzione: Gruppi aggiuntivi (Gruppo 1 / Gruppo 2)

Se il tuo prelievo mensile comprende anche persone a carico (figli, genitori, partner), puoi configurare fino a due gruppi aggiuntivi specificando il numero di persone e la quota mensile per ciascuna. Il simulatore calcola il capitale necessario per sostenere tutti.

### Cosa leggi nei risultati

| Voce | Significato |
|---|---|
| **Capitale da investire** | L'importo totale da mettere nel conto il Giorno Zero perché tutto funzioni |
| **Capitale investito** | Come sopra, al netto delle uscite immediate del Giorno Zero |
| **Uscite Giorno Zero** | Beneficenza + regali sottratti subito |
| **Primo Prelievo (Mese 1)** | Bonifico totale del primo mese (tuo + gruppi). Se hai attivato la rata crescente, questo è il punto di partenza |
| **Oneri Fiscali Totali** | Tutto quello che pagherai al fisco nei decenni della simulazione (bollo + tasse sui guadagni) |

### Il grafico

Mostra come il capitale decresce anno per anno. Passa il cursore su un punto per vedere:
- Quanto capitale rimane nel conto quell'anno
- L'importo esatto del bonifico mensile (con spaccato per beneficiario e percentuali)
- Quanto ha trattenuto il fisco quel mese

---

## Dashboard Direct — "Quanto posso prelevare ogni mese?"

Usa questa modalità quando hai già un capitale (una vincita, un'eredità, la liquidazione di un immobile) e vuoi capire quanto puoi prelevare ogni mese senza esaurirlo prima del previsto.

### Parametri da inserire

| Campo | Cosa inserire |
|---|---|
| **Capitale totale** | L'importo lordo disponibile prima di qualsiasi destinazione |
| **Anni di autonomia** | Per quanti anni vuoi che duri |
| **Rendimento annuo lordo** | Come nella dashboard Reverse |
| **Inflazione media** | Come nella dashboard Reverse |
| **Tassazione ETF** | Come nella dashboard Reverse |
| **Beneficenza (%)** | Percentuale del capitale totale da donare subito al Giorno Zero |
| **Giorno Zero — regali** | Numero di persone e importo da regalare subito a ciascuna |
| **Distribuzione prelievi** | Come dividere il prelievo mensile tra te e i due gruppi (in percentuale) |

#### Opzione: Proteggi dall'inflazione (toggle)

Stesso comportamento della dashboard Reverse: il prelievo mensile cresce con l'inflazione per mantenere il potere d'acquisto. In questo caso il **primo prelievo** sarà più basso rispetto alla rata fissa, perché deve lasciare spazio alla crescita futura.

### Cosa leggi nei risultati

| Voce | Significato |
|---|---|
| **Bonifico Netto Mensile** | Il prelievo totale mensile sostenibile per il numero di anni scelto |
| **Capitale investito** | Quanto entra nel conto dopo le uscite del Giorno Zero |
| **Il tuo bonifico** | La tua quota personale del prelievo mensile |
| **Oneri Fiscali Totali** | Come nella dashboard Reverse |
| **Uscite Giorno Zero** | Beneficenza + regali |

Nella sezione **Erogazioni mensili** trovi lo spaccato per persona: quanto riceve ciascun membro del Gruppo 1 e del Gruppo 2.

### Il grafico

Identico alla dashboard Reverse: mostra la curva del capitale nel tempo. Stesso tooltip con tutti i dettagli anno per anno.

---

## Concetti chiave

### Rendimento annuo lordo
È la stima di quanto cresce il tuo portafoglio in un anno prima che lo Stato trattenga qualcosa. Per orientarti:
- Portafoglio prudente (obbligazioni + azionario): 2–3%
- Portafoglio bilanciato: 4–5%
- Portafoglio azionario globale (es. MSCI World): 6–7% (storico, non garantito)

Il simulatore usa questo valore come **tasso fisso medio per tutta la durata**. Vedi la sezione Limitazioni per capire perché questa è una semplificazione importante.

### Imposta di bollo (0,2% annuo)
È una tassa sul semplice possesso di un conto titoli, indipendente da guadagni o perdite. Il simulatore la applica ogni mese (0,2% ÷ 12) sul valore del portafoglio in quel momento.

### Tasse sulle plusvalenze (26%)
In Italia, quando vendi quote di un ETF ad accumulazione, paghi il 26% **solo sulla parte di guadagno effettivo** — non sull'intero prelievo. Se il tuo portafoglio è cresciuto poco rispetto a quanto hai investito, la tassazione è quasi nulla. Cresce nel tempo man mano che il portafoglio si apprezza.

Il simulatore calcola questo con il **Gain Ratio**: la percentuale del portafoglio che rappresenta guadagno puro rispetto al prezzo di acquisto originale.

### Rata fissa vs rata crescente
- **Rata fissa**: ricevi sempre lo stesso importo nominale ogni mese. Nel tempo, a causa dell'inflazione, comprerà meno cose.
- **Rata crescente**: l'importo aumenta ogni anno in linea con l'inflazione. Il tuo potere d'acquisto rimane costante, ma il capitale richiesto è significativamente maggiore.

---

## Limitazioni del modello

Queste sono le semplificazioni del simulatore che devi conoscere prima di usarlo per decisioni importanti.

### Rendimento medio fisso — il limite più importante

Il simulatore usa un **rendimento medio annuo costante** per tutti gli anni della simulazione. Nella realtà i mercati oscillano: ci sono anni al +20% e anni al -30%.

Questo crea il cosiddetto **rischio sequenza dei rendimenti**: se i primi anni della tua rendita coincidono con un mercato in forte calo, potresti esaurire il capitale molto prima di quanto il simulatore prevede, anche se la media di lungo periodo coincide con le tue ipotesi. Il simulatore non cattura questo rischio.

**Cosa fare:** usa ipotesi di rendimento conservative (2–4% invece di 6–7%) per costruire un margine di sicurezza.

### Aliquota fiscale fissa

Il simulatore usa l'aliquota del 26% per tutta la durata. La normativa fiscale può cambiare.

### Portafoglio singolo, un solo rendimento

Il modello assume un unico asset con rendimento omogeneo. Portafogli reali sono più complessi (diverse asset class, ribilanciamenti, dividendi, ecc.).

### Nessuna spesa straordinaria

Il modello non include spese impreviste (salute, immobili, emergenze). Il prelievo mensile è l'unica uscita prevista oltre al fisco.

---

## Disclaimer

**Questo strumento è esclusivamente a scopo educativo e informativo.**

I risultati prodotti dal simulatore sono proiezioni basate su ipotesi semplificate e non costituiscono consulenza finanziaria, fiscale o legale. Le performance passate dei mercati finanziari non garantiscono risultati futuri. Prima di prendere decisioni di investimento rilevanti, rivolgiti a un consulente finanziario indipendente e abilitato.

---

## Verifica dei calcoli

Il motore di calcolo è stato sottoposto a un audit indipendente in tre fasi:

1. **Verifica analitica** — per i casi senza tasse, i risultati del simulatore sono stati confrontati con la formula chiusa dell'annuity finanziaria: coincidono al centesimo.
2. **Simmetria cross-dashboard** — il capitale richiesto dalla dashboard Reverse, inserito nella dashboard Direct, restituisce esattamente lo stesso prelievo mensile (e viceversa). Errore massimo riscontrato: < €1 su importi fino a €2.000.000, attribuibile ad arrotondamenti floating point.
3. **Test di monotonia** — verificato che all'aumentare del rendimento il prelievo sostenibile aumenta, all'aumentare delle tasse diminuisce, e così via per tutte le variabili. Nessuna violazione riscontrata.

Il codice dell'audit è disponibile nel file `audit_v3.py`.

---

## Compatibilità

Testato su Chrome, Firefox, Edge e Safari (desktop e mobile).
Funziona su qualsiasi dispositivo con un browser moderno — nessuna installazione.
