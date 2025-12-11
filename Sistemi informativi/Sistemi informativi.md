>[!summary]
>Nelle aziende moderne, il sistema informativo (che gestisce i dati e processi) è diventato cruciale per la competitività, poiché la capacità di operare dipende da funzionalità tecnologiche. L'evoluzione delle strategie aziendali richiede modifiche in hardware, software e infrastrutture, con Internet e il Web come fondamenti per costruire un'economia basata sull'informazione. Le organizzazioni devono integrare informazioni eterogenee da fonti distribuite, rendendo necessario gestire grandi volumi di dati.
>
>La progettazione di sistemi informativi deve affrontare complessità progettuale e organizzativa, dovute a diversi formati di dati, reti e processi distribuiti. La soluzione attuale è il sistema informativo distribuito, che permette collaborazione tra organizzazioni mantenendo autonomia, a differenza dei sistemi centralizzati. Questi sistemi devono gestire sfide come il Big Data e il Cloud Computing, integrando tecnologie eterogenee.
>
>Governare questa complessità richiede metodi e strumenti specifici per supportare l'organizzazione nel gestire processi interni ed esterni, al fine di ottimizzare l'efficienza e la sinergia tra entità

### Dati e informazioni
>[!note]
>Nel contesto dei sistemi informativi, è fondamentale distinguere tra dato, informazione, conoscenza e saggezza attraverso la piramide DIKW (Data - Information - Knowledge - Wisdom), dove:
>- Dato: rappresenta la base, costituito da fatti o misure, dotati di tipo e unità di misura. I dati sono numerosi e granulari, ma non hanno senso senza contesto.
>- Informazione: deriva dai dati e aggiunge contesto per rendergli utili. È l'output di interrogazioni su dati organizzati.
>- Conoscenza: si ottiene integrando informazioni con esperienza, permettendo di interpretare la realtà. Non è trasferibile facilmente, richiede contesto e interpretazione.
>- Saggezza: applica conoscenza per guidare decisioni. È l'azione più adatta in un momento specifico.
>
>![[Pasted image 20250915102721.png|center]]
>

La piramide evidenzia una stratificazione a livelli, dove ogni livello è costruito su quello inferiore, ma ha meno estensione (più sintetico e astratto).

La gestione automatica dei dati è altamente automatizzata (tramite l'uso di database), mentre informazione, conoscenza e saggezza richiedono sempre maggiore intervento umano. L'obiettivo è trasformare dati in azioni utili, guidando decisioni attraverso l'esperienza e la sintesi.

### Le organizzazioni
>[!note]
>L'uso di sistemi informativi richiede la comprensione delle risorse e dei processi aziendali per creare valore. Le risorse sono elementi fondamentali con cui un'azienda opera, sia materiali che immateriali, e si suddividono in risorse esterne (ambiente, mercato, clienti) e risorse interne (scambio, struttura, gestione).
>
>I processi sono le attività che un'azienda svolge per gestire il ciclo di vita delle risorse, raggiungendo risultati misurabili. Essi si classificano in base a modelli come la piramide di Anthony o La catena del valore di Porter.
>
>L'obiettivo dei sistemi informativi è trasformare i dati in informazioni utili, gestendo le risorse e i processi per supportare decisioni strategiche, ottimizzare operazioni e migliorare l'efficienza aziendale. La gestione esplicita e automatizzata dell'informazione è cruciale per rendere i processi più efficaci e replicabili.

L'informazione, come risorsa immateriale, ha caratteristiche uniche: è intangibile, non deperibile e auto-rigenerante. La sua gestione coinvolge attività come la creazione, acquisizione, elaborazione, archiviazione, trasmissione e presentazione, che possono essere gestite in modo implicito (basato sull'esperienza) o esplicito (con o senza supporto IT).

>[!tip] Piramide di Anthony
>La piramide di Anthony è un modello gerarchico che suddivide i processi aziendali in tre livelli, corrispondenti alle diverse funzioni organizzative:
>- Livello operativo: Gestisce le attività quotidiane, direttamente legate alle operazioni concrete.
>- Livello programmazione e controllo: Gestisce le attività tattiche, come la pianificazione e il controllo delle risorse.
>- Livello pianificazione strategica: Gestisce decisioni a lungo termine, orientate alla definizione di obiettivi e politiche aziendali.
>
>La piramide di Anthony è utile per comprendere come i processi aziendali siano organizzati in una struttura gerarchica, con il supporto dei sistemi informativi per automatizzare e ottimizzare le attività dei livelli inferiori.
>
>![[Pasted image 20250915115547.png|center]]

