# Progetto Architetture degli Elaboratori

```
Nome e cognome: NOTARI KRISTIAN
Matricola:      892708
Email:          kristian.notari@studenti.unimi.it
````

## Specifiche progetto

### Descrizione generale progetto
Il circuito implementato avrà il compito di rappresentare graficamente su di una matrice led il polinomio (x^2 + x + q), capace di formare rette e parabole, in un intervallo positivo di x (0-31), dati i coefficienti di x^2, x e q in input. La matrice corrisponderà ad un grafico di soli punti interi, dove ogni led corrisponderà ad un numero tra 0 e 31.
Il circuito sarà regolato da un clock che, ad elevata frequenza, permetterà il rapido aggiornarsi della matrice led dati i nuovi valori in input in modo dinamico. Inoltre, avrà la possibilità di salvare un grafico in memoria così da confrontarlo con un altro attivo e modificabile, oltre ad effettuare operazioni di addizione e sottrazione tra i due (di base il circuito, qualora fossero selezionate queste due operazioni, non visualizzerà nulla fino a che almeno un grafico non è stato salvato).

### Interfaccia utente (componenti Input/Output)
L'interfaccia sarà composta da un tastierino numerico da 0 a 9 con cui inserire i coefficienti del polinomio (a singola cifra) e da una matrice led capace di far vedere graficamente l'elemento geometrico desiderato. Inoltre il tastierino avrà una serie di comandi per la gestione degli input (come un tasto annulla e azzera), quelli per la gestione del grafico salvato (salva, elimina, carica) e uno di scelta dell'operazione da effettuare su due eventuali grafici. Vi saranno display per visualizzare i coefficienti attuali e quelli salvati, oltre all'operazione e al coefficiente selezionati.

### Condizioni iniziali del circuito
Il circuito non è dotato di situazioni iniziali o finali pertanto avrà semplicemente i coefficienti del polinomio in input equivalenti a 0 e l'operazione impostata su "doppio grafico".

### Condizioni finali del circuito
Il circuito non è dotato di situazioni iniziali o finali pertanto avrà semplicemente la matrice led in output corrispondente ai dati presenti all'interno del circuito in un dato momento.

### Ciclo tipico di utilizzo descritto in termini di componenti di input/output
L'utente dovrà impostare i coefficienti del polinomio attraverso il tastierino numerico per poi visualizzare l'output sulla matrice di led. Se vorrà, in qualsiasi momento, potrà scegliere quale coefficiente modificare e se resettare il plotter allo stato iniziale o meno, oltre ad effettuare le operazioni sopracitate.

## Sottocircuiti implementati

### Gestore input
![alt text](risorse/m_input.png)<br>
Si occupa di gestire l'input utente. Controlla l'inserimento dei coefficienti da tastierino, gestisce gli input di selezione coefficiente e operazione e inoltra al resto del circuito (organizzazione cablaggio) i segnali di controllo dei grafici.<br>
In ingresso ci sono i segnali che determinano il coefficente in uscita, da 0 a 9 compresi, i segnali di reset del circuito, azzera, annulla, inserisci per manipolare i coefficienti, left e right per selezionare il coefficiente da modificare, salva, carica e cancella per manipolare il circuito da salvare, di cui caricare i coefficienti nel grafico attivo o da cancellare, oltre al segnale per modificare l'operazione da effettuare sui due grafici.<br>
In uscita inoltra i segnali di reset, azzera, annulla, inserisci, salva, carica e cancella, che serviranno al resto del circuito e interfaccia il numero inserito, un segnale di click che identifica quando viene premuto un pulsante del tastierino, e il codice operazione selezionato.<br>
Possiede un sottocircuito interno "keypad" che fa corrispondere in modo univoco all'input a 1 di uno dei 10 segnali di ingresso (i numeri da 0 a 9) il numero associato attraverso semplici porte logiche, oltre a registrare in output quando è stato cliccato un pulsante del tastierino. Inoltre possiede due contatori interni a 2 bit con valore minimo 0 (00) e valore massimo 2 (10) che determinano il coefficiente e l'operazione selezionati, modificabili attraverso i segnali di left/right (quando a 1 decrementano/incrementano il contatore, con limite ai valori minimi/massimi) e il segnale di op_code (che incrementa sempre quando a 1, senza limiti inferiori/superiori).

### Memoria dati
![alt text](risorse/m_memory.png)<br>
La memoria dati gestisce i dati in input dei coefficienti del grafico attivo interfacciandoli con il resto del circuito e permettendo all'utente operazioni come l'annulla e il salvataggio dei coefficienti del grafico da salvare.<br>
In ingresso 

### Circuito di calcolo
![alt text](risorse/m_calcolo.png)<br>

### Circuito di disegno
![alt text](risorse/m_drawer.png)<br>

## Circuito principale
@@@@@@@@@@@@@@@@@@@@<br>COME FAR ANDARE AVANTI IL CONTATORE DELLE X (CON CLOCK) COSI' E' DINAMICO E SI AGGIORNA SEMPRE CON ALTA FREQUENZA<br>@@@@@@@@@@@@@@@@@@@@
<br>GESTIONE OVERFLOW PERCHE NON POSSO RAPPRESENTARE NUMERI OLTRE 0...31 PER LE Y<br>@@@@@@@@@@@@@@@@@@@@
<br> SICCOME AVREI DOVUTO SALVARE ANCHE L'OVERFLOW DEL NUMERO DA SALVARE, O PREFERITO SALVARLO IN RAPPRESENTAZIONE GRAFICA -> DA CUI TUTTA GESTIONE DEL MERGING<br>@@@@@@@@@@@@@@@@@@@@
<br>SCELTO UN CONTATORE PERCHE OGNI VOLTA CALCOLARE OGNY Y PER OGNI X AVREBBE RICHIESTO UN CIRCUITO LUNGO E COMPLESSO SENZA SENSO QUANDO POSSO AGGIORNARE DINAMICAMENTE<br>@@@@@@@@@@@@@@@@@@@@


## Interazione tra sottocircuiti

## Considerazioni / possibili estensioni o modifiche