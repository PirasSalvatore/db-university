# university DB

Modellizzare la struttura di un database per memorizzare tutti i dati riguardanti una università:
sono presenti diversi `Dipartimenti` (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
ogni `Dipartimento` offre più `Corsi di Laurea` (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
ogni `Corso di Laurea` prevede diversi `Corsi` (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
ogni `Corso` può essere tenuto da diversi `Insegnanti`;
ogni `Corso` prevede più appelli d'`Esame`;
ogni `Studente` è iscritto ad un solo `Corso di Laurea`;
ogni `Studente` può iscriversi a più appelli di `Esame`;
per ogni appello d'`Esame` a cui lo `Studente` ha partecipato, è necessario memorizzare il **voto** ottenuto, anche se non sufficiente. Pensiamo a quali entità (tabelle) creare per il nostro database e cerchiamo poi di stabilirne le relazioni. Infine, andiamo a definire le colonne e i tipi di dato di ogni tabella.

## table name: `Dipartimenti`

**colums**

- id
- name
- code
- adress
- classes
- ? corsi di laurea

## table name: `Corsi_di_laurea`

**colums**

- id
- name
- code
- ? corsi(materie)/plan/corsi
- life
- credits

## table name: `Corsi`

**colums**

- id
- name
- code
- ? insegnanti
- credits

## table name: `insegnanti`

**colums**

- id
- name
- last name
- ? corso
- email
- ? esami

## table name: `Studenti`

**colums**

- id
- name
- lastname
- data_of_born
- email
- password
- ? corso
- ? libretto

## table name: `Libretto`

**colums**

- id
- credits

## table name: `Esami`

**colums**

- id
- corso
- insegnante
- studente
- voto
- class

## realitions

1 diparte molti corsi di laurea
1 corso di laurea molti corsi
molti corso molti insegnanti (un insegnante può tenere motli corse, e un corso puù essere tenuto da motli insegnanti)
1 corso molti esami
1 studente 1 corso
1 studente molti esami
1 insegnante molti esami