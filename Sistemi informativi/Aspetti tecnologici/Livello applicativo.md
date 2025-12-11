>[!note]
>Le applicazioni informatiche si sono evolute da programmi scritti in linguaggi vicini alla macchina, con funzioni di base e dati salvati su file separati, fino a sistemi complessi basati su DBMS che consentono la condivisione di dati e l'uso di interfacce grafiche.
>
>Ad oggi le applicazioni sono organizzate in tre livelli logici:
>1. Presentazione (P): gestisce l'interfaccia utente.
>2. Logica applicativa (A): contiene le funzioni e le regole di business.
>3. Accesso ai dati (D): gestisce le informazioni e l'interazione con database o sistemi legacy.
>
>Il frontend riguarda l'interazione con l'utente, mentre la logica applicativa e accesso ai dati formano il backend, accessibile tramite API, che permettono l'integrazione con altri software.

Architetturalmente, le applicazioni possono essere:
- Monolitiche: tutti i livelli sono nello stesso software.
- Distribuite: I livelli sono separati e comunicano tramite interfacce. E possono essere sistemi chiusi o aperti.

Le applicazioni distribuite risultano più flessibili e scalabili, quindi oggi sono le più diffuse.

### Componenti funzionali
>[!note]
>Un sistema informativo è composto da più applicazioni modulari, ognuna con funzioni specifiche. Un modulo è un componente software autonomo con obiettivi funzionali precisi, e la suddivisione in moduli riflette spesso la struttura organizzativa aziendale.

La modularità migliora la manutenibilità e consente di modificare o sostituire singoli moduli senza compromettere l'intero sistema, mantenendo stabili le interfacce. È particolarmente utile nei sistemi aperti, dove è necessaria flessibilità per integrare altri sistemi o adattarsi ai cambiamenti.

>[!tip] Complessità e acquisizione
>Poiché i sistemi informativi sono molto complessi, è spesso inefficiente svilupparli da zero. Si preferisce quindi usare moduli già pronti e sviluppare solo le parti personalizzate. Tra i moduli più comunemente acquistati ci sono i sistemi ERP (Enterprise Resource Planning) e CRM (Customer Relationship Management), che rappresentano componenti tecnologici del livello applicativo.

### ERP
>[!note]
>L'ERP (Enterprise Resource Planning) è una suite software che integra e supporta le principali funzioni operative di un'azienda, coprendo l'intera catena del valore di Porter. Col tempo si sono sviluppate versioni verticali per specifici settori industriali e, più recentemente, si sono integrate tecnologie di intelligenza artificiale, machine learning e strumenti di analisi per la sostenibilità ambientale. Si caratterizzano per tre proprietà fondamentali:
>- Unicità dell'informazione: garantisce una sola rappresentazione dei dati valida per tutti i moduli.
>- Modularità: che consente di integrare o sostituire moduli in modo flessibile.
>- Prescrittività: Impone modelli di processo basati su best practice, costringendo l'azienda ad adattarsi a procedure standard ottimizzate.

La suite ERP comprende moduli che gestiscono attività operative come vendite, logistica, produzione, acquisti e risorse umane, oltre a moduli direzionali per la pianificazione e l'analisi dei dati. L'ERP core può essere esteso con sistemi aggiuntivi come PLM, SCM e CRM, che permettono di integrare la gestione del ciclo di vita del prodotto, della supply chain e delle relazioni con i clienti.

Essendo software COTS, gli ERP vengono adattati alle esigenze aziendali tramite parametrizzazione o personalizzazione del codice.

### CRM
>[!note]
>Il CRM (Customer Relationship Management) è una suite software che supporta le aziende nella gestione delle relazioni con i clienti, mettendo il cliente al centro della strategia aziendale. Serve a comprendere meglio i bisogni e i comportamenti dei clienti, migliorare l'efficacia dei canali di contatto e aumentare la fedelizzazione, con l'obiettivo di accrescere sia il valore del cliente per l'azienda sia quello dell'azienda per il cliente.
>
>CRM copre l'intero ciclo di vita del rapporto con il cliente, dal primo contatto fino al post-vendita. Tuttavia, la sua adozione risulta più utile nei settori con alta interazione con la clientela, relazioni di lungo periodo, ampia base di clienti e presenza di più canali di comunicazione. Rispetto ai moduli commerciali dell'ERP, il CRM offre funzioni più evolute per gestire la multicanalità, il supporto post-vendita, la fidelizzazione e l'analidi del comportamento dei clienti.
>
>Il CRM non è solo un software, ma una strategia aziendale volta a migliorare le relazioni con i clienti e ottimizzare le attività di marketing e vendita. Si compone di tre moduli principali: CRM operativo, CRM analitico e CRM collaborativo.

