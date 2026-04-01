# Emotional Debt nella Software Engineering


Negli ultimi anni, la Software Engineering ha riconosciuto l’impatto delle dimensioni psicologiche sulla produttività e sulla qualità del software. Tuttavia, manca ancora una formalizzazione chiara dei meccanismi attraverso cui condizioni come il burnout si traducono in effetti osservabili nei repository.

Questo lavoro introduce il concetto di:

* 🔥 Burnout: condizione psicologica individuale
* 💳 Emotional Debt: accumulo di tensione emotiva non elaborata
* 👃 Emotional Smells: manifestazioni socio-tecniche osservabili

e propone un modello che collega questi tre livelli, colmando il divario tra dimensione individuale e comportamento osservabile nei sistemi software.

Questo repository accompagna la tesi magistrale “Definizione e Studio di Emotional Debt nello Sviluppo Software Distribuito” e contiene tutti i materiali necessari per comprendere, replicare e validare uno studio empirico sul ruolo dei fattori emotivi nei processi di sviluppo software.


## 🎯 Obiettivo della tesi

L’obiettivo principale è:

formalizzare il costrutto di Emotional Debt
dimostrare empiricamente il suo ruolo di variabile mediatrice
identificare proxy osservabili nei repository (Emotional Smells)

Il lavoro si colloca all’intersezione tra:

* Software Engineering empirica
* Sentiment Analysis e NLP
* Sistemi socio-tecnici
* AI per analisi del codice

## 🧪 Metodo di ricerca

Lo studio adotta un approccio quantitativo basato su:

Survey empirica (Qualtrics + Prolific)
Costruzione di costrutti latenti
Analisi tramite PLS-SEM (Partial Least Squares Structural Equation Modeling)

Modello analizzato:

Burnout → Emotional Debt → Emotional Smells → Consequences

## 📊 Risultati principali

L’analisi empirica mostra che:

Il Burnout spiega oltre il 60% della varianza dell’Emotional Debt
L’Emotional Debt ha un impatto significativo sugli Emotional Smells
È presente una mediazione significativa tra burnout e comportamenti osservabili

Questi risultati suggeriscono che le condizioni psicologiche influenzano il software in modo indiretto, attraverso un debito emotivo accumulato che si manifesta nei processi di sviluppo.

## 📂 Struttura del Repository

### 📝 survey/  

Contiene il questionario utilizzato per la raccolta dati.

Include:

Struttura completa del survey
Item di misura per:
* Burnout
* Emotional Debt
* Emotional Smells

Permette la replica della fase di raccolta dati.

### 📊 data/

Dataset utilizzati nello studio.

survey.csv → dati grezzi Qualtrics
survey_pls.csv → dataset pulito per SmartPLS

Il dataset finale è ottenuto tramite gli script nella cartella Scripts.

### 🧹 Scripts/

Script Python per la preparazione dei dati.

format_for_plssem.py

Lo script:

- Rimuove risposte incomplete
- Applica filtri di qualità (attention check)
- Filtra per tempo minimo di completamento
- Rinomina e riorganizza le variabili
- Genera survey_pls.csv
- Esecuzione
- python Scripts/format_for_plssem.py

Requisiti
- pip install pandas numpy

### 📈 pls-sem/

Materiali relativi all’analisi PLS-SEM.

SmartPLS project/
Modello di misura (outer model)
Modello strutturale (inner model)
Configurazione bootstrapping:
5000 subsamples
test a due code
α = 0.05

### Exports/

File per verifica indipendente dei risultati:

Bootstrapping
PLS Algorithm
PLSpredict
HTMT
VIF
PCA

### 🧠 conceptual/

Contiene il modello concettuale della tesi:

Formalizzazione teorica dell’Emotional Debt
Relazioni tra costrutti

### 📄 thesis/

Contiene l’elaborato finale della tesi magistrale in versione PDF.

## 🔁 Replica completa dello studio
### 1. Raccolta dati

* Qualtrics → somministrazione survey
* Prolific → reclutamento partecipanti

Filtri applicati:

Attention check
Tempo minimo di completamento
Sviluppatori attivi

### 2. Preparazione dati
python Scripts/format_for_plssem.py

### 3. Analisi PLS-SEM

Software: SmartPLS 4

Eseguire:

1. PLS Algorithm
2. Bootstrapping
3. PLSpredict

4. Validazione risultati

Verificare:

Affidabilità

- Cronbach’s Alpha
- Composite Reliability
- rho_A

Validità

- AVE
- HTMT

Modello strutturale

- Path coefficients
- R²
- f²
- Q²_predict
- VIF

## 💡 Contributo scientifico

Questo lavoro contribuisce allo stato dell’arte:

* Introducendo Emotional Debt come nuovo costrutto
* Collegando burnout e comportamento nei repository
* Proponendo un approccio misurabile e replicabile
* Aprendo alla possibilità di strumenti automatici di detection

## 🚀 Sviluppi futuri
* Detection automatica di Emotional Smells nei repository
* Integrazione con pipeline CI/CD
* Supporto al decision-making nei team
* Analisi dell’impatto della GenAI sul debito emotivo