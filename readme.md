>Modellizzare la struttura di un database per memorizzare tutti i dati riguardanti una università:

- sono presenti diversi '`Dipartimenti`' (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);,
- ogni `Dipartimento` offre più `Corsi di Laurea` (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..),
- ogni `Corso di Laurea` prevede diversi `Corsi` (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);,
- ogni `Corso` può essere tenuto da diversi `Insegnanti`;,
- ogni `Corso` prevede più appelli `d'Esame`;,
- ogni `Studente` è iscritto ad un solo `Corso di Laurea`;,
- ogni `Studente` può iscriversi a più appelli di `Esame`;,
- per ogni appello `d'Esame` a cui lo `Studente` ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente.

Pensiamo a quali entità (tabelle) creare per il nostro database e cerchiamo poi di stabilirne le relazioni. Infine, andiamo a definire le colonne e i tipi di dato di ogni tabella.

Esportare quindi il diagramma in jpg e caricarlo nella repo.
>

# università 

# dipartimenti (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.)
  - id pk auto_increment
  - nome notnull varchar(40)

# corsi_di_laurea (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
  - id pk auto_increment
  - nome notnull varchar(40)
  - dipartimento_id notnull
 
# corsi (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.)
  - id pk auto_increment
  - nome notnull varchar(40)
  - corso_di_laurea_id notnull

# insegnanti
  - id pk auto_increment
  - nome notnull varchar(40)

# insegnanti_corsi
  - insegnanti_id notnull
  - corsi_id notnull

# studenti
  - id pk auto_increment
  - nome notnull varchar(40)
  - corso_di_laurea_id notnull

# appelli
  - id pk auto_increment
  - data notnull date   
  - corso_id notnull

# iscrizioni_appelli
  - studente_id notnull
  - appello_id notnull
  - voto null tinyint
  - lode null tinyint default(0) 
  - presenza notnull tinyint default(0)                  

