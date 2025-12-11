> [!note]  
> La sicurezza nei sistemi informativi consiste nell'insieme di misure organizzative e tecnologiche che garantiscono a ogni utente autorizzato l'accesso esclusivo ai servizi e alle risorse a lui destinati, assicurando che dati e applicazioni siano protetti da utilizzi non autorizzati. Il sistema viene interpretato come un insieme di entità che cooperano per obiettivi comuni, e la sicurezza definisce le regole che permettono a questa cooperazione di avvenire in modo affidabile e controllato, mantenendo la fiducia negli scambi informativi.

La definizione ISO della sicurezza pone l'attenzione sulle proprietà che un sistema deve preservare: l'integrità, che impedisce modifiche non autorizzate o accidentali ai dati; l'autenticità, che garantisce l'identificazione corretta delle entità coinvolte e l'impossibilità di negare la provenienza delle informazioni; la riservatezza, che tutela i dati da accessi non consentiti e, quando riguarda le persone, si estende alla privacy; la disponibilità, che assicura agli utenti autorizzati l'accesso alle informazioni nei tempi e nei modi previsti.

>[!tip] Sicurezza come requisito  
>La sicurezza è un requisito non funzionale dell'intero sistema informativo e deve essere integrata in tutte le fasi di progettazione e sviluppo, così da permettere non solo la prevenzione di intrusioni e abusi (protezione attiva), ma anche la capacità di reagire e limitare gli effetti di attacchi riusciti (protezione reattiva).
### Minacce, violazioni, vulnerabilità e attacchi
>[!note]  
>Le minacce ai sistemi informativi possono essere fisiche, logiche o accidentali. Le prime riguardano danni agli impianti o infrastrutture, le seconde colpiscono informazioni e risorse attraverso sottrazioni, alterazioni o accessi nascosti, mentre le terze nascono da errori di configurazione o malfunzionamenti. Le violazioni derivano dallo sfruttamento delle vulnerabilità presenti nei sistemi e possono impedire l'uso legittimo delle risorse, come nel caso della negazione del servizio.
>  
>Una vulnerabilità indica un punto debole su cui un exploit può fare leva per causare comportamenti anomali. La maggior parte deriva da scarsa qualità progettuale, bachi software, testing insufficiente o carenze nei controlli fisici e logici. Gli attacchi consistono in azioni malevole che colpiscono basi di dati, infrastrutture e reti con l'obiettivo di rubare, alterare o distruggere informazioni, con particolare rilevanza nei sistemi critici.

A livello di rete sono frequenti attacchi basati sull'intercettazione del traffico, sull'impersonificazione degli agenti, sulla deviazione invisibile delle comunicazioni o sull'intasamento dei servizi. A livello applicativo emergono tecniche come il phishing, l'uso di malware nelle sue diverse forme, l'impiego di backdoor e spyware e gli attacchi zero-day, che sfruttano vulnerabilità non ancora note ai produttori e quindi prive di correzioni disponibili.

Le minacce possono provenire sia da soggetti esterni sia da utenti interni che sfruttano i propri privilegi per accedere ad aree non autorizzate. Per questo l'attenzione va posta su tutti i punti di accesso della rete e sugli operatori che hanno controllo delle infrastrutture.

### Crittografia per la protezione dei dati
>[!note]  
>La crittografia consiste nella trasformazione di un messaggio in una forma cifrata tramite un algoritmo e una o più chiavi, la cui segretezza è l'elemento essenziale per garantire riservatezza e autenticità. L'efficacia della protezione dipende dalla lunghezza della chiave e dalla vastità dello spazio delle combinazioni possibili, che rende difficile agli attaccanti recuperare la chiave e decifrare i dati.
> 
>   
>Gli algoritmi crittografici si dividono in due categorie:
>- Chiave simmetrica: utilizzano un'unica chiave condivisa e comprendono metodi come DES, 3-DES e AES.
>- Chiave asimmetrica: basati su coppie di chiavi pubblica e privata e fondati su problemi matematici complessi, tra cui gli algoritmi RSA, Diffie-Hellman ed El-Gamal.

