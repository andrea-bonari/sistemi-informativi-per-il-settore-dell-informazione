>[!note]  
>Il livello architettura definisce come l'hardware e il software si organizzano per gestire la risorsa informazione, illustrando le diverse architetture fisiche su cui possono essere collocati i componenti di un sistema informativo. L'architettura definisce l'insieme delle scelte tecniche e organizzative che influenzano sviluppo e utilizzo delle risorse IT.
>
>Si distinguono due macro-categorie di architetture: centralizzate e distribuite. Nei sistemi centralizzati, dati e applicazioni risiedono su un unico nodo di elaborazione, mentre i terminali connessi dispongono solo di funzioni basilari di input e output.
>
>Le architetture distribuite si caratterizzano, invece, per la presenza di più nodi capaci di elaborare e cooperare, con applicazioni e basi di dati distribuite ma coordinate.

Negli anni '90, il modello distribuito ha mostrato limiti di complessità gestionale e progettuale, aggravati dall'espansione di Internet. Ciò ha portato allo sviluppo di architetture multilivello, che distribuiscono in modo più efficiente i livelli logici delle applicazioni sui livelli fisici dei sistemi, garantendo maggiore scalabilità e capacità di risposta a un elevato numero di utenti.
### Applicazioni distribuite
>[!note]  
>Le applicazioni distribuite suddividono i livelli logici del software (layer di presentazione, logica applicativa e gestione dati) su più livelli hardware, detti tier. Ogni tier è una macchina o un insieme di macchine dotate di capacità elaborative proprie. La modalità con cui i layer vengono distribuiti sui tier determina diverse tipologie di architetture, che variano per flessibilità, prestazioni e complessità gestionale.

>[!tip] Architettura Single-Tiered
>Nell'architettura Single-Tiered, tutti i livelli software risiedono su un unico nodo, come nei sistemi mainframe. Questa soluzione centralizzata è oggi considerata obsoleta ma rimane valida per affidabilità, prestazioni e semplicità di manutenzione. Tuttavia, è rigida e poco adatta a interfacce grafiche evolute, poiché accentra anche l'elaborazione visiva sul server centrale.

>[!tip] Architettura Two-Tiered
>L'architettura Two-Tiered introduce una separazione tra client e server, distribuendo i layer su due nodi. Nata negli anni '80 con il modello client/server, può assumere varie configurazioni in base alla collocazione dei layer logici. Si distinguono i thin client, che gestiscono solo la presentazione (come i browser Web), e i thick client, che includono anche parte della logica applicativa (come le app mobili). I thin client richiedono connessioni stabili ma hanno bassa complessità, mentre i thick client riducono la dipendenza dalla rete ma aumentano i costi di aggiornamento e gestione distribuita.
>
>![[Pasted image 20251111163330.png]]

>[!tip] Architettura Three-Tiered
>L'architettura Three-Tiered suddivide i tre layer su tre macchine distinte: client, server intermedio (middle tier) e server dati. Questo modello migliora sicurezza, scalabilità e flessibilità. Il middle tier gestisce la logica applicativa, riduce il carico sul DBMS e mantiene connessioni permanenti con esso, ottimizzando le prestazioni per un alto numero di utenti. Le configurazioni thin sono preferite per applicazioni Internet, mentre le thick si adattano meglio a contesti Intranet.
>
>![[Pasted image 20251111163347.png]]

>[!tip] Architetture $n$-Tiered
>Le architetture $n$-Tiered estendono il modello a più livelli fisici, distribuendo ulteriormente le funzioni su macchine dedicate (gateway server, authentication server, transaction server, database server, ecc.). Nei sistemi informativi basati su Web, è comune una struttura a cinque tier, dove i primi tre gestiscono la presentazione (browser, web server e script engine) e gli altri due gestiscono logica applicativa e dati. L'aggiunta di componenti come database gateway migliora l'integrazione di sorgenti dati eterogenee, assicurando trasparenza e semplificando la manutenzione del sistema.

### Scalabilità
> [!note]  
> La scalabilità di un'architettura IT è la capacità di adattarsi a un aumento delle richieste degli utenti mantenendo prestazioni adeguate. Può essere ottenuta attraverso aggiornamenti dell'hardware o modifiche alla struttura del sistema, con l'obiettivo di gestire carichi crescenti senza comprometterne l'efficienza.

La scalabilità verticale (scale-up) aumenta le prestazioni potenziando un singolo nodo, ad esempio aggiungendo CPU, RAM o memoria. È semplice da realizzare ma limitata da vincoli fisici e da una crescita delle prestazioni non sempre proporzionale all'aumento delle risorse.

La scalabilità orizzontale (scale-out) replica i nodi per distribuire il carico di lavoro. Richiede sistemi di load balancing ma offre maggiore flessibilità e costi contenuti grazie al principio del downsizing, secondo cui più server economici possono sostituire uno di fascia alta a parità di potenza complessiva. Tuttavia, la progettazione è più complessa e deve bilanciare il numero ottimale di nodi per evitare sprechi o carenze di risorse. Nel contesto Web si introduce, inoltre, il concetto di elasticità, ossia la capacità di un sistema di aumentare o ridurre dinamicamente le proprie risorse in base alla domanda. L'elasticità può essere vista come una forma reversibile di scalabilità orizzontale, ed è un principio fondamentale del Cloud Computing.

