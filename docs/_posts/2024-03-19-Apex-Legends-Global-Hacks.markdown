---
layout: post
title:  "[Italian] Apex Legends Global Hacks"
date:   2024-03-19 14:43:56 +0000
categories: security
---
il torneo Apex Legends Global Series (ALGS) è conosciuto nel settore del gaming professionistico come il torneo più prestigioso, direttamente organizzato e supportato da Electronic Arts, dell'omonimo gioco Apex Legends.
Il torneo si struttura in una serie di *giornate* durante le quali, in ciascuna regione, le squadre più forti del mondo si danno battaglia per cercare di conquistare uno dei 20 posti disponibili all'evento conclusivo: una finale in LAN con un montepremi complessivo di 1.000.000 di dollari.
Nel corso della giornata conclusiva per la regione del Nord America, tuttavia, il torneo è stato scosso da un evento che, nel mondo del pro gaming, o del gaming online in generale, risulta essere senza precedenti:

Mentre si disputava una partita, due dei giocatori più quotati, e di conseguenza seguiti live attraverso la famosa piattaforma di streaming Twitch, sono stati vittima di un attacco informatico nel corso del quale gli *hacker* sarebbero riusciti ad ottenere esecuzione di codice da remoto sui computer dei giocatori, eseguendo di conseguenza il deploy di strumenti adibiti al *cheating* (Aimbot, wallhack etc..).

L'accaduto, oltre ad aver portato all'immediata interruzione della competizione in corso, ha sollevato un enorme polverone e dato il via ad una serie di speculazioni sulle modalità attraverso le quali, gli attaccanti avrebbero potuto portare a compimento questa violazione.

Premesso che, nel momento in cui sto scrivendo questo articolo, non vi sono stati annunci ufficiali, vorrei provare, anche grazie al mio background tecnico, ad esaminare in maniera asettica la situazione per capire che cosa potrebbe essere successo.

### L'accaduto

Credo che il modo migliore per spiegare che cosa sia accaduto in quegli istanti, agli occhi degli spettatori, sia quello di mostrare una clip catturata dagli stream della partita in corso.

<iframe src="https://clips.twitch.tv/embed?clip=ApatheticAcceptableWhaleCopyThis-p4_Azg9oYVXBJr5x&parent=swappage.github.io" frameborder="0" allowfullscreen="true" scrolling="no" height="378" width="620"></iframe>

Come si può vedere, mentre la partita era in corso, sullo schermo è comparso un *gump* di un software per *cheating*, e il giocatore ha iniziato a vedere a schermo tutti gli altri player, anche attraverso i muri o gli ostacoli.

La cosa che si potrebbe pensare a prima vista, è che, accidentalmente e in maniera del tutto involontaria il giocatore abbia attivato, durante la propria live, il software in questione, auto smascherando il fatto che le sue attuali bilità non fossero reali, ma coadiuvate da strumenti che lo aiutavano *barando* in maniera plateale.

E tutto questo avrebbe senso se, allo stesso tempo, quasi in contemporanea, un altro famosissimo giocatore è risultato vittima del medesimo trattamento:

<iframe src="https://clips.twitch.tv/embed?clip=VivaciousNaiveWolfFUNgineer-eIoLbgTeD42AIjMd&parent=swappage.github.io" frameborder="0" allowfullscreen="true" scrolling="no" height="378" width="620"></iframe>

Ma quindi cosa può essere effettivamente successo realmente? Se diamo per scontata l'onestà dei sopra citati player, che comunque sono risaputi godere di ottima fama, e di aver dimostrato le loro reali capacità anche in eventi dal vivo, quali possono essere gli scenari possibili?

Di seguiro proverò ad esaminare alcuni degli scenari, per capire il livello di compromissione a cui ci si trova davanti, e se questo possa o meno rappresentare un rischio anche per altri utenti del battle royale targato EA/Respawn.

### Remote Code Execution

Se diamo per assodato che nè Genburten nè ImperialHal abbiano volontariamente installato dei *cheat engine* sui propri sistemi, affinchè questi possano essere stati *deployati* in maniera coatta, è necessario che in qualche modo i loro computer siano stati compromessi attraverso un sistema che abbia consentito agli attaccanti di eseguire codice arbitrario da remoto.

