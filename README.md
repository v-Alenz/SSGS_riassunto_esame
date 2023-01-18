
# Possibili esami SSGS

## Indice


## VS code 
### Introduzione a VS Code 
 
 - Con quali tecnologie e' stato sviluppato?
 
 Electron, JavaScript. Sviluppato da Microsoft.

 - Puoi vere piu di un porgetto apperto su VSCode?

 Si.

## Java Debugging
 - Quale e' la differenza tra testing e debbuging?

 Testing trova i *Failure* mentre debugging trova i *Bug*. (Trova l'errore, elimina il foult).

 - Perche' ha senso fare debugging serio?
 
 Perche' fare la print in 2000 righe di codice fa cagare.

 - Cosa e' un Breakpoint?
 
 Un punto arbitrario nel codice in cui interrompere l'esecuzione.

 - Cosa e' un LogPoint?
 
 Come le print ma meglio.

 - Cosa e' un conditional Breakpoint?
 
 Come il Breakpoint ma si interrmpe solo se e' vero.

 - Puoi modificare le variabili durante l'esecuzione?
 
 Si, in debugger ti consente di modificare le variabili e valutare le espressioni.

 - Se si modifica il file Java durante il debugging, devo ricominciare da capo?
 
 Nope, grazie alla feature del **Hot Code Replacement**

## GIT
 - Che cosa e' GIT?
 
 Un sistema di Versioning del Codice.

 - Quando nasce e chi lo ha creato?
 
 Nasce nel 2005 creato dal team di Linus Torvalds per lo sviluppo del kernel Linux.

 - A vosa serve?
 
 Per poter gestire le varie versioni di un SW, per poter lavorare con altre persone sullo stesso source.

 - Quale e' l'idea alla base di GIT?
 
 Avere un Repository con tutte le versioni, tutti gli utenti:
  
  - Copiano in locale il Repository.
  - Fanno commit dei cambiamenti.
  - Risolvono eventuali confilitti.

 - Come si crea un Repository?
 
 `git init`

 - Come vedo lo status di un Repository?
 
 `git status`

 - Come aggiungo un file al Repository?
 
 `git add <filename>` oppure `git add .` li aggiunge tutti.

 - Quali stati puo avere un file nel Repository?
 
 Unchanged, changed e staged.

 - Come tolgo un file dalla Staging Area?
 
 `git reset <filename>`

 - Come faccio il commit dei files dal repo locale?
 
 `git commit ...`

 - Cosa sono i Branch in un Repository?
 
 Sono versioni alternative di uno stesso progetto (piattaforma diversa, linguaggio diverso..) sviluppate in parallelo.

 - Come si gestisce un Branch nel Repository?
 
    - `git branch <new branch name>`: creo un nuovo banch.
    - `git checkout <destination>`: muovo la HEAD (mi sposto) in un altro branch.
    - `git checkout -b <destination>`: mi muovo in un nuovo branch e se non esiste lo creo.
    - `git branch -d <branch name>`: eleimito un branch. Funziona solo se e' gia stato fatto un merge oppure bisogna forzarlo con `-D` al posto di `-d`.

 - Cosa e' il Meriging?
 
 Unire in un solo branch le modifice fatte in uno o piu altri. Possono esssere necessarie azioni manuali di risoluzione dei conflitti.

 - Come si fa un Merge?
 
 `git merge <branch name>`.

 - Come annullo un Merge in faco si confliti irrisolvibili?
 
 `git merge --abort`.

 - Cosa e' la Rebase?
 
 Appende le modifche fatte ad un brench ad un altro.

 - Come faccio se devo modificare l'ultimo commit fatto?
 
 `git commit --ammend ...`

 - Come faccio per elimiare dei commit e tornare indietro nelle versioni.
 
 `git reset <node name>`

 - Come faccio per passare da un nodo ad un altro?
 
 `git checkout <node name>`

 - Durante il clone, copio tutti i branch del progetto?
 
 Nope, copio solo quello dove e' presente l'HEAD. Se voglio un altro branch devo fare `git checkout origin/<branch name>`.

## Git && VS code


## Testing JUnit
 - Cosa e' JUnit?
 
 Fraework di *unit testing* per Java.

 - Cosa posso fare con JUnit?
    - Scrivere casi di test.
    - Eseguire i casi di test e vedere il risultato.
    - Raggruppare i casi di test in testsuite.

 - Come JUnit implementa il testing?
 
 Tramite classi di test da "accoppiare" alla classe da testare.

 - Cosa significa che un test e' coeso?
 
 Che testa usa sola funzionalita'. Se devo testarne altre mi creo direttamente un altro test.

 - Come fa JUnit a testare le cose?
 
 Tramite le asserzioni.

## Maven
 - Cosa e' Maven?
 
 Tool per la gestione dei progetti Java basato sul POM.
 
 - Perche' usare Maven?
 
 Portabilita': effettua automaticamente la gestione ed il download delle librerie Java. Esegire test automatici.

 - Cosa e' la *build* in Maven?
 
 La build e' il processo che ci consente di coprire tutti gli step necessari al "deliverable" del SW.

 - Cosa e' il POM?
 
 (Project object model) Un file di configurazione XML che contiene tutte le dipendenze e relative configurazioni.

 - Come e' specirficate le dimendenze nel POM?

 Si dividono in diversi TAG:
    - La tripletta *groupOD*, *aritfactID*, *version* identificano univopcamente la libreria nel repo di Maven.
    - il tag *type* identifica il fomato della libreria, di default e' .jar.
    - il tag *scope* identifica la fase (di Maven) del progetto in cui e' necessaria la dipendenza.
    - il tag *optional* indica che la dipendenza e' opzionale nel caso in cui importo questo progetto in un altro.

 - In cosa consiste il Maven Build Lifecycle?

 Esistono 3 lifecycles builtin?
    - *default* responsabile del deployment.
    - *clean* pulisce i files buildati.
    - *site* crea la documentaizone del progetto.
 Ogni lifecycle e' usa sequenza di fasi.

 - Cosa sono le *fasi* in Maven?

 Ogni fase e' responsabile di uno specifico task.

 - Quali sono le fasi piu importanti del lifecycle di default?

    - validate
    - compile
    - test-compile
    - test
    - package
    - integratin-test
    - install
    - deploy

 - In quale ordine vengono eseguite le fasi?

 Quando viene lanciata una fase questa viene eseguita e vengono eseguite anche tutte le fasi da cui questa dipende.

 - Cosa sono i Golas in Maven?

 Sono i vari obbiettivi di cui si compone una specifica fase. I goal sono reponsabili degli specifici task.

 - Cosa sono i plugin in Maven?

 Un plugin e' una componente che implementa un insime di goals. Per esempio `mvn <plugin name>:help`.
 Non tutti i goals e' detto che siano legati ad una stessa fase, ad esempio un plugin puo implementare goals appartenenti a due fasi diverse.

 - Come gestiso quali goals eseguire in quali fasi?

 Specificando il compostamento delle fasi direttamente nel POM.

 - Cosa e' il *Super POM*?

 Un file (del tutto simile al POM) in cui sono specificate le assocazione di default tra el fasi del lifecycle de i plugins. 

 - Cosa e' l'*Effecitove POM*?

 L'unione del POM e del Super POM di un dato progetto.

 - Cosa sono le Propertyes di Maven?

 Sono simili al concetto di costante nei linguaggi di porgrammazione. Una voltra definiti i loro valori sono accessibili ovunque all'interno del POM con la sintassi ${NAME}.

 - Cosa fa il Plugin Resurces?

 Si occupa di copiare i files dalle cartelle resources alla corripettiva cartella nel target, estendendo tutte le properties.

 - Un progetto Maven puo dipendere da un altro?

 Si, ma deve essere prima installato utilizzando la fase di *install* dal progetto che vogliamo ereditare.
 Sara' poi necessario solo aggiungere la diopendenza del progetto nel POM del progetto figlio.

 - E' possibile avere un Progetto Multi-Module in Maven?

 Si, e' possibile connetter due progetti e fare in modo che quando chiuamo una fase del lifecycle su uno, viene eseguita anche sull'altro.
 E' possibile farlo aggiungendo il tag `<modules>` direttamente nel POM.

 - Cosa sono i Profili in Maven?

 Impostazioni valide solo in un determinato contesto. 
 Ad esempio possiamo compilare il porgetto in fase di sviluppo (profilo DEV) e aggiungere delle dipemndenze di testing, 
 e poi copilarlo con un altro porfilo (es. Deploy) e non includere suddette dipendenze
 E' possibile campiare profilo da line di comando aggiungendo il tag `-P <profile name>` oppure nel POM con il tag `activation`.

 - Cosa e' l'Ereditarieta' del POM?

 Un progetto figlio in Maven eredita le informazioni contenute nel POM del padre, ma puo comunque fane l' override.

## GitHub Gestione progetti

 - Cosa e' GitHub?
 
 Un servizio di hosting di Repository GIT.

 - Come faccio se voglio creare un mio Repository a pratire da un altro?
 
 Utilizzando la funzionalita' Fork di GitHub.

## GitHub Actions
 - Cosa sono le GitHub Actions?
 
 Strumento di automatizazione, consente di creare una pipeline/workflow di task.

- Cosa significa CI/CD?

Continuous Integration / Continuous Deployment.

 - Fammi un esempio di utilizzo delle GitHub Actions.

 Azioni in risposta ad eventi che accadono nel Repository, eseguire i test automatici tutte le volte che avviene un merge, 
 eseguire i test automatizzati, creare un pacchetto e fare il deploy suserver ogni volta che avviene un merge sul brench master.

 - Quali sono le compomnenti delle GitHub Actions?

    - *eventi*: azzioni che triggerano workflow (merge, commit ecc..)
    - *workflow*: insime di jobs.
    - *jobs*: lista di steps eseguiti da uno stesso runner. Ogni job e' eseguito in parallelo all'interno di una virtual machine dedicata.
    - *step*: esecuzione di comandi che possono essere actions o comandi shell.
    - *actions*: comandi specifici che eseguono un task fornito da GitHub.
    - *runner*: server che eseguono un determinato workflow. Puo essere hostato da GitHub stesso oppure gestito da un server locale. 

 - Cosa e' YAML?

 E' un linguaggio di scambio dati usato per i files di configurazione simile a JSON e XML. 
 Utilizza l'indentazione (come python) per indicare la nidificazione.
 Consente di creare Mappature per associare coppie chiave/valore con chiavi univoche.
 Consesnte inoltre di creare liste i cui elementi sono separati da un trattino (`-`) e uno spazio.

 - Dove posso trovare le Acrtions gia fornite da GitHub?

 Nel loro relativo Marketplace.

 - Cosa sono i *secrets*?

 Un meccanismo che consente di conservere in modo sicuro dati sensibili  (es password) che verranno poi passati ai jobs.

 - Posso specificare un ordine in cui eseguire i vari jobs?

 Si, di base i jobs vengono eseguiti in parallelo ma e' comunque possibile spoecificare ad uno di aspettare l'esecuzione di un altro.

 - Come faccio a specificare a GitHub quali jobs eseguire?

 Inserendoli in un file di configurazione all'intenro della cartella `.github/workflow` del Repository.

## Docker
 - Cosa e' Docker?
 
 Framwork di sviluppo che permette la creazione e gestione di container.

 - Cosa e' un container?
 
 **Paccketti software** che contengono tutti gli elementi necessari per l'esecuzione di un app in qualsiasi ambiente e consistentemente.

 - Quale e' la differenza tra Container e Virtual Machine?

 Un container e' un astrazione fatta direttamente sul sistema host e di conseguenza non ha un suo kernel, ecc...
 Una macchina virtuale sono invece astrazione dell'hardware fisico e di conseguenza hanno il loro sistema operativo.

 - Perche' proprio Docker?

 Non lo so, tanto in produzione si usa *containerd*

 - Quali sono i concetti base dietro a Docker?
    - *container*: sono istanze in esecuzionme di un immagine.
    - *imamgine*: codice sorgente dell'applicazione esguibile e tutto cio che serve per la sua esecuzione (strumenti, librerie, dipendenze ecc..)
    - *registry*: archivio di immagini (volendo condivisibili)
    - *docker hub*: repository pubblico di immagini
    - *dockerfile*: file di testo con le istruzioni relative alla creazione di un immagine.
    - *docker engine*: client/server che costruisce ed esegue i container.
    - *docker desktop*: l'applicazione marcia che ti fa gestire i container docker.

 - Quali sono le differenze tra *imamgine* e *container*?

 L'immagine contiene i temoplates per il container (codice, tool ecc..).
 Il container invece e' un porgramma in esecuzine che corrisponde ad un istanza dell'immagine.

 - Cosa sono i livelli delle immagini di Docker?

 Ogni volta che apporto modifiche ad un immagine viene generato un nuovo livello sopra all'immagine precedente.
 E' poi possibile creare containers da ogni livello dell'immagine (anche se di default viene preso semopre l'ultimo).
 Da notare che se vengono apportate modifiche all'interno di un container rimarranno all'intenro del container stesso e moriranno con lui.


 - E' possibile rendere i dati di un container persistenti?

 Si, e' possibile condividere tramite il comando `VOLUME` o `bind mounts` una cartella/porzione di dati nel 
 filesystem della macchina Host al filesystem del container.

 - Cosa sono i Networks in Docker?

 Sono delle reti emulate per mettere in comunicaizione uno o piu containers tra di loro.
 Di default viene utilizzata al rete di default definita da Docker, ma si possono creare reti di comunicaizone personalizzate.