> [!tip] Server Farm
> Le server farm rappresentano un approccio tipico di scale-out: gruppi di server che condividono carichi, applicazioni e dati, percepiti come un'unica risorsa. Garantiscono elevata scalabilità e disponibilità, con costi ridotti rispetto ai sistemi centralizzati. Possono essere organizzate secondo due modelli principali:
>- Cloning (RACS): tutti i server eseguono le stesse applicazioni e dati. Offrono tolleranza ai guasti e possono essere configurati come shared-nothing (dati replicati su ogni nodo, ideali per servizi di sola lettura) o shared-disk (dati condivisi in un cluster). ![[Pasted image 20251111164718.png|center]]
>- Partitioning: l'applicazione e i dati sono suddivisi tra più nodi, ognuno specializzato in una parte del servizio. È trasparente agli utenti ma riduce la disponibilità in caso di guasto, a meno che non si combini con la clonazione. ![[Pasted image 20251111164816.png|center]]
>
> 
>L'unione di partizionamento e clonazione permette di ottenere sistemi sia scalabili che affidabili (RAPS), con degrado parziale anziché totale in caso di errore.
>![[Pasted image 20251111164836.png|center]]

### Virtualizzazione
> [!note]  
> La virtualizzazione è una tecnologia software che consente di astrarre le risorse fisiche di un sistema (CPU, memoria, disco) e renderle disponibili in forma virtuale. Ogni risorsa virtuale si comporta come una controparte fisica, permettendo di gestire in modo più flessibile e ottimizzato le infrastrutture IT, specialmente nelle server farm e nei data center.
> Attraverso essa, è possibile disaccoppiare le risorse fisiche dalle applicazioni, frazionare una risorsa fisica in più risorse virtuali e condividere la stessa risorsa tra più utenti, mantenendo l'illusione dell'uso esclusivo. Questo aumenta l'efficienza e riduce gli sprechi di capacità elaborativa.

L'insieme delle risorse virtuali usate da un'applicazione costituisce una macchina virtuale (VM), la cui esecuzione è gestita da uno hypervisor o virtual machine monitor. L'hypervisor può essere installato:
- direttamente sull'hardware (bare-metal), garantendo migliori prestazioni.
- sopra un sistema operativo host (hosted), offrendo maggiore flessibilità.

Ogni macchina virtuale può ospitare un proprio sistema operativo guest, anche diverso dall'host, consentendo di eseguire più ambienti software sulla stessa macchina fisica.

Ciò ha reso possibile la server consolidation, cioè la riduzione del numero di server fisici attraverso la concentrazione di più macchine virtuali su un unico hardware, con un uso medio delle risorse molto più efficiente.

>[!tip] Migrazione di VM
>Un ulteriore vantaggio della virtualizzazione è la migrazione delle VM, ossia la possibilità di spostare una macchina virtuale da un server fisico a un altro. Le tecniche di migrazione possono essere:
>- a freddo, con arresto e riavvio della VM, oppure
>- a caldo, che consente lo spostamento durante l'esecuzione, senza interruzione del servizio.    

### Cloud Computing
>[!note]  
>Il Cloud Computing è un paradigma tecnologico che consente l'accesso, tramite rete, a un insieme condiviso di risorse informatiche (server, storage, applicazioni, servizi) configurabili e disponibili su richiesta. Si basa sulla virtualizzazione e sul modello dell'utility computing, dove le risorse sono fornite come un servizio e pagate in base all'uso effettivo.  
>
>Il Cloud consente di accedere a risorse da qualsiasi dispositivo connesso, in modo flessibile e scalabile, riducendo i costi operativi. È particolarmente efficace per applicazioni con carichi di lavoro variabili e gestione di grandi volumi di dati.

Secondo il NIST, il Cloud Computing presenta cinque caratteristiche fondamentali:
- On-demand self-service: l'utente ottiene autonomamente risorse informatiche.
- Accesso alla rete onnipresente: fruizione tramite Internet e dispositivi standard.
- Indipendenza dalla localizzazione: l'utente non conosce l'ubicazione fisica delle risorse.
- Elasticità: le risorse possono essere aumentate o ridotte rapidamente.
- Monitoraggio dell'utilizzo: i costi dipendono dalle risorse effettivamente consumate.

> [!tip] Modelli di servizio
> I modelli di servizio principali sono tre:
>- IaaS (Infrastructure as a Service): fornitura di risorse hardware virtuali come server e storage, gestite dall'utente.
>- PaaS (Platform as a Service): fornitura di infrastruttura e piattaforme software (es. DBMS, API). L'utente gestisce solo le applicazioni.
>- SaaS (Software as a Service): fornitura diretta di applicazioni pronte all'uso accessibili via web.  
>
>Generalizzando, si parla anche di Everything as a Service (XaaS), estendendo il paradigma a vari livelli.

> [!tip] Modelli di deployment
> I modelli di deployment del Cloud sono quattro:
>- Private Cloud: infrastruttura dedicata a una singola organizzazione, con alta sicurezza e personalizzazione ma costi più elevati.
>- Community Cloud: condiviso tra organizzazioni con obiettivi comuni, buon equilibrio tra sicurezza e costo.
>- Public Cloud: offerto al pubblico da provider esterni, economico e scalabile ma con minore sicurezza.
>- Hybrid Cloud: combinazione di più modelli (public, private, community) che collaborano tramite tecnologie standard.