### Vettori di attacco
Premesso che al momento non vi sono comunicati ufficiali da parte delle software house, i vettori impiegati per conseguire i risultati precedentemente descritti possono essere diversi e di differente complessità, che possono coinvolgere unicamente i sistemi degli utenti che hanno riscontrato la compromissione, o che, nei casi più estremi, possono rappresentare un rischio anche per altri giocatori.
Vediamo cosa può essere accaduto, in ordine di probabilità.

#### Phishing
Tra tutti i vettori di attacco che possono essere stati impiegati, quello più semplice, e di conseguenza più plausibile, riguarda senz'altro l'impiego di tecniche di *social engineering*: attraverso un pretesto, gli attaccanti potrebbero aver eseguito un attacco di *phishing* su larga scala verso i principali videogiocatori di Apex Legends partecipanti al torneo ALGS, averne di conseguenza compromessi alcuni in tempi non sospetti e, dopo aver preso il controllo delle loro postazioni, aver sferrato l'attacco effettivo durante il torneo.
I pretesti possono essere molteplici, e i criminali informatici al giorno d'oggi sono diventati particolarmente abili nel pianificare attacchi di questo tipo: basti considerare che ormai, gli attacchi basati su social engineering, rappresentano la maggioranza dei vettori di compromissione anche di grandi realtà aziendali, che sicuramente prendono questi tipi di minacce molto seriamente.
Se questo fosse il caso, gli altri giocatori di Apex Legends potrebbero, in un certo senso, dormire sonni tranquilli, perchè il vettore di compromissione sarebbe esterno ai canali di gioco.

#### Apex Game servers go brrrrr
Apex tuttavia non è famoso per essere stato, negli anni, un gioco esente da problemi: sono infatti diversi gli eventi nefasti che hanno interessato l'infrastruttura di backend del gioco di casa EA, e recentemente si sono osservati episodi nei quali certi individui erano in grado di sovvertire le meccaniche di gioco manipolando direttamente il comportamento di alcuni asset lato server.

<blockquote class="twitter-tweet" data-media-max-width="560"><p lang="en" dir="ltr">1v30 plus aimbotter Ranked :) <a href="https://t.co/lZk27quRg2">pic.twitter.com/lZk27quRg2</a></p>&mdash; TSM ImperialHal (@ImperialHal) <a href="https://twitter.com/ImperialHal/status/1755436088590496085?ref_src=twsrc%5Etfw">February 8, 2024</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> 

Nel video possiamo infatti vedere uno degli ultimi attacchi di arassment alle lobby del gioco dove gli attaccanti riusciano a spawnare entità (bot) all'interno del match per importunare i giocatori.

È evidente come in questo caso, la compromissione sia completamente differente in termini di vettore di attacco, in quanto chi esegue questi tipi di manipolazioni, è quasi certamente in grado di interagire con l'infrastruttura di backend, ed inviare ai server delle partite in corso comandi non autorizzati, che però questi accettano ed interpretano correttamente.

Questa tipologia di compromissione, mixata con gli accadimenti di domenica, ha portato a speculazioni, ad oggi assolutamente non provate, ma allo stesso tempo nemmeno smentite, secondo le quali il client di gioco, possa essere stato sfruttato come vettore di *command and control* per eseguire codice arbitrario sui sistemi vittima.

Secondo il mio modesto parere, questa dinamica di attacco è al quanto improbabile, a meno che il client di gioco, davvero, non preveda delle funzionalità interne che consentano ai server di backend di impartire l'esecuzione di codice sui computer dei giocatori: questo sarebbe non solo estremamente grave, ma allo stesso tempo una scelta enormemente irresponsabile da parte degli sviluppatori, nonchè allo stesso tempo una violazione della riservatezza dei sistemi degli utenti, in quanto in qualsiasi momento, EA avrebbe la possibilità di eseguire un accesso non autorizzato ai sistemi del proprio bacino di utenza videoludica.

Di conseguenza l'unico modo in cui un attacco di questo tipo si potrebbe configurare, riguarderebbe la presenza e lo sfruttamento di una vulnerabilità nel client di gioco, veicolabile tramite l'invio di pacchetti malevoli da parte del server.
Tuttavia anche in questo caso lo scenario risulterebbe molto improbabile: per svolgere un attacco del genere, se le funzioni non sono previste, sarebbe necessario, in qualche modo, sovvertire il flusso di esecuzione dell'applicativo stesso che, una volta *exploitato* avrebbe pochissime possibilità di conservare la propria integrità di processo, e verosimilmente crasherebbe.

