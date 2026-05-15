[Tutorial GitHub](index.html)

In questa pagina

[Collaboratori](#collaboratori)
[Casi d'uso](#collab-usecases)
[Pro & Contro](#collab-procon)
[Come si gestiscono](#collab-steps)
[Branch](#branch)
[Casi d'uso](#branch-usecases)
[Pro & Contro](#branch-procon)
[Workflow tipico](#branch-workflow)
[Fork](#fork)
[Casi d'uso](#fork-usecases)
[Pro & Contro](#fork-procon)
[Contributo vs Personale](#fork-tipi)
[Riepilogo](#riepilogo)

Altri tutorial

[Introduzione a GitHub](tutorial-github.html)
[← Torna all'indice](index.html)

CORSO TEPSIT — ANNO 3

# Collaboratori, Branch e Fork

I tre meccanismi fondamentali per lavorare in team su GitHub: quando usarli, come funzionano, vantaggi e limiti di ciascuno.

Lettura ~20 min

Collaboratori · Branch · Fork

Diagrammi SVG inclusi

## 1 Collaboratori

Un **collaboratore** è un utente GitHub a cui il proprietario di un repository ha concesso accesso diretto in scrittura (*write access*). A differenza dei fork, i collaboratori lavorano *direttamente* sul repository originale, con piena capacità di aprire branch, fare push e fare merge.

Repository
Centrale (GitHub)

👑 Owner
Accesso pieno

👤 Collab. A
Write access

👤 Collab. B
Write access

👤 Collab. C
Write access

push / pull
push / pull
push / pull

Tutti i collaboratori lavorano direttamente sullo stesso repository centrale.

### Casi d'uso ottimali

🏢

#### Team aziendale privato

Piccolo gruppo di sviluppatori fidati che lavorano sullo stesso prodotto.

🎓

#### Progetto scolastico

Studenti che collaborano su un repository di gruppo senza burocrazia aggiuntiva.

🔒

#### Repository privato

Quando il codice non è pubblico e si vuole controllare chi accede.

⚡

#### Iterazioni rapide

Startup o hackathon dove la velocità conta più della formalità delle review.

✔ Pro

* Accesso diretto, nessun fork necessario
* Configurazione semplice e immediata
* Visibilità completa sulla storia dei commit
* Ideale per team piccoli e fidati
* Possibilità di assegnare diversi livelli di permesso (read, triage, write, maintain, admin)

✘ Contro

* Rischio di push accidentali su branch protetti
* Ogni collaboratore vede e modifica l'intera codebase
* Non scalabile per community aperte (open source pubblico)
* Difficile revocare selettivamente l'accesso a singole parti
* Un collaboratore con permessi elevati può causare danni irreversibili

### Come aggiungere un collaboratore

1

#### Vai alle impostazioni del repository

Dal repository su GitHub, clicca su *Settings* → *Collaborators and teams*.

2

#### Aggiungi il collaboratore

Clicca su *Add people* e cerca il nome utente o l'indirizzo email GitHub della persona.

3

#### Scegli il livello di accesso

Seleziona il ruolo: **Read** (solo lettura), **Triage** (gestione issue/PR), **Write** (push), **Maintain** o **Admin**.

4

#### L'invitato accetta l'invito

Il collaboratore riceve un'email con il link all'invito e deve accettarlo entro 7 giorni.

ℹ️

**Branch Protection Rules**

Per proteggere il branch `main` da push diretti accidentali, vai in *Settings → Branches → Add rule* e abilita "Require a pull request before merging". Così anche i collaboratori con write access devono passare da una PR.

⚠️

**Attenzione ai permessi Admin**

Un collaboratore con ruolo **Admin** può modificare le impostazioni del repository, eliminare branch protetti o addirittura cancellare il repository stesso. Assegna questo ruolo con estrema cautela.

## 2 Branch

Un **branch** (ramo) è una linea di sviluppo indipendente all'interno dello stesso repository. Ogni branch è essenzialmente un puntatore mobile a uno specifico commit. Creare un branch non crea copie di file: Git si limita a memorizzare le differenze (*delta*), rendendo l'operazione istantanea e leggerissima.

main

feature

merge

C1
C2
C3
C7
C8
C4
C5
C6

hotfix

H1
fix urgente

Il branch `feature` si ramifica da `main` in C3, evolve autonomamente e poi viene unito con un merge. Il branch `hotfix` gestisce una correzione urgente.

### Casi d'uso ottimali

🌿

#### Feature branch

Ogni nuova funzionalità viene sviluppata in isolamento, senza interferire con il codice stabile.

🚑

#### Hotfix

Correzione urgente di un bug in produzione senza dover attendere il completamento delle feature in sviluppo.

🧪

#### Sperimentazione

Testare un approccio tecnico rischioso senza compromettere il codice principale.

🔖

#### Release branch

Congelare una versione per le ultime correzioni mentre `main` procede con nuove feature.

👩‍💻

#### Code review

Il branch è la base per aprire una Pull Request e ricevere feedback prima del merge.

🏭

#### Ambienti multipli

Branch `develop`, `staging`, `production` per gestire i diversi ambienti di deploy.

✔ Pro

* Operazione istantanea e a costo quasi zero (solo un puntatore)
* Isolamento completo del lavoro in corso
* Facilita la code review tramite Pull Request
* Permette di lavorare in parallelo su più feature
* Rollback facile: basta non fare merge o eliminare il branch
* Integrazione con CI/CD: ogni branch può avere la sua pipeline

✘ Contro

* I branch longevi accumulano *merge conflicts* difficili da risolvere
* Richiede disciplina: branch abbandonati creano confusione
* Il merge di branch divergenti può richiedere molto tempo
* Senza naming convention il repository diventa caotico
* Non adatto a isolare lavori di persone esterne al repository

### Workflow tipico con i branch

🌐 GitHub Web

🖥️ GitHub Desktop

🌐 GitHub.com — interfaccia web

1

#### Apri il repository e crea il branch

Nel repository su GitHub, clicca sul selettore del branch in alto a sinistra (di solito mostra **main**). Digita il nome del nuovo branch nel campo di ricerca, ad esempio `feature/login-oauth`, quindi clicca su *"Create branch: feature/login-oauth from main"*.

📁 Repository
→
⎇ main ▾
→
digita nome branch
→
Create branch…

2

#### Modifica i file direttamente online

GitHub include un editor di testo integrato. Naviga nel file da modificare, clicca sull'icona della matita **✏️** in alto a destra, apporta le modifiche e clicca su *"Commit changes…"*. Scegli la modalità *"Commit directly to feature/login-oauth branch"*.

Apri file
→
✏️ Edit
→
Commit changes…

3

#### Apri la Pull Request

Dopo il commit, GitHub mostra un banner giallo *"Compare & pull request"*. Cliccalo, inserisci titolo e descrizione della PR, assegna reviewer se necessario, poi clicca *"Create pull request"*.

Compare & pull request
→
Titolo + descrizione
→
Create pull request

4

#### Review e merge

I reviewer approvano la PR. Il maintainer clicca *"Merge pull request"* → *"Confirm merge"*. Si può scegliere tra *Merge commit*, *Squash and merge* o *Rebase and merge* dal menu a discesa.

5

#### Elimina il branch

Dopo il merge, GitHub propone automaticamente il pulsante *"Delete branch"* nella pagina della PR. Cliccalo per rimuovere il branch remoto.

**Nota per chi usa anche il terminale:** se lavori localmente, clona o aggiorna il repository con
`git pull`, crea il branch con `git switch -c feature/login-oauth` e pubblicalo con
`git push -u origin feature/login-oauth`. Il resto (PR, merge, eliminazione) si fa comunque su GitHub.com.

🖥️ GitHub Desktop — app per Windows e macOS

1

#### Aggiorna il repository locale

Assicurati di essere su **main**: dal menu in alto seleziona il branch *main* nel selettore centrale. Poi clicca *"Fetch origin"* nella toolbar per scaricare gli ultimi aggiornamenti.

⎇ Current Branch: main
→
Fetch origin

2

#### Crea il nuovo branch

Clicca sul pulsante *"Current Branch"* → *"New Branch"*. Inserisci il nome `feature/login-oauth` e clicca *"Create Branch"*. GitHub Desktop crea e passa automaticamente sul nuovo branch.

⎇ Current Branch
→
New Branch
→
digita nome
→
Create Branch

3

#### Modifica i file con il tuo editor

Clicca *"Open in …"* (VS Code, Xcode, ecc.) nella toolbar di GitHub Desktop oppure naviga manualmente alla cartella. Salva le modifiche: appariranno automaticamente nel pannello *Changes* a sinistra di GitHub Desktop.

4

#### Committa le modifiche

Nel pannello *Changes*, spunta i file da includere, scrivi un titolo per il commit nel campo in basso (es. *"feat: aggiunge login OAuth"*) e clicca *"Commit to feature/login-oauth"*.

☑ seleziona file
→
Titolo commit
→
Commit to feature/…

5

#### Pubblica il branch su GitHub

Clicca il pulsante blu *"Publish branch"* nella toolbar. Il branch verrà caricato sul repository remoto su GitHub.com.

Publish branch

6

#### Apri la Pull Request da Desktop

Clicca *"Create Pull Request"* nella toolbar (o nel menu *Branch*): si apre automaticamente la pagina della PR su GitHub.com nel browser, già precompilata. Completa titolo, descrizione e crea la PR.

Branch
→
Create Pull Request
→
[si apre GitHub.com]

7

#### Dopo il merge: sincronizza e pulisci

Torna su **main** dal selettore branch, clicca *"Fetch origin"* poi *"Pull origin"*. Per eliminare il branch locale: *Branch* → *Delete…* → spunta *"Delete remote branch"*.

⎇ main
→
Pull origin
→
Branch → Delete…

💡

**Naming convention consigliata**

Usa prefissi per tipo: `feature/` per nuove funzionalità, `fix/` per bug, `hotfix/` per urgenze, `chore/` per manutenzione, `docs/` per documentazione. Separa le parole con il trattino: `feature/user-profile-page`.

### Principali strategie di branching

| Strategia | Descrizione | Adatta per | Complessità |
| --- | --- | --- | --- |
| **GitHub Flow** | Solo `main` + branch feature. Si fa PR e si mergia direttamente su main. | Web app con deploy continuo | Bassa |
| **Git Flow** | `main`, `develop`, `feature/*`, `release/*`, `hotfix/*` | Software con release versionate | Alta |
| **Trunk-based** | Branch cortissimi (max 1-2 giorni), merge frequenti su `main`. | Team maturi con alta copertura test | Media |
| **Forking Flow** | Ogni sviluppatore ha un fork personale. I branch vengono aperti lì. | Open source / contributori esterni | Media |

## 3 Fork

Un **fork** è una copia completa e indipendente di un repository, creata nel proprio account GitHub. Il fork mantiene un legame con il repository originale (detto *upstream*), permettendo di sincronizzare i cambiamenti, ma lo sviluppo avviene su una copia separata. È il meccanismo alla base di tutta la collaborazione open source.

🏠 Repo Originale
upstream / owner
github.com/owner/progetto

🍴 Fork di Alice
github.com/alice/progetto
copia autonoma

🍴 Fork di Bob
github.com/bob/progetto
copia autonoma

fork

fork

Pull Request

sync

Alice e Bob eseguono un fork del repository originale, lavorano sulle proprie copie e possono proporre modifiche tramite Pull Request. La sincronizzazione (fetch upstream) mantiene i fork aggiornati.

### Casi d'uso ottimali

🌍

#### Contribuire all'open source

Il modo standard per proporre modifiche a progetti pubblici senza avere write access.

🔬

#### Sperimentazione libera

Provare modifiche radicali all'architettura senza rischiare di rompere nulla sull'originale.

📚

#### Apprendimento da codice altrui

Forkare un progetto interessante per studiarlo, modificarlo e vedere gli effetti.

🛠️

#### Mantenere una variante

Creare e mantenere una versione personalizzata di un software (es. tema con le modifiche del proprio brand).

🏛️

#### Archivio personale

Salvare una copia di un progetto che potrebbe essere rimosso o reso privato.

👥

#### Community aperte

Migliaia di contributori possono lavorare in parallelo senza coordinarsi anticipatamente.

✔ Pro

* Non serve alcun permesso sul repository originale
* Massimo isolamento: i cambiamenti non impattano l'upstream
* Ideale per community aperte con molti contributori anonimi
* Il proprietario dell'upstream mantiene il pieno controllo
* Permette di mantenere una variante divergente a lungo termine
* Punto di partenza per imparare da codice reale in modo sicuro

✘ Contro

* Processo più lungo: fork → branch → PR → review → merge
* Il fork può divergere molto dal progetto originale nel tempo
* Sincronizzazione (fetch upstream) manuale e soggetta a conflitti
* Non adatto per team interni dove si ha già accesso
* Un fork abbandonato può creare confusione su quale sia il progetto "vero"
* Issues e Projects del fork non sono collegati all'upstream

### Sincronizzare il fork con l'upstream

🌐 GitHub Web

🖥️ GitHub Desktop

🌐 GitHub.com — metodo più rapido

1

#### Vai alla pagina del tuo fork

Accedi a GitHub e apri il tuo fork (sarà elencato tra i tuoi repository con il simbolo 🍴). Nota che sotto il nome del repository è indicato *"forked from owner/progetto"*.

2

#### Clicca su "Sync fork"

Vicino al selettore del branch trovi il pulsante *"Sync fork"* con un indicatore del numero di commit di cui sei indietro rispetto all'upstream. Cliccalo per aprire il pannello di sincronizzazione.

⎇ main
·
🔄 Sync fork ▾

3

#### Conferma l'aggiornamento

Nel pannello che si apre, GitHub mostra quanti commit e quale branch dell'upstream verranno applicati. Clicca *"Update branch"* per completare la sincronizzazione. Se ci sono conflitti, GitHub ti avvisa e ti chiede di risolverli.

Update branch

💡

**Quando compare il pulsante "Sync fork"?**

Il pulsante appare solo quando il repository upstream ha nuovi commit che il tuo fork non ha ancora. Se i due sono allineati, il pulsante non è visibile. Controlla periodicamente, specialmente prima di iniziare un nuovo contributo.

🖥️ GitHub Desktop — sincronizzazione locale

1

#### Apri il fork in GitHub Desktop

Se hai già clonato il fork, aprilo da *File → Add Local Repository* oppure da *File → Clone Repository* se è la prima volta. Assicurati di essere sul branch **main**.

2

#### Aggiorna il fork tramite "Branch → Merge into current branch…"

GitHub Desktop rileva automaticamente il repository upstream. Dal menu in alto scegli *Branch* → *Merge into current branch…*. Nella finestra che si apre, seleziona **upstream/main** (o il branch principale dell'upstream) e clicca *"Merge upstream/main into main"*.

Branch
→
Merge into current branch…
→
upstream/main
→
Merge

3

#### Pubblica i nuovi commit sul fork remoto

Dopo il merge locale, clicca *"Push origin"* nella toolbar per aggiornare anche il tuo fork su GitHub.com.

Push origin

**Alternativa da terminale (solo per riferimento):**
`git fetch upstream` → `git merge upstream/main` → `git push origin main`.
GitHub Desktop esegue gli stessi passaggi internamente.

## 4 Fork per Contribuire vs Fork Personale

L'operazione tecnica di fork è identica in entrambi i casi, ma l'**intenzione**, il **ciclo di vita** e la **gestione** del fork cambiano radicalmente a seconda dello scopo. Comprendere questa differenza evita confusione e pratiche sbagliate.

🤝

#### Fork per Contribuire

* L'obiettivo finale è proporre modifiche al progetto originale tramite una **Pull Request**
* Il fork deve **rimanere sincronizzato** con l'upstream il più possibile
* Si creano branch tematici (`fix/bug-123`) per ogni contributo, poi si elimina il branch dopo il merge
* Le modifiche sono pensate per essere **accettate dalla community** del progetto originale
* Il fork di solito è **temporaneo** o viene mantenuto solo come base di lavoro
* Le issue e le discussioni avvengono sul **repository upstream**, non sul fork
* Il fork non dovrebbe avere una propria README o documentazione divergente

🧩

#### Fork Personale / Variante

* L'obiettivo è creare una **versione modificata** per uso proprio, senza intenzione di contribuire all'upstream
* La sincronizzazione con l'upstream è **opzionale e selettiva** (solo bugfix, non feature)
* Si lavora direttamente su `main` o su branch propri, senza preoccuparsi della compatibilità con l'upstream
* Le modifiche possono essere **incompatibili** con la visione del progetto originale
* Il fork diventa un **progetto indipendente** con la propria identità (es. cambiare nome, aggiungere feature specifiche)
* Issues, wiki e documentazione sono propri del fork
* Esempio: forkare un tema Jekyll per personalizzarlo per il proprio blog

🤝 Contributo all'upstream

🧩 Fork Personale

Fork del repo upstream

Crea branch fix/feature

Commit e push sul fork

Apri Pull Request → upstream

✓ Merge (o rifiuto)

Fork del repo base

Modifica direttamente main

Aggiungi feature proprie

Sync selettivo dall'upstream

Progetto autonomo ∞

Il ciclo di vita è molto diverso: il fork per contribuire converge verso l'upstream, il fork personale diverge e diventa autonomo.

### Domande guida per capire quale tipo di fork stai facendo

| Domanda | Contributo | Personale |
| --- | --- | --- |
| Vuoi che le tue modifiche vengano accettate dall'upstream? | ✅ Sì, è l'obiettivo | ❌ Non necessariamente |
| Il tuo fork deve rispecchiare l'upstream? | ✅ Sì, tienilo sincronizzato | ⚠️ Solo quando serve |
| Le tue modifiche rispettano le linee guida del progetto? | ✅ Obbligatorio (CONTRIBUTING.md) | ❌ Non importa |
| Aprirai una Pull Request? | ✅ Sì, è il passaggio finale | ❌ Probabilmente no |
| Il fork ha una sua identità/brand propria? | ❌ No, è solo un tramite | ✅ Sì, è un prodotto distinto |
| Le modifiche sono compatibili con l'upstream? | ✅ Devono esserlo | ⚠️ Spesso no |

📌

**Nota sulla licenza**

Quando forki un progetto per uso personale, devi rispettare la licenza del progetto originale. Una licenza MIT permette modifiche e redistribuzione libera; una GPL impone che anche il fork derivato sia open source; una licenza proprietaria potrebbe vietare il fork del codice sorgente. Controlla sempre il file `LICENSE` prima di usare un fork per scopi commerciali o pubblici.

## 5 Riepilogo: Quando usare cosa

I tre strumenti non sono alternativi: si usano spesso insieme. Il punto chiave è capire *quali diritti di accesso hai* e *qual è il tuo obiettivo*.

👥

#### Usa i Collaboratori

Quando hai un team ristretto e fidato che deve lavorare direttamente sullo stesso repository, specialmente se privato.

🌿

#### Usa i Branch

Sempre e comunque, per qualsiasi unità di lavoro: una feature, un fix, un esperimento. Non committare mai direttamente su `main`.

🍴

#### Usa il Fork

Quando non hai accesso al repository (open source) oppure vuoi una copia completamente indipendente per uso personale o per creare una variante.

### Confronto finale

| Caratteristica | Collaboratori | Branch | Fork |
| --- | --- | --- | --- |
| **Serve permesso sull'originale?** | ✅ Sì (admin lo aggiunge) | ✅ Sì (write access) | ❌ No |
| **Dove vive il codice?** | Stesso repository | Stesso repository | Repository separato |
| **Isolamento del lavoro** | Dipende dai branch usati | Alto (branch separato) | Massimo (repo separato) |
| **Complessità di setup** | Bassa | Bassissima | Media |
| **Scalabilità (numero utenti)** | Piccoli team (≤20) | Illimitata | Illimitata |
| **Proposta modifiche all'upstream** | Diretta (push + PR interna) | Pull Request interna | Pull Request esterna |
| **Gestione accesso granulare** | Ruoli: read/write/admin | Branch protection rules | Non necessaria |
| **Rischio sul repository originale** | Medio (dipende dai permessi) | Basso (PR + review) | Nullo |

🎯

**La combo vincente per un progetto scolastico o aziendale**

Aggiungi i membri del team come **collaboratori** con write access → ognuno lavora su un **branch** dedicato → propone il merge tramite **Pull Request** → il maintainer fa review e approva. Branch protection su `main` impedisce push diretti accidentali. Questo schema è usato dalla stragrande maggioranza dei team professionali.

[Torna all'indice](index.html)