>[!tip] Crittografia simmetrica  
>La crittografia simmetrica utilizza un'unica chiave segreta condivisa tra mittente e destinatario, che deve essere cambiata spesso per evitare che un attaccante, pur intercettando i messaggi cifrati, riesca a ricavarne la chiave tramite crittoanalisi. Le due tecniche fondamentali sono la sostituzione, che applica una mappatura fissa o controllata dalla chiave alle lettere del testo, e la trasposizione, che permuta le posizioni dei caratteri secondo uno schema determinato. Gli algoritmi moderni combinano più passaggi di sostituzione e permutazione attraverso strutture come S-box e P-box, fino a ottenere cifrature complesse come l'AES, che opera su blocchi da 128 bit e utilizza chiavi lunghe per resistere agli attacchi a forza bruta.
>
> I principali limiti della crittografia simmetrica riguardano la gestione della chiave, che deve essere distribuita tramite un canale sicuro e aggiornata frequentemente, mentre il suo vantaggio principale è la rapidità delle operazioni di cifratura e decifratura, ulteriormente migliorabile con implementazioni hardware dedicate.

>[!tip] Crittografia asimmetrica
>La crittografia asimmetrica si basa su una coppia di chiavi correlate per ciascun agente: una chiave pubblica, liberamente distribuibile, e una chiave privata, che deve rimanere segreta. La sicurezza deriva dal fatto che ciò che viene cifrato con una chiave può essere decifrato solo con l'altra, senza che sia possibile ricavare la chiave privata dalla pubblica. Questo elimina la necessità di condividere segreti attraverso la rete e consente di garantire riservatezza cifrando con la chiave pubblica del destinatario, oppure autenticità cifrando con la chiave privata del mittente.
>
>Le due proprietà possono essere combinate applicando una doppia cifratura, così da ottenere contemporaneamente autenticazione e protezione del contenuto. Gli algoritmi asimmetrici sfruttano funzioni matematiche semplici da eseguire ma difficili da invertire, come la fattorizzazione di grandi numeri nei casi di Diffie-Hellman e RSA. Il limite principale di questi metodi è la lentezza computazionale, motivo per cui nella pratica la cifratura asimmetrica viene usata soprattutto per proteggere lo scambio delle chiavi, mentre la cifratura effettiva dei messaggi è affidata ad algoritmi simmetrici più veloci.
>
>Di seguito si illustra il funzionamento di RSA:
>1. Si scelgono due numeri primi $P$ e $Q$ di valore elevato.
>2. Si calcola $N=P\times Q$ e $Z=(P-1)\times(Q-1)$.
>3. Si scelgono due valori $E$ e $D$, dove $E<N$ va scelto tra i numeri che non hanno fattori comuni con $Z$, mentre $D$ deve soddisfare $(E\times D)\mod Z=1$.
>4. Le chiavi pubbliche e private sono definite come $K_{p}=(E,N)$, $K_{pr}=(D,N)$.

>[!tip] Funzioni di Hash e firma digitale
>Le funzioni di hash servono a garantire l'integrità dei messaggi: trasformano un messaggio di qualsiasi lunghezza in un digest di lunghezza fissa. Questo digest ha tre proprietà fondamentali: messaggi uguali producono lo stesso digest, messaggi diversi producono digest diversi, e dal digest non si può risalire al messaggio originale. In pratica, il mittente calcola il digest del messaggio e lo invia insieme al messaggio stesso; il destinatario ricalcola il digest dal messaggio ricevuto e, se coincide con quello ricevuto, il messaggio è integro.
>
>Per proteggere ulteriormente l'impronta digitale dagli attacchi, si usa la firma digitale. Qui il digest viene crittografato con la chiave privata del mittente e allegato al messaggio. Il destinatario, usando la chiave pubblica del mittente, decodifica la firma e confronta il digest originale con quello calcolato, verificando così autenticità e integrità. La firma digitale è unica per ogni documento, non può essere copiata su altri messaggi e garantisce anche il non ripudio, dimostrando che i dati non sono stati modificati dopo la firma.

Per usare la crittografia è necessario possedere e gestire correttamente le chiavi, un processo chiamato gestione delle chiavi, che include generazione, conservazione e scambio delle chiavi. Le chiavi devono essere generate da chi le utilizza, preferibilmente come sequenze casuali tramite generatori di numeri casuali di alta qualità. La conservazione può avvenire in software, cifrando le chiavi in file protetti da password, oppure in hardware, usando dispositivi rimovibili o “attivi” come smart card e token USB, capaci anche di eseguire autonomamente operazioni crittografiche.

Lo scambio delle chiavi è critico soprattutto nella crittografia simmetrica, perché la compromissione della chiave annulla la sicurezza. Può avvenire tramite canali separati (Out-Of-Band), tramite cifratura della chiave segreta con la chiave pubblica del destinatario, o tramite una terza parte fidata (key distribution center). Per le chiavi pubbliche, invece, il problema non è mantenerle segrete ma associarle correttamente al loro proprietario, cosa che avviene tramite certificati digitali (PKC), spesso secondo lo standard X.509v3.

