>[!note]  
>Le tecnologie a livello di piattaforma rappresentano l'infrastruttura di base di un sistema informativo e forniscono gli strumenti, i servizi e le risorse necessari per sviluppare, implementare, integrare e gestire applicazioni e dati. Esse costituiscono la spina dorsale del sistema e vengono classificate in categorie differenti in base al loro ruolo.

### Architetture di integrazione
>[!note]  
>Le architetture di integrazione rappresentano l'insieme di soluzioni tecniche e organizzative che permettono di coordinare e connettere le diverse parti di un sistema informativo, sia all'interno dell'organizzazione sia tra organizzazioni diverse. Esse mirano a garantire la collaborazione tra i moduli applicativi, la condivisione dei dati e la continuità dei processi aziendali.

I sistemi informativi sono composti da applicazioni e dati governati da regole aziendali che si concretizzano in processi. Tuttavia, lo sviluppo incrementale e disomogeneo dei sistemi porta spesso alla creazione di applicazioni a silos, ossia moduli isolati che non comunicano tra loro. Questa frammentazione provoca inefficienze operative, ridondanza dei dati, difficoltà di gestione e ostacola la cooperazione tra funzioni aziendali.

L'integrazione risulta necessaria non solo all'interno dell'organizzazione, ma anche nei rapporti con sistemi esterni (clienti, fornitori, partner), spesso sviluppati con tecnologie e modelli differenti. Le architetture di integrazione rispondono quindi al bisogno di un flusso informativo continuo e coerente, assicurando interoperabilità, coerenza dei dati e coordinamento tra processi intra-organizzativi e inter-organizzativi.

### Livelli applicativi e tecniche di integrazione
>[!note]  
>Le tecniche di integrazione permettono di collegare e coordinare applicazioni e dati all'interno di un sistema informativo, intervenendo su diversi livelli logici: dati, logica applicativa e presentazione. Ogni approccio presenta vantaggi e limiti, a seconda dell'architettura software e delle tecnologie adottate.

>[!tip] Integrazione delle basi di dati
>Nell'integrazione a livello dati, l'obiettivo è garantire un flusso informativo continuo e coerente tra le diverse funzioni aziendali, rendendo i dati accessibili come se provenissero da un'unica sorgente condivisa. Un middleware si occupa di mantenere la congruenza dei dati tra database diversi e di uniformarne formato e semantica. Le difficoltà principali riguardano la rappresentazione (modi diversi di strutturare la stessa informazione), la struttura (ordine dei campi o modelli gerarchici differenti), la presentazione (formati diversi per la stessa informazione) e la semantica (diverso significato o unità di misura dei dati).
>
>![[Pasted image 20251111120455.png|center]]

>[!tip] Integrazione a livello applicativo
>L'integrazione a livello di logica applicativa consente la comunicazione diretta tra applicativi. È più semplice nei sistemi con architetture aperte e modulari, mentre risulta complessa o impraticabile in software monolitici o con architetture chiuse.
>
>![[Pasted image 20251111120538.png|center]]

>[!tip] Integrazione a livello client
>L'integrazione a livello di presentazione si basa sulla modifica dei client (front-end) per consentire l'accesso alle funzioni esposte dai server di altre applicazioni. Questa soluzione può risultare utile quando non è possibile intervenire sui livelli più profondi, ma comporta rischi di coerenza e problemi tecnici legati a linguaggi, connessioni simultanee e gestione corretta delle sequenze operative.
>
>![[Pasted image 20251111120558.png|center]]

### Modelli di integrazione delle applicazioni
>[!note]  
>I modelli di integrazione delle applicazioni descrivono diverse modalità per collegare più sistemi informativi, interni o esterni a un'organizzazione, con l'obiettivo di garantire interoperabilità e coordinamento.

>[!tip] Architettura punto-a-punto
>L'architettura punto-a-punto collega direttamente le applicazioni tramite connettori o API personalizzate. Ogni sistema comunica in modo indipendente con gli altri, senza un nodo centrale. Sebbene semplice da implementare in contesti ridotti, questo modello non è scalabile: il numero di connessioni cresce quadraticamente ($n^{2}$) e ogni modifica richiede interventi multipli, rendendo la manutenzione complessa.

>[!tip] Architettura hub-and-spoke  
>L'architettura hub-and-spoke introduce un hub centrale che gestisce la comunicazione tra applicazioni collegate tramite adattatori (spoke). L'hub si occupa di indirizzamento, trasformazione dei dati e coordinamento, riducendo le interfacce a $n$. Ciò facilita l'aggiunta o la sostituzione di componenti, ma concentra la complessità e la logica applicativa nel nodo centrale.

>[!tip] Business Process Management System  
>Con l'uso di un Business Process Management System (BPMS) o Workflow component, l'integrazione è guidata da processi formalizzati che gestiscono lo scambio di informazioni e lo stato di avanzamento tra applicazioni. Il BPMS consente di separare la logica di processo dalla logica applicativa, semplificando modifiche e riorganizzazioni. Può essere integrato in suite ERP o operare come componente esterno, ad esempio tramite BPMN.

>[!tip] Architetture orientate ai servizi
>Le architetture orientate ai servizi (SOA) rappresentano un paradigma basato su servizi modulari accessibili tramite Internet. Ogni servizio incapsula una funzionalità di business, è indipendente e interagisce attraverso interfacce standard descritte in WSDL e comunicate tramite SOAP o, nelle versioni leggere, con lo stile REST (HTTP + XML/JSON).
>  
>Il funzionamento delle SOA si fonda sul rapporto tra Service Provider, Service Registry e Service Requestor: i provider pubblicano i servizi, i registry li catalogano e i requestor li ricercano e invocano dinamicamente. L'accordo tra le parti è definito da un Service Level Agreement (SLA), che specifica parametri di qualità (QoS) come tempi di risposta, disponibilità e costi operativi.

La composizione e orchestrazione di servizi consente di combinare più servizi elementari per costruire funzionalità complesse, tipiche di applicazioni come l'e-commerce. L'orchestrazione regola la sequenza e le modalità di invocazione dei servizi. In contesti inter-organizzativi, la flessibilità dinamica permette di selezionare in tempo reale i fornitori più adatti tramite Service Broker, garantendo adattabilità e continuità operativa anche in scenari di cambiamento rapido.