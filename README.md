SPIEGAZIONE CODICE

Creo due macrocomponenti chiamati AppHeader ed AppMain

In AppHeader creo semplicemente un header con all'interno il titolo e il logo della pagina

Dopodichè creo altri due componenti figli di AppMain che sono CardList e SingleCard
In CardList inserisco nei data l'array che contiene tutti i dati delle card (nome, foto, desc ecc.) ed uso questo componente per ciclare sull'array importando poi il componente SingleCard che crea la card singola
In SingleCard invece creo effettivamente la struttura che prenderà i data importati con i props per creare in pagina la singola card con la sua immagine il titolo ecc.

In AppMain infine importo CardList