Le PKI (Public Key Infrastructure) gestiscono la generazione, emissione, distribuzione e revoca dei certificati. L'utente richiede un certificato a una Certification Authority (CA), che verifica l'identità e può usare una Registration Authority (RA) per confermare le credenziali. I certificati vengono conservati in repository accessibili agli utenti e contengono informazioni sulla chiave pubblica, il titolare e la validità; la loro integrità è garantita dalla firma digitale della CA. Per fidarsi di un certificato, oltre a verificarne la firma, occorre controllare che la CA emittente sia affidabile.

I certificati digitali e le chiavi pubbliche trovano applicazione nello scambio sicuro di email, nel controllo remoto, nell'accesso ad hardware di rete, nelle applicazioni e-commerce, nei siti web sicuri e per verificare software firmato.

### Gestione degli utenti e controllo accessi
>[!note]
>![[Pasted image 20251211130644.png|center]]
>L'autenticazione serve a riconoscere con certezza un utente prima di permettergli di accedere a sistemi, dati o applicazioni protette. Per autenticare un agente si possono usare tre tipi di fattori: qualcosa che l'utente conosce (password), qualcosa che possiede (carta magnetica, token) o qualcosa che è (caratteristiche biometriche come impronta digitale o retina). L'autenticazione semplice si basa su username e password, mentre quella robusta può usare sistemi OTP, challenge-response, smart card o biometria.
>
>L'autenticazione a più fattori (MFA) aumenta la sicurezza combinando almeno due fattori differenti, come “qualcosa che sai” più “qualcosa che hai”. La 2FA, molto diffusa, utilizza di solito password e un codice numerico temporaneo generato da app o token (OTP). Esiste anche la 3FA, più rara, che combina tutti e tre i fattori, come nel SPID di livello 3. L'uso della 2FA protegge da attacchi come brute force, osservazione diretta o smudge e riduce la necessità di rispondere a domande di sicurezza. È consigliata per la maggior parte dei servizi online importanti, sebbene non sempre obbligatoria.

L'autorizzazione serve a stabilire quali operazioni un utente autenticato può effettivamente compiere sui dati o sulle risorse di un sistema. Il controllo degli accessi verifica se un agente ha diritto di leggere, scrivere o eseguire determinate funzioni, e può essere gestito dal sistema operativo, dal DBMS o da servizi specifici di sicurezza. Nei DBMS sicuri, il controllo deve considerare la granularità degli oggetti (tabelle, colonne, tuple, viste), le correlazioni semantiche dei dati, la protezione dei metadati e il ciclo di vita dei dati. Le regole di accesso definiscono chi può fare cosa, in quali condizioni e con quali privilegi.

Le regole si basano su quattro elementi principali: soggetto (utente, gruppo, ruolo o applicazione), oggetto (risorsa da proteggere), diritto (tipo di accesso) e vincoli (restrizioni basate sul contenuto o sul contesto). I vincoli permettono di applicare controlli basati sulla semantica dei dati, per esempio consentendo a un dipendente di leggere solo il proprio stipendio. Le regole possono essere gestite con politiche discrezionali (DAC), dove il proprietario dei dati decide gli accessi, o mandatorie (MAC), utilizzate per dati sensibili con livelli di classificazione e clearance. Nei sistemi MAC, le regole fondamentali sono “No-Read-Up” e “No-Write-Down”, che impediscono flussi di dati tra soggetti con livelli di sicurezza diversi.

Il controllo basato sul ruolo (RBAC) o sul contenuto permette ulteriori filtraggi mirati, ad esempio limitando l'accesso ai dati di un reparto specifico o solo a determinati campi di una tabella. Nei sistemi MAC, le informazioni vengono gestite tramite etichette di classificazione affidabili e integrate nella Trusted Computing Base del DBMS, garantendo protezione anche in ambienti multi-livello.