>[!tip] CRM operativo
>Il CRM operativo gestisce le interazioni quotidiane con i clienti e comprende tre aree: marketing, vendite e servizi post-vendita.
>Nel marketing, automatizza la gestione delle campagne, la generazione di liste clienti e le strategie di cross-selling e upselling, migliorando l'efficienza e tasso di conversione. Nelle vendite, include moduli per la gestione dei contatti, delle opportunità e del processo di vendita, supportando gli agenti lungo tutto il ciclo commerciale. Nei servizi ai clienti, offre strumenti come contact center, servizi web self-service e sistemi di call scripting per migliorare la qualità dell'assistenza e la fidelizzazione.

>[!tip] CRM analitico
>Il CRM analitico elabora e analizza i dati raccolti dal CRM operativo per identificare pattern di comportamento e preferenze dei clienti. Utilizza data warehouse e tecniche di data mining per produrre report, segmentazioni e previsioni. Le informazioni ottenute vengono poi restituite al CRM operativo per migliorare le campagne di marketing, strategie di vendita e servizio al cliente.

>[!tip] CRM collaborativo
>Il CRM collaborativo calcola e condivide indicatori aziendali come la redditività e la soddisfazione dei clienti. Questi dati sono utili per monitorare l'efficacia delle strategie CRM e valutare il ritorno degli investimenti.
### Data Warehousing
>[!note]
>Il Data Warehousing è una tecnologia che consente di raccogliere e integrare grandi quantità di dati provenienti da diverse fonti, per poi analizzarli a supporto delle decisioni tattiche e strategiche. A differenza dei sistemi operazionali (OLTP), i sistemi analitici (OLAP) si concentrano sull'osservazione del fenomeno nel tempo, offrendo una visione storica e multidimensionale dei dati.
>
>Un data warehouse è orientato ai fatti e alle entità. integrato, storico e persistente. La sua struttura si basa su un modello multidimensionale chiamato ipercubo, formato da fatti da analizzare, dimensioni e rappresentano i punti di vista come misure numeriche. Le dimensioni possono essere organizzate in gerarchie, permettendo diversi livelli di dettaglio nell'analisi.

L'architettura di un sistema di Data Warehousing comprende le sorgenti dati, il processo ETL (Extraction, Transformation, Loading) che estrae, pulisce e integra le informazioni, il data warehouse centrale e i data mart, che sono sezioni tematiche più specifiche. Esistono diversi modelli logici:
- MOLAP: utilizza basi di dati multidimensionali pure e molto veloci
- ROLAP: sfrutta basi relazionali più compatte ma meno performanti
- HOLAP: combina i due approcci precedenti

Le principali operazioni OLAP permettono di navigare e filtrare i dati in modi diversi: il drill-down e il roll-up aumentano e riducono il livello di dettaglio, mentre slice e dice consentono di selezionare porzioni specifiche dell'ipercubo.

Un ruolo importante è svolto dai metadati, che descrivono la struttura, le fonti e le trasformazioni dei dati, garantendo coerenza e tracciabilità.

>[!tip] Costruzione di un data warehouse
>La costruzione di un data warehouse è un processo iterativo, basato sulla realizzazione progressiva di ipercubi dedicati ai singoli fatti. Gli aggiornamenti vengono gestiti tramite procedure ETL, ma i costi elevati, i tempi lunghi e la necessità di manutenzione ne rappresentano i principali limiti.
>
>Le tendenze più recenti puntano all'integrazione con tecnologie big data, che permettono analisi più rapide e aggiornate in tempo reale.
### Data Mining
>[!note]  
>Il Data Mining è il processo di estrazione automatica di informazioni nascoste all'interno di grandi basi di dati, come i data warehouse. A differenza delle semplici analisi OLAP, che si basano sull'interazione diretta dell'utente, il data mining individua correlazioni, regole e schemi nascosti utili per supportare decisioni strategiche. Il processo si articola in sette fasi: selezione, pulizia, integrazione, trasformazione, analisi, valutazione e presentazione dei risultati. Le prime quattro fasi coincidono con quelle di costruzione del data warehouse, mentre le successive sono proprie del data mining.
>
>Le tecniche di data mining possono essere supervisionate o non supervisionate, a seconda che venga fornita o meno una variabile target di riferimento. Possono inoltre essere predittive, quando mirano a prevedere eventi futuri, o descrittive, quando si limitano a individuare pattern e regolarità nei dati. Tra le principali tecniche troviamo le regole associative, la classificazione e il clustering.