#### AntiCheating Conspiracy!
L'ultimo scenario messo sul tavolo, che possa coinvolgere l'infrastruttura di gioco, prevede il coinvolgimento del motore anticheat.
Apex Legends utilizza un sistema anti cheat sviluppato da Epic Games chiamato *Easy AntiCheat*, il cui funzionamento si basa sull'installazione di un driver in kernel space, che monitora in maniera costante il processo del gioco per verificare che questo sia integro e non manipolato da strumenti software esterni.
Il fatto che questo strumento monitori costantemente il client di gioco, e che per come funziona, operi con dei privilegi estremamente elevati, lo rende senza ombra di dubbio un target appetibile nel caso in cui un attaccante voglia tentare di eseguire codice su un sistema vittima, tuttavia è importante ricordare che le funzioni che svolge il motore anticheat sono prevalentemente di monitoraggio a basso livello del processo e, sebbene sia un prodotto closed source e quindi poco documentato, ad oggi non si hanno notizie di casi pregressi in cui sia stata rinvenuta una criticità che possa consentire ad un attaccante dis fruttare questo specifico driver per esecuzione di codice da remoto (RCE).
Per lo più i driver vengono impiegatiper attacchi EOP (Elevation of privileges), e credo che affinchè un attaccante possa sfruttare Easy AntiCheat come vettore per remote code execution, da parte sua sia necessario uno sforzo paragonabile ad un *supply chain attack*: cosa poco sensata in termini di costi benefici.

#### Supply chain attack
E qui veniamo all'ultima delle possibilità, la più catastrofica possibile, e di conseguenza anche quella, a mio avviso, meno probabile: la compromissione del client direttamente a livello di repository di sviluppo.
Se gli attaccanti avessero avuto accesso ai repository utilizzati dagli sviluppatori del gioco, questi avrebbero potuto *trojanare* il client facendo in modo che, nel corso di un aggiornamento, la backdor venisse *deployata* su tutti i sistemi su cui Apex Legends veniva installato/aggiornato.

Queste tipologie di attacco vengono chiamate con il nome di *supply chain attack*, e non sarebbe la prima volta che accadono: tuttavia queste tipologie di compromissioni generalmente si possono osservare in attacchi *nation state sponsored* o comunque di alto profilo, dove i costi benefici sono decisamente diversi da quelli che si possono ottenere da uno (passatemi il termine) *show case* come quello di domenica notte.

### Concludendo
Per quello che si può sapere, al momento in cui sto scrivendo questa mia elocubrazione delirante, non vi sono comunicati ufficiali da parte degli sviluppatori dei vari componenti che costituiscono l'infrastruttura di gioco di Apex Legends (in ogni sua parte).
Sicuramente le investigazioni sono ancora in corso, e a due giorni di distanza, pare che, anche altri esperti del settore, stiano considerando la compromissione dei singoli sistemi, come l'ipotesi più plausibile.

"Ma quindi è sicuro secondo te giocare ad Apex a fronte di quanto accaduto domenica?"

La risposta è: non lo so.. e tutto dipende dal modello di rischio a cui si è esposti.
Io non credo che quanto accaduto domenica notte possa essere collegato ad una compromissione dei sistemi di backend e di conseguenza ad una diffusione massiccia di client potenzialmente vulnerabili: secondo il mio modesto parere, le compromissioni dei PC di **Genburten** e di **ImperialHal** non può essere collegata ai nefasti casi di attacco che hanno riguardato i server di gioco, e allo stesso modo penso che, se così fosse, e EA/Respawn ne avessero avuto anche il minimo sentore, sarebbero rapidamente corsi ai ripari chiudendo temporaneamente l'infrastruttura fino al rilascio di una patch di sicurezza.

Ad ogni modo, una cosa è certa: sicuramente il personale del SoC e dell'incident response team di EA, in questi giorni non se la staranno passando bene, e in qualità di persona che lavora nel ramo della sicurezza informatica, è proprio quando vedo scenari come questo che penso di aver fatto la scelta giusta, scegliendo di giocare dal lato della barricata di chi simula un attacco, e non di chi deve difendere le infrastrutture. 

Per ora è tutto, e alla prossima.