>[!tip] Catena del valore di Porter
>La catena del valore di Porter suddivide le attività aziendali in due categorie:
>- Attività primarie: funzioni direttamente legate alla creazione di valore per il cliente.
>- Attività secondarie: funzioni di supporto che facilitano le attività primarie.
>
>La catena del valore di Porter è un modello che evidenzia come le attività primarie e secondarie interagiscono per generare profitto, con un focus su efficienza e differenziazione.
>
>![[Pasted image 20251021100859.png|center]]
### Definizione di sistema informativo
>[!note]
>Un sistema informativo (SI) è un insieme di dati, processi e persone, descritti da delle regole. In questo sistema i dati alimentano i processi, che si basano generalmente su un'infrastruttura tecnologica e sono eseguiti da persone.
>
>Il sistema è alimentato da eventi (trasformati in dati) e a sua volta genera informazioni. Talvolta tramite un meccanismo di retroazione le informazioni prodotte possono diventare eventi.
>
>![[Pasted image 20250915102309.png|center]]

### Classificazione di SI
>[!note]
>La complessità dei processi aziendali richiede sistemi informativi diversificati, classificabili anche in base alla piramide di Anthony in sistemi operazionali e sistemi decisionali:
>- Sistemi operazionali: Gestiscono le attività quotidiane utilizzando dati strutturati e focalizzandosi su processi operativi o di controllo.
>- Sistemi decisionali: Supportano decisioni strategiche, analizzando dati storici e aggregati tramite strumenti come data warehouse, OLAP, business intelligence e DSS.

Entrambi i tipi di sistemi hanno dei rispettivi dati, che possono essere in alcuni casi automatizzati:
- Dati operativi: dettagliati, strutturati e provenienti dall'interno.
- Dati strategici: aggregati, macroeconomici o relativi a budget, spesso provenienti dall'estero.

>[!tip] Sistemi OLTP e Sistemi OLAP
>I sistemi OLTP gestiscono transazioni brevi ma frequenti, utilizzando dati dettagliati e attuali, memorizzati in basi di dati relazionali. Le operazioni si concentrano su `INSERT`, `UPDATE` e `DELETE`, e seguono le proprietà ACID (Atomiche, Consistenti, Isolate, Durevoli). La loro performance è misurata in base al numero di transazioni al secondo.
>
>I sistemi OLAP si focalizzano sull'analisi di dati storici e aggregati, organizzati in schemi multidimensionali. Le interrogazioni sono complesse e richiedono aggregazioni, con un focus su query di sola lettura. L'efficienza è valutata in base al tempo di risposta.

>[!tip] Intelligenza Artificiale
>L'adozione dell'intelligenza artificiale ha permesso di gestire dati non strutturati e processi decisionali complessi, riducendo la dipendenza umana e ampliando l'automazione anche in contesti strategici.

### IT e componenti di un SI
>[!note]
>La relazione tra organizzazione e tecnologia IT è una dinamica interazione che influisce reciprocamente su entrambi i livelli. Questa relazione non è lineare, ma piuttosto bidirezionale: le esigenze interne (requirements pull) guidano l'adozione di soluzioni tecnologiche, mentre l'arrivo di nuove tecnologie (technology push) può plasmare strategie, processi e struttura organizzativa. Fattori come decisioni strategiche, cultura aziendale e contesto esterno ne determinano il percorso.

Il sistema informativo è un insieme di componenti tecnologici (hardware, software, dati, servizi esterni) e aspetti non tecnologici (accettazione da parte degli utenti, strategia aziendale). La sua progettazione richiede un approccio intersettoriale, integrando tecnologia, organizzazione e processi.

Per garantire coerenza, l'Enterprise Architecture (EA) fornisce una visione strutturata, allineando obiettivi aziendali, aspetti organizzativi e tecnologie.

La progettazione di sistemi informativi è un processo complesso, che coinvolge architettura, componenti essenziali (database, applicazioni, infrastruttura) e una pianificazione attenta. L'obiettivo è creare un sistema che soddisfi esigenze attuali e future, sostenendo crescita e innovazione.