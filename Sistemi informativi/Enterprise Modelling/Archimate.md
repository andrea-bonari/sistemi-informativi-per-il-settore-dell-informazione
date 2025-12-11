>[!note]
>Archimate è un linguaggio di modellazione grafica per l'Enterprise Architecture sviluppato da The Open Group. Archimate adotta un approccio a livelli e orientato ai servizi, suddividendo l'architettura in tre principali strati:
>- Business Layer
>- Application Layer
>- Technology Layer
>
>Questi strati si ispirano ai concetti del framework di Zachman, ma si concentrano su aspetti specifici legati alle esigenze di diversi stakeholder.

Gli stakeholder principali che consideriamo sono:
- Stakeholder di business: interessati alla definizione dei servizi da offrire, al loro target e alle funzioni aziendali coinvolte.
- Stakeholder applicativo: preoccupati degli applicativi da realizzare, dei dati da gestire e delle interazioni con i servizi.
- Stakeholder infrastrutturale: focalizzati sulle piattaforme tecnologiche necessarie per implementare i servizi.

>[!tip] Modello a servizi
>Archimate pone enfasi sulla distinzione tra interfaccia e implementazione. Questo approccio è illustrato in un esempio classico: un servizio di ristorazione, dove l'interfaccia comprende la sala e i camerieri, mentre l'implementazione corrisponde alla cucina e al personale. La relazione tra interfaccia e implementazione è definita come realisation relation, mentre la relazione tra componenti e servizi necessari è chiamata serving relation.
>
>![[Pasted image 20251021134239.png|center]]

>[!tip] Classificazione degli elementi
>I costrutti di Archimate Core sono organizzati sulla dimensione dei livelli e degli aspetti. Come sappiamo già i livelli sono Business, Application e Technology, mentre gli aspetti sono:
>- Passivo: struttura statica
>- Comportamentale: azioni del sistema
>- Attivo: soggetti che eseguono le azioni

### Elementi principali del modello

>[!note] Componenti
>I componenti sono gli elementi essenziali per descrivere la struttura di sistema e sono organizzati in base ai libelli e gli aspetti. Graficamente gli elementi attivi sono rappresentati da rettangoli semplici, quelli comportamentali da rettangoli con angoli arrotondati e quelli passivi da rettangoli con una banda superiore aggiunta.
>
>Inoltre ci possono essere delle decorazioni, che indicano il tipo specifico di comportamento (per esempio un icona ellittica per i servizi e un'icona freccia per i processi)

>[!note] Relazioni
>Le relazioni definiscono i collegamenti tra elementi e sono classificate in strutturali e dipendenza. Le relazioni strutturali sono:
>- Composizione: lega un elemento ai suoi componenti.
>- Realizzazione: indica che un elemento realizza un altro.
>- Assegnamento: associa un elemento a chi lo esegue.
>
>Le relazioni di dipendenza sono invece:
>- Accesso: un elemento utilizza un altro.
>- Serving: collega un servizio a un elemento che lo utilizza.

Gli elementi principali del livello business sono:
- Servizio business
- Funzione business
- Oggetto passivo

![[Pasted image 20251021135751.png|center]]
>[!example]
>Un servizio business ("Document creation") è realizzato da una funzione business ("Write Answer"), che utilizza un oggetto passivo (documento testuale).
>

Gli elementi principali del livello applicazione sono:
- Servizio applicativo
- Funzione applicativa
- Oggetto dati
- Componente applicativo

![[Pasted image 20251021140007.png|center]]
>[!example]
>Un servizio applicativo ("Document creation") è realizzato da una funzione applicativa ("Editing"), che utilizza un oggetto dati ("Word Document") e viene eseguita da un componente applicativi (programma di elaborazione testi)

Gli elementi principali del livello tecnologico sono:
- Servizio tecnologico
- Funzione tecnologica
- Nodi
- Artefatti

![[Pasted image 20251021140246.png|center]]
>[!example]
>Un servizio tecnologico ("Database server") è realizzato da una funzione tecnologica ("SQL server") e viene eseguito su un nodo (un server con SO e software di condivisione file).

>[!tip] Nodi
>I nodi rappresentano le infrastrutture hardware/software a diversi livelli di dettaglio:
>- Livello alto: il nodo è considerato un unico elemento.
>- Livello medio: il nodo include componenti raggruppati.
>- Livello dettagliato: Il nodo mostra tutti componenti.