>[!tip] DBMS DAC
>Nei DBMS che adottano il modello DAC (Discretionary Access Control), il controllo degli accessi può basarsi sia sul nome della tabella e dei suoi attributi sia sul contenuto dei dati. Le autorizzazioni possono essere definite nel profilo utente o associate agli oggetti e specificate tramite comandi del DBMS o del sistema operativo. Per esempio, la clausola `GRANT` permette di concedere a un utente diritti come `INSERT` o `SELECT` su una tabella, oppure su una vista che limita i dati visibili in base a criteri specifici (ad esempio solo gli impiegati di un certo reparto).
>
>Un'altra tecnica è la query modification, dove la query dell'utente viene automaticamente adattata per rispettare le regole di accesso; ad esempio, se un utente può leggere solo gli stipendi inferiori a 1500, la query originale viene modificata dal DBMS per filtrare automaticamente i dati.
>
>Il modello DAC può essere esteso a sei componenti includendo la regola di propagazione dei privilegi, che stabilisce se e come i privilegi possono essere concessi ad altri utenti, con possibilità di limitazioni o revoche. I sistemi DAC possono anche basarsi sui ruoli aziendali, associando le autorizzazioni a ruoli come manager o impiegato invece che ai singoli utenti. Questo facilita la gestione e manutenzione delle regole di accesso, rendendole coerenti con la struttura organizzativa e memorizzandole in archivi di sistema consultabili al momento della decisione di accesso.

>[!tip] MAC DBMS
>Nei DBMS che adottano il modello MAC (Mandatory Access Control), i dati vengono gestiti in tabelle multilivello, con classificazioni diverse per attributi, tuple e intere relazioni. La polinstanziazione è il meccanismo principale: esistono più copie fisiche della stessa tabella, ciascuna corrispondente a un livello di sicurezza, in modo da prevenire inferenze illecite. La Trusted Computing Base (TCB) media tutti gli accessi tramite componenti affidabili (Reference Monitor).
>
>Ogni tupla di una Multi-Level Relation (MLR) ha un attributo di classificazione e gli attributi stessi hanno etichette di sensitività. I soggetti possono leggere solo le istanze al proprio livello o inferiori, mentre la scrittura avviene creando polistanziazioni se necessario, evitando inferenze non autorizzate o negazioni di servizio.
>
>Nelle istanze multilivello, valori nulli possono rappresentare dati assenti o dati di livello superiore non visibili all'utente. Per evitare inferenze, si possono inserire valori fittizi compatibili con il livello di accesso, oppure mantenere tuple separate con la stessa chiave primaria ma con differenti classificazioni. In questo modo, le istanze a livelli superiori contengono l'intero insieme dei dati, mentre quelle a livelli inferiori presentano solo le informazioni consentite, preservando la sicurezza e l'integrità dei dati sensibili.
### Elementi di cybersecurity
>[!note]
>Il cyberspace è l'ambiente digitale e fisico in cui avvengono le attività su Internet, esposto a rischi crescenti per la diffusione globale e immediata di azioni malevoli. La cybersecurity riguarda le misure fisiche, logiche e organizzative necessarie a proteggere sistemi e informazioni da attacchi che mirano a furti, frodi, sabotaggi o ransomware. La vulnerabilità nasce spesso dal fatto che reti e sistemi sono progettati più per l'usabilità che per la sicurezza, e può essere sfruttata da criminali, hacker o terroristi per ottenere vantaggi illeciti.
>
>Gli attacchi possono colpire qualsiasi organizzazione, dalle multinazionali alle PMI, queste ultime particolarmente vulnerabili. Le contromisure comprendono piani strategici nazionali, misure organizzative, formazione e sensibilizzazione, e regolamentazioni per proteggere le vittime. Sta crescendo il fenomeno del “Crime-as-a-Service”, un mercato di strumenti e competenze informatiche criminali vendute a gruppi o individui senza know-how tecnico, aumentando le capacità offensive di chiunque.
>
>Affrontare queste minacce richiede cooperazione internazionale su tre fronti: sicurezza informatica, con strutture di alert e contrasto agli attacchi; governance di Internet, secondo un modello multi-stakeholder che non sia controllato solo da privati o imprese; e tutela della libertà di espressione, promuovendo accesso universale e cultura digitale sicura. Le sfide della cybersecurity sono quindi non solo tecnologiche, ma anche sociali, economiche e organizzative.

>[!tip] Approccio Zero Trust
>L'approccio Zero Trust nasce dal principio che nessuna entità, interna o esterna alla rete aziendale, può essere considerata affidabile di default. Ogni accesso a sistemi e applicazioni deve essere strettamente necessario e continuamente verificato. Questo modello è diventato rilevante con la diffusione del cloud, dell'informatica distribuita e dello smart working, dove il concetto tradizionale di perimetro di rete non è più valido. L'accesso è basato sul privilegio minimo e tutte le attività degli utenti e dei dispositivi vengono costantemente monitorate per individuare eventuali comportamenti sospetti. L'implementazione può avvenire attraverso architetture e strumenti specifici come Zero Trust Architecture, Zero Trust Network Access e Zero Trust Secure Web Gateway. I principi operativi includono visibilità e controllo su ambienti cloud e dispositivi, segmentazione delle reti e delle applicazioni, autenticazione multifattore, controllo granulare degli accessi, riduzione dell'uso di VPN e firewall tradizionali e l'adozione di tecniche di deception per rilevare tempestivamente attaccanti e minacce. Zero Trust rappresenta quindi un paradigma di sicurezza continuo e dinamico, adatto a infrastrutture moderne e a scenari di lavoro da remoto.

