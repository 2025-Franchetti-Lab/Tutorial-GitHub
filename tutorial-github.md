Tutorial GitHub

Introduzione

[🌐 Cos'è GitHub](#intro)
[📅 Storia e Origine](#storia)
[💼 Utilizzi Principali](#utilizzi)

Concetti Chiave

[📁 Repository](#repository)
[🌿 Branch](#branch)
[💻 Clone in Locale](#clone)
[📸 Commit](#commit)
[🔄 Push e Pull](#pushpull)

GitHub Desktop

[⬇️ Download](#download)
[⚙️ Installazione](#installazione)
[👤 Configurazione](#configurazione)
[🚀 Workflow Pratico](#workflow)

CORSO DI INFORMATICA — ANNO 1

# Introduzione a GitHub

Impara a gestire i tuoi progetti di codice con il sistema di controllo versione più diffuso al mondo, senza usare la riga di comando.

📚 Tutorial completo
🖥️ GitHub Desktop
⏱️ Lettura: ~25 min

## 1 Cos'è GitHub

**GitHub** è una piattaforma web che permette di *ospitare, condividere e collaborare*
su progetti software. È costruita attorno a **Git**, un sistema di *controllo versione*
(Version Control System, VCS) che tiene traccia di ogni modifica apportata al codice nel tempo.

In parole semplici: immagina di scrivere un documento di testo e di poter "salvare" ogni versione
con un messaggio che spiega cosa hai cambiato. Se commetti un errore, puoi tornare a qualunque
versione precedente. GitHub fa esattamente questo, ma per il codice sorgente, e in più ti permette
di lavorare insieme ad altri programmatori da tutto il mondo.

GitHub

piattaforma

👨‍💻
Sviluppatori

📁
Repository

🐛
Issues

⚙️
Actions/CI

🌐
Open Source

Fig. 1 — L'ecosistema GitHub: la piattaforma al centro connette sviluppatori, repository, issue tracking, automazioni e progetti open source

🗂️

#### Controllo Versione

Ogni modifica al codice viene registrata con data, autore e descrizione, permettendo di "viaggiare nel tempo".

🤝

#### Collaborazione

Più sviluppatori possono lavorare sullo stesso progetto senza sovrascriversi a vicenda.

☁️

#### Cloud Hosting

Il codice è salvato online, accessibile da qualsiasi computer e protetto da perdite accidentali.

🌍

#### Community Open Source

Milioni di progetti pubblici su cui puoi imparare, contribuire e fare fork liberamente.

## 2 Storia e Origine

Per capire GitHub è necessario conoscere prima **Git**, lo strumento su cui si basa.

2005
Git creato da
Linus Torvalds

2008
GitHub.com
viene lanciato

2012
1 milione di
repository

2018
Microsoft acquista
GitHub ($7.5B)

Oggi
>100M sviluppatori
nel mondo

Fig. 2 — Linea del tempo: da Git a GitHub fino ad oggi

### Git vs GitHub: qual è la differenza?

| Caratteristica | Git | GitHub |
| --- | --- | --- |
| **Tipo** | Software installato sul computer | Piattaforma web (servizio online) |
| **Funzione** | Traccia le modifiche localmente | Ospita repository online, facilita la collaborazione |
| **Creatore** | Linus Torvalds (2005) | Tom Preston-Werner et al. (2008) |
| **Utilizzo** | Da riga di comando o app grafiche | Tramite browser web o app desktop |
| **Costo** | Gratuito e open source | Gratuito (piano base) / a pagamento (piani avanzati) |

💡

**Da sapere**

GitHub non è l'unica piattaforma basata su Git. Esistono alternative come **GitLab** e **Bitbucket**, ma GitHub è la più usata con oltre 100 milioni di sviluppatori registrati.

## 3 Utilizzi Principali

GitHub è usato in moltissimi contesti, ben oltre la semplice archiviazione del codice:

🎓

#### Studio e Portfolio

Studenti e sviluppatori junior usano GitHub come portfolio: mostrano i propri progetti ai futuri datori di lavoro.

🏢

#### Lavoro in Team

Aziende di tutto il mondo coordinano team di sviluppo, gestiscono rilasci software e tracciano bug su GitHub.

🌐

#### Open Source

Projetti enormi come Linux, VS Code, React e Python sono ospitati su GitHub e aperti ai contributi di chiunque.

📄

#### Documentazione

Molte organizzazioni usano GitHub per gestire documentazione tecnica con lo stesso flusso del codice.

🤖

#### Automazioni CI/CD

Con GitHub Actions è possibile eseguire test automatici, build e deploy ogni volta che si pubblica nuovo codice.

🔍

#### Ricerca e Ispirazione

È la libreria più grande al mondo di codice sorgente: puoi cercare soluzioni, esempi e librerie per qualsiasi problema.

✅

**Perché impararlo subito?**

Quasi tutte le aziende del settore informatico usano Git e GitHub. Conoscerlo fin dal primo anno ti darà un vantaggio enorme sia negli studi sia nel mondo del lavoro.

## 4 Repository

Un **repository** (spesso abbreviato in *"repo"*) è la cartella principale di un progetto
gestito con Git. Contiene tutti i file del progetto e l'intera **cronologia** delle modifiche:
chi ha cambiato cosa, quando e perché.

Puoi pensarlo come una cartella "intelligente" che ricorda ogni cambiamento mai apportato,
in modo da poter tornare indietro in qualsiasi momento.

🔓 Repository PUBBLICO

👁️ Visibile a tutti
🔍 Cercabile su GitHub
🤝 Contribuzioni esterne
💸 Gratuito illimitato
🌐 Ideale per Open Source

🔒 Repository PRIVATO
👥 Solo persone invitate
🔐 Non cercabile
🏢 Ideale per lavoro/aziende
🎓 Utile per compiti scolastici
💚 Gratuito con GitHub Free

Fig. 3 — Differenze tra repository pubblico e privato

### Struttura di un Repository

All'interno di un repository troverai tipicamente:

📁 Contenuto tipico di un repository

📄

#### README.md

Il "biglietto da visita" del progetto. Spiega cos'è, come si usa e come contribuire. Viene mostrato automaticamente nella pagina principale del repo.

📂

#### Cartelle con i file di codice

Tutto il codice sorgente, organizzato in cartelle per funzione (es. `src/`, `tests/`, `docs/`).

🚫

#### .gitignore

Lista di file e cartelle che Git deve ignorare (es. file con password, file temporanei del sistema operativo).

📋

#### LICENSE

Specifica come il codice può essere usato da altri (es. MIT, GPL). Nei repo pubblici è molto importante.

💜

**Consiglio pratico**

Per i progetti scolastici, crea sempre un repository **privato**. Potrai renderlo pubblico in seguito, una volta che sei soddisfatto del risultato — diventerà parte del tuo portfolio!

## 5 Branch

Un **branch** (ramo) è una linea di sviluppo indipendente all'interno di un repository.
Immagina di stare scrivendo un racconto: il branch ti permette di esplorare un finale alternativo
su un foglio separato, senza toccare il manoscritto originale. Se il finale alternativo ti piace,
lo "unisci" (merge) alla storia principale; altrimenti lo butti via senza danni.

Commit su main

Commit su feature

Merge

main

C1
Primo commit

C2

C3
Crea branch

feature/nuova-funzione

F1

F2

C4

M
Merge!

C5

📌 Il branch main contiene il codice "ufficiale" e funzionante
Le nuove funzioni si sviluppano su branch separati e vengono unite solo quando sono pronte

Fig. 4 — Struttura dei branch: main (blu) e un branch feature (verde) che viene poi unito (merge, viola)

### Il Branch `main`

Ogni repository ha un branch principale chiamato **main** (in passato si chiamava *master*).
Questo è il ramo "ufficiale" del progetto: contiene la versione del codice che funziona correttamente
e che è pronta per essere usata.

🌿 Regola d'oro del branching

Il branch **main** dovrebbe contenere sempre codice che *funziona*. Le sperimentazioni, le nuove funzioni e le correzioni di bug si fanno su branch separati — si uniscono al main solo dopo aver verificato che tutto funzioni correttamente.

Per ora, come studenti alle prime armi, lavorerete principalmente direttamente sul branch main. Sarà sufficiente!

## 6 Clone in Locale

Il **clone** è l'operazione con cui scarichi una copia completa di un repository
da GitHub al tuo computer locale. Con il clone ottieni non solo i file, ma anche l'intera cronologia
dei commit: in pratica porti tutto il progetto sul tuo PC per lavorarci offline.

☁️ GitHub (Remote)

📁
mio-progetto
github.com/utente/mio-progetto

Clone

💻 Il Tuo Computer
📁
mio-progetto (copia locale)
C:\Utenti\Nome\mio-progetto

La copia locale è completa: include tutti i file e tutta la cronologia dei commit

Fig. 5 — Il clone crea una copia completa del repository da GitHub al computer locale

ℹ️

**Clone vs Download ZIP**

Potresti scaricare il codice come file ZIP dal sito, ma in quel caso perderesti tutta la cronologia Git e non potresti fare commit o sincronizzare le modifiche. Il clone è sempre la scelta giusta.

## 7 Commit

Un **commit** è un "salvataggio con messaggio" delle modifiche apportate ai file.
Ogni commit è una fotografia dello stato del progetto in un certo momento, accompagnata da
un messaggio che spiega *cosa* è cambiato e *perché*.

A differenza di Ctrl+S, che salva semplicemente il file, un commit registra la modifica
nella cronologia permanente del repository: non si perde mai e puoi tornare a qualsiasi
commit passato.

C1

a1b2c3d
Aggiungi
index.html

C2

e4f5g6h
Aggiungi
stile CSS

C3

i7j8k9l
Correggi bug
nel menu

C4

m0n1o2p ← HEAD
Aggiungi form
di contatto

Ora sei
qui ↓

Fig. 6 — Cronologia dei commit: ogni nodo è uno snapshot permanente del progetto, con hash univoco e messaggio descrittivo

### Anatomia di un buon Commit

✍️ Come scrivere un messaggio di commit efficace

Un messaggio di commit dovrebbe rispondere alla domanda: *"Se applicato, questo commit farà cosa?"*

| ❌ Messaggi da evitare | ✅ Messaggi corretti |
| --- | --- |
| modifica | Aggiungi validazione form di login |
| fix | Correggi bug nel calcolo del totale carrello |
| aggiornamento | Aggiorna versione libreria jQuery a 3.7.1 |
| cose varie | Rimuovi codice non utilizzato dalla homepage |

⚠️

**Importante: commit frequenti e piccoli**

È molto meglio fare tanti commit piccoli (uno per ogni piccola modifica) che un singolo grande commit con decine di cambiamenti. Così è più facile trovare dove è stato introdotto un bug.

## 8 Push e Pull

Dopo aver fatto dei commit in locale, le modifiche esistono solo sul tuo computer. Per sincronizzarle con GitHub, usi **Push** e **Pull**:

**Push** (spingere) = invii i tuoi commit locali verso GitHub.
**Pull** (tirare) = scarichi sul tuo computer i commit che altri hanno pubblicato su GitHub.

💻 Computer Locale
📁
Working copy
commits C1, C2, C3, C4

⬆️ Push

⬇️ Pull

☁️ GitHub (Remote)
📁
Repository remoto
commits C1, C2, C3, C4, C5…

Push → carichi le tue modifiche
Pull ← scarichi le altrui modifiche

Fig. 7 — Push e Pull: i due flussi di sincronizzazione tra computer locale e GitHub

### Fetch vs Pull

Esiste anche il comando **Fetch**, che *controlla* se ci sono aggiornamenti sul remote
senza scaricarli. È come guardare se hai posta in cassetta senza ancora prenderla.
Con GitHub Desktop il fetch avviene automaticamente in background.

| Operazione | Cosa fa | Quando usarla |
| --- | --- | --- |
| **Push** | Carica i tuoi commit locali su GitHub | Dopo aver fatto uno o più commit |
| **Pull** | Scarica e integra i commit dal remote | Ogni volta che inizi a lavorare (specialmente in team) |
| **Fetch** | Controlla se ci sono aggiornamenti (senza scaricarli) | Per vedere cosa è cambiato prima di integrare |

## 9 GitHub Desktop — Download

**GitHub Desktop** è l'applicazione ufficiale di GitHub che ti permette di eseguire
tutte le operazioni Git (clone, commit, push, pull…) tramite un'interfaccia grafica,
*senza mai toccare la riga di comando*. È gratuita, disponibile per Windows e macOS,
e perfetta per iniziare.

#### 🌐 Pagina di download ufficiale

Vai su **desktop.github.com** dal tuo browser per scaricare GitHub Desktop.
Il sito rileva automaticamente il tuo sistema operativo (Windows o macOS) e propone il file corretto.

### Requisiti di sistema

| Sistema Operativo | Versione minima | File da scaricare |
| --- | --- | --- |
| 🪟 **Windows** | Windows 10 (64-bit) o superiore | `GitHubDesktopSetup-x64.exe` |
| 🍎 **macOS** | macOS 10.15 Catalina o superiore | `GitHubDesktop-x64.zip` (Intel) o `-arm64.zip` (Apple Silicon) |

1

#### Apri il browser e vai su desktop.github.com

Vedrai un pulsante "Download for Windows" (o macOS). Il sito rileva automaticamente il tuo sistema operativo.

2

#### Clicca il pulsante di download

Verrà scaricato il file di installazione. Su Windows sarà un file `.exe`; su macOS un file `.zip`.

3

#### Salva il file e procedi all'installazione

Una volta completato il download, apri il file scaricato per avviare il processo di installazione (descritto nella prossima sezione).

✅

**GitHub Desktop include Git**

Non è necessario installare Git separatamente. GitHub Desktop include automaticamente tutto il necessario.

## 10 Installazione

### 🪟 Su Windows

1

#### Avvia il file .exe

Fai doppio clic su `GitHubDesktopSetup-x64.exe` nella cartella Download. Se appare un avviso di sicurezza di Windows, clicca su **"Esegui comunque"**.

2

#### Installazione automatica

L'installazione avviene in modo completamente automatico: non devi scegliere percorsi o opzioni. Attendi il completamento (circa 1–2 minuti).

3

#### Avvio automatico

Al termine dell'installazione, GitHub Desktop si avvia automaticamente e compare la schermata di benvenuto/accesso. Puoi trovare l'icona anche nel menu Start.

### 🍎 Su macOS

1

#### Estrai il file .zip

Fai doppio clic sul file `.zip` scaricato nella cartella Download. macOS estrarrà automaticamente l'applicazione `GitHub Desktop.app`.

2

#### Sposta nell'applicazioni

Trascina l'icona di `GitHub Desktop.app` nella cartella **Applicazioni** (per trovarlo facilmente con Spotlight e Launchpad).

3

#### Apri e consenti l'esecuzione

Al primo avvio macOS potrebbe chiedere conferma perché l'app proviene da Internet. Clicca **"Apri"** nella finestra di avviso. Poi segui la configurazione guidata.

ℹ️

**Nota per macOS con chip Apple Silicon (M1/M2/M3)**

Se hai un Mac con chip Apple Silicon, scarica la versione `-arm64.zip` invece di quella `-x64.zip`. In caso di dubbio, clicca sul menu Apple → "Informazioni su questo Mac" e guarda il processore.

## 11 Configurazione

Al primo avvio, GitHub Desktop ti guida nella configurazione iniziale in pochi semplici passi.

### Passo 1 — Accedi o crea un account GitHub

1

#### Crea un account (se non ce l'hai)

Vai su **github.com**, clicca **"Sign up"** e registrati con la tua email. È completamente gratuito. Scegli uno username semplice da ricordare: sarà visibile nei tuoi repository.

2

#### Nella schermata di benvenuto di GitHub Desktop

Clicca **"Sign in to GitHub.com"**. Si aprirà il browser con la pagina di login di GitHub.

3

#### Autorizza GitHub Desktop

Dopo aver fatto login nel browser, GitHub ti chiederà di autorizzare l'applicazione Desktop. Clicca **"Authorize desktop"**. Il browser ti chiederà di tornare all'applicazione: conferma.

GitHub Desktop
Clicca Sign In

apre

Browser
Login su GitHub

autorizza

GitHub.com
Authorize Desktop

torna a

✅ Loggato!
Pronto all'uso

Fig. 8 — Flusso di autenticazione di GitHub Desktop con il proprio account GitHub

### Passo 2 — Configura nome e email

Dopo il login, GitHub Desktop ti chiede di impostare il **nome** e l'**email**
che appariranno in ogni tuo commit. Questi dati identificano l'autore delle modifiche nella cronologia del repository.

⚠️

**Usa la stessa email dell'account GitHub**

Se usi un'email diversa da quella del tuo account GitHub, i commit non verranno associati al tuo profilo. Usa esattamente la stessa email con cui ti sei registrato.

Puoi modificare nome e email in qualsiasi momento da:

GitHub Desktop
→
Preferences / Impostazioni
→
Git

💜

**Configurazione completata!**

A questo punto GitHub Desktop è pronto per essere usato. Nella prossima sezione vedremo come eseguire le operazioni principali in modo pratico.

## 12 Workflow Pratico con GitHub Desktop

Ora che hai configurato GitHub Desktop, vediamo come eseguire ogni operazione passo per passo.

📁 A — Creare un nuovo Repository

1

#### Apri GitHub Desktop

Clicca sul menu **File** e scegli **"New Repository…"** oppure usa la scorciatoia `Ctrl+N` (Windows) / `⌘N` (macOS).

2

#### Compila il modulo

Inserisci il **nome** del repository (es. `primo-progetto`), una breve descrizione, scegli dove salvarlo sul tuo computer e seleziona se inizializzare con un README. Se vuoi che il repo sia privato, lo imposterai dopo la pubblicazione.

3

#### Clicca "Create Repository"

GitHub Desktop crea la cartella sul tuo computer con Git già inizializzato. Vedrai il repository apparire nell'elenco a sinistra.

4

#### Pubblica su GitHub (Publish)

Clicca il pulsante **"Publish repository"** in alto a destra. Potrai scegliere se tenerlo privato o pubblico. Clicca nuovamente **"Publish Repository"** per confermare.

💻 B — Clonare un Repository Esistente

1

#### Clona da GitHub Desktop

Clicca **File → Clone Repository…** oppure `Ctrl+Shift+O` / `⌘⇧O`.

2

#### Scegli il repository

Nella scheda **"GitHub.com"** vedrai tutti i tuoi repository. Seleziona quello che vuoi clonare, scegli la cartella di destinazione sul tuo PC e clicca **"Clone"**.

3

#### Oppure clona da URL

Usa la scheda **"URL"** e incolla l'indirizzo del repository (es. `https://github.com/utente/repo`). Utile per clonare repository di altri utenti o organizzazioni.

📸 C — Fare un Commit

1

#### Modifica i file del progetto

Apri la cartella del repository con il tuo editor preferito (es. Visual Studio Code) e apporta le modifiche ai file che ti servono.

2

#### Torna su GitHub Desktop

Vedrai automaticamente nella colonna sinistra i file modificati, con un segno di spunta accanto a ciascuno. I file con spunta verde verranno inclusi nel commit. Clicca sul nome di un file per vedere le differenze (righe in rosso = rimosse, in verde = aggiunte).

3

#### Scrivi il messaggio del commit

In basso a sinistra, nel campo **"Summary (required)"**, scrivi un messaggio breve e descrittivo (es. *"Aggiungi navigazione al menu principale"*). Puoi aggiungere una descrizione più lunga nel campo **"Description"**.

4

#### Clicca "Commit to main"

Il commit viene salvato nella cronologia locale. Nota: le modifiche sono ancora solo sul tuo computer!

⬆️ D — Push: Invia i Commit a GitHub

1

#### Dopo aver fatto uno o più commit

In alto vedrai il pulsante **"Push origin"** con un numero che indica quanti commit locali devono essere ancora inviati a GitHub.

2

#### Clicca "Push origin"

GitHub Desktop invierà tutti i commit locali al repository remoto su GitHub. Puoi verificare andando su github.com e aprendo il tuo repository: vedrai i file aggiornati.

💡

**Push frequente**

Fai push regolarmente, non solo alla fine della giornata. Così il tuo lavoro è sempre al sicuro su GitHub, anche se il computer si guasta.

⬇️ E — Pull: Scarica Aggiornamenti da GitHub

1

#### Controlla se ci sono aggiornamenti

GitHub Desktop aggiorna automaticamente in background lo stato del remote. Se altri hanno fatto push (o se tu stesso hai modificato qualcosa via browser), vedrai il pulsante **"Pull origin"** con un numero.

2

#### Clicca "Pull origin"

GitHub Desktop scarica e integra automaticamente i nuovi commit. I file nella tua cartella locale vengono aggiornati.

⚠️

**Fai sempre Pull prima di iniziare a lavorare**

Se stai collaborando con altri (o lavori su più computer), fai sempre Pull come prima cosa. Eviterai conflitti e lavorerai sempre sulla versione più aggiornata del codice.

### Il Workflow Completo

⬇️ Pull
Aggiornati

✏️ Modifica
i file

📸 Commit
Salva snap

⬆️ Push
Carica su GitHub

✅ Online!
Codice su GitHub

Ripeti il ciclo per ogni nuova modifica

Fig. 9 — Il ciclo di lavoro con GitHub Desktop: Pull → Modifica → Commit → Push

## 📋 Riepilogo dei Concetti

Ecco un glossario rapido di tutti i termini imparati in questo tutorial:

| Termine | Definizione rapida | Analogia |
| --- | --- | --- |
| **Git** | Software di controllo versione installato sul PC | Il motore di un'auto |
| **GitHub** | Piattaforma web per ospitare repository Git | Il garage dove parcheggi l'auto |
| **Repository** | Cartella progetto con cronologia completa | Un raccoglitore con tutte le bozze di un documento |
| **Branch** | Linea di sviluppo parallela | Un foglio separato per bozze alternative |
| **main** | Branch principale con il codice ufficiale | La versione definitiva del documento |
| **Clone** | Copia locale completa di un repository remoto | Fotocopiare l'intero raccoglitore |
| **Commit** | Salvataggio con messaggio nella cronologia | Una foto istantanea del documento con una didascalia |
| **Push** | Carica i commit locali su GitHub | Inviare la bozza al professore |
| **Pull** | Scarica i commit dal remote al PC locale | Ricevere le correzioni del professore |
| **GitHub Desktop** | App grafica per usare Git senza riga di comando | Un'auto con il cambio automatico invece che manuale |

🎉

**Complimenti!**

Hai completato l'introduzione a GitHub. Ora conosci i concetti fondamentali e sai come usare GitHub Desktop per gestire i tuoi progetti. Il passo successivo? Crea il tuo primo repository, aggiungi qualche file di codice e prova il ciclo Pull → Commit → Push!

Tutorial GitHub — Introduzione alla Piattaforma  |  Corso di Informatica — Anno 1

Realizzato per uso didattico  ·  Immagini e loghi di GitHub appartengono a GitHub, Inc.
