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

## Circuito principale

## Interazione tra sottocircuiti

## Considerazioni / possibili estensioni o modifiche