### Meccanismi di sicurezza infrastrutturali
>[!note]
>Le contromisure a livello di architettura fisica per proteggere un sistema informativo includono la configurazione sicura di sistemi operativi, client e server, insieme all'applicazione di politiche di autenticazione, controllo degli accessi e log delle attività. Gli strumenti principali sono firewall e proxy server, che filtrano il traffico tra reti fidate e reti esterne, impedendo accessi non autorizzati, e i sistemi di Intrusion Detection, che monitorano eventi di rete e di sistema per individuare tentativi di compromissione della confidenzialità, integrità o disponibilità dei dati.

>[!tip] Firewall
>Un firewall è un insieme di componenti e servizi finalizzati a controllare e limitare il traffico tra una rete interna e reti esterne. La sua efficacia dipende dalla corretta configurazione delle regole di filtraggio. Deve essere l'unico punto di contatto con l'esterno, bloccare tutti i pacchetti tranne quelli autorizzati e risultare sicuro a sua volta.
>
>I firewall si basano su due tipi principali di componenti: screening router, che filtrano i pacchetti in base all'intestazione (packet filtering) o al contenuto (packet inspection), e application gateway, che controllano il traffico a livello applicativo tramite proxy. I packet-filtering router operano a livello di rete e trasporto, permettendo o negando il passaggio dei pacchetti in base a regole sugli header. I packet-inspection router valutano anche il payload e possono monitorare lo stato delle sessioni TCP, offrendo più flessibilità nelle regole ma senza ricostruire i pacchetti.
>
>Gli application gateway offrono il maggior controllo sul traffico, ricostruendo e filtrando i pacchetti a livello applicativo tramite proxy specifici per ciascun protocollo. Ciò riduce il rischio di attacchi basati su vulnerabilità dei protocolli, ma rallenta il traffico e richiede proxy dedicati per ogni nuovo protocollo.
>
>In architetture complesse, come quelle web a tre o cinque livelli, i firewall possono essere disposti in sequenza con una zona DMZ (DeMilitarized Zone) tra il firewall esterno e quello interno. La DMZ ospita le risorse esposte alla rete esterna, mentre il resto della rete rimane protetto dal firewall interno, fornendo un ulteriore livello di sicurezza.

>[!tip] Intrusion Detection Systems
>Un'intrusione consiste in azioni che compromettono integrità, riservatezza o disponibilità di un sistema. L'intrusion detection è il processo di monitoraggio di sistemi o reti per rilevare tracce di attacchi. Gli IDS automatizzano questo processo, identificando intrusioni da utenti esterni (crackers) o interni (insider threat). Possono interagire con firewall per bloccare connessioni sospette o notificare l'amministratore.
>
>Gli IDS si basano sul presupposto che le attività di sistema siano osservabili e che le attività normali e quelle intrusive mostrino evidenze diverse. Un IDS è composto da sensori che raccolgono dati (log), algoritmi di analisi che rilevano intrusioni e componenti di alerting e response che notificano o intervengono sugli attacchi.
>
>Gli IDS possono essere network-based, analizzando il traffico di rete per rilevare pacchetti malevoli, o host-based, installati su singoli computer per monitorare attività di sistema e applicazioni. I network-based sono efficienti e richiedono pochi sensori ma non rilevano pacchetti cifrati né l'esito degli attacchi. Gli host-based rilevano anche attacchi su dati cifrati e software compromesso ma hanno maggiore impatto sulle prestazioni e sono difficili da scalare.
>
>Dal punto di vista dell'analisi, gli IDS possono usare misuse detection, confrontando l'attività con pattern di attacchi noti, o anomaly detection, rilevando deviazioni dai comportamenti normali. La misuse detection è precisa ma limita il rilevamento ad attacchi conosciuti; l'anomaly detection rileva anche attacchi sconosciuti ma genera molti falsi allarmi.
>
>Le risposte dell'IDS possono essere passive, notificando l'amministratore, o attive, intervenendo direttamente per bloccare o mitigare l'attacco.