>[!tip] Regole associative
>Le regole associative identificano relazioni ricorrenti tra attributi diversi di un dataset e sono espresse nella forma $A\Rightarrow B$, dove $A$ è la condizione iniziale e $B$ la conseguenza. La loro validità è misurata tramite supporto (frequenza con cui la regola si verifica): $$\text{Supporto}=P(A,B)$$e confidenza (probabilità che B si verifichi dato A): $$\text{Confidenza}=P(A|B)= \frac{P(A,B)}{P(A)}$$
>Queste regole sono impiegate, ad esempio, nella market basket analysis o nei sistemi di raccomandazione per suggerire prodotti correlati agli acquisti precedenti.

> [!tip] Classificazione
> La classificazione assegna automaticamente elementi a classi predefinite utilizzando un modello addestrato su dati etichettati (training set). Il modello viene poi validato su un test set per verificarne l'accuratezza. Tra i classificatori più usati vi sono gli alberi di decisione, che organizzano gli attributi dei dati in una struttura gerarchica, consentendo di prevedere la classe di appartenenza di nuovi elementi. La qualità del modello viene misurata tramite indicatori come Precision e Recall: $$\begin{align*}
>\text{Precision}&= \frac{\text{Veri positivi}}{\text{Veri positivi}+\text{Falsi Positivi}}\\
>\text{Recall}&= \frac{\text{Veri positivi}}{\text{Veri positivi}+\text{Falsi Negativi}}
>\end{align*}$$Essi valutano rispettivamente l'accuratezza e la capacità di individuare correttamente gli elementi di una classe.

>[!tip] Clustering 
> Il clustering è una tecnica non supervisionata che raggruppa automaticamente elementi simili in cluster, senza conoscere in anticipo le classi di appartenenza. Gli elementi di uno stesso cluster sono tra loro simili, mentre quelli di cluster diversi lo sono il meno possibile. L'algoritmo più diffuso è il k-means, che partendo da centroidi iniziali identifica iterativamente i gruppi ottimali. Il clustering è applicato, ad esempio, nella segmentazione di mercato, dove i clienti vengono suddivisi in gruppi omogenei in base a reddito, professione o comportamento d'acquisto.

Nel CRM analitico, il data mining consente di comprendere meglio il comportamento dei clienti e di personalizzare le strategie aziendali.

### Process Mining
>[!note]  
>Il Process Mining è un approccio che consente di analizzare i processi aziendali reali a partire dai dati di monitoraggio generati durante la loro esecuzione. Serve a comprendere come i processi vengono effettivamente svolti, individuando scostamenti rispetto ai modelli previsti, inefficienze, colli di bottiglia e opportunità di miglioramento. Combina i dati dei log di eventi con i modelli di processo per supportare decisioni basate su evidenze oggettive.
>
>Gli elementi fondamentali del Process Mining sono i log di eventi e il modello di processo. I log registrano ogni evento con informazioni come Case ID, attività, timestamp, stato dell'attività e risorse coinvolte. Ogni log è composto da tracce, che rappresentano l'insieme ordinato delle attività di una singola istanza di processo. L'analisi delle tracce consente di individuare pattern, varianti e comportamenti ricorrenti.

Le tecniche principali del Process Mining sono tre:

1. Process Discovery, che costruisce automaticamente un modello di processo a partire dai log di eventi, senza informazioni a priori. Analizza le relazioni tra attività — successione, causalità, parallelismo e scelta — per generare un modello coerente con le esecuzioni osservate.
2. Conformance Checking, che confronta il modello teorico con i log reali per individuare deviazioni e misurare la fitness, cioè il grado di corrispondenza tra comportamento atteso e comportamento reale. Le deviazioni non sono sempre negative: possono segnalare errori o miglioramenti spontanei del processo.
3. Enhancement (Miglioramento dei processi), che utilizza i log per analizzare frequenze, tempi di esecuzione, varianti e percorsi più seguiti, individuando inefficienze e aree di ottimizzazione.

Il Process Mining supporta l'intero ciclo di vita di un processo: scoperta, verifica e miglioramento. Questo approccio permette alle organizzazioni di basare l'ottimizzazione dei processi su dati concreti e verificabili, migliorando efficienza, conformità e qualità operativa.

