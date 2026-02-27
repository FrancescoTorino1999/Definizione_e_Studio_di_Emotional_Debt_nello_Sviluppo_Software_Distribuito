# Emotional Debt nella Software Engineering

Questo repository contiene tutti i materiali necessari per comprendere, replicare e analizzare lo studio empirico sul concetto di **Emotional Debt** nel contesto della Software Engineering.

Il progetto introduce e valida empiricamente il costrutto di:

- 🔥 Burnout  
- 💳 Emotional Debt  
- 👃 Emotional Smells  

attraverso un modello strutturale analizzato con metodologia **PLS-SEM (Partial Least Squares Structural Equation Modeling)**.

L’obiettivo è colmare il divario tra dimensione psicologica individuale e manifestazioni socio-tecniche osservabili nei processi di sviluppo software.

---

# 📂 Struttura del Repository

.
├── survey/
├── data/
├── pls-sem/
│ ├── SmartPLS project/
│ └── Exports/
├── Scripts/
├── conceptual/
└── thesis/


---

# 📝 survey/

Contiene il questionario utilizzato per la raccolta dati tramite Qualtrics.

Include:

- Esportazione del survey
- Struttura delle domande
- Item di misura relativi a:
  - Burnout
  - Emotional Debt
  - Emotional Smells

Questa cartella consente la replica completa della fase di raccolta dati.

---

# 📊 data/

Contiene i dataset utilizzati per l’analisi.

### File presenti

- `survey.csv` → dataset grezzo esportato da Qualtrics  
- `survey_pls.csv` → dataset pulito e formattato per SmartPLS  

Il file pulito è generato tramite script Python presenti nella cartella `Scripts`.

---

# 📈 pls-sem/

Contiene tutti i materiali relativi all’analisi PLS-SEM.

## 🧩 SmartPLS project/

- File completo del progetto SmartPLS
- Specifica del modello di misura
- Specifica del modello strutturale
- Configurazione bootstrapping (5000 subsamples, test a due code, BCa CI)

## 📤 Exports/

Contiene le esportazioni dei risultati:

- `Bootstrapping.xlsx`
- `Confirmatory Tetrad Analysis.xlsx`
- `Principal Components Analysis.xlsx`
- `PLS Predict.xlsx`
- `PLS Algorithm.xlsx`

Permette la verifica indipendente di:

- Affidabilità interna
- Validità convergente
- Validità discriminante
- Coefficienti di percorso
- R²
- f²
- Q²_predict
- HTMT
- VIF

---

# 🧹 Scripts/

Contiene gli script Python per la preparazione dei dati.

## format_for_plssem.py

Lo script:

- Rimuove risposte incomplete
- Applica filtri di qualità (attention check)
- Applica filtro sul tempo di completamento
- Rinomina e riorganizza le variabili
- Genera `survey_pls.csv`

---

## ▶ Come eseguire lo script

```bash
python format_for_plssem.py
```

Requisiti

Python 3.9+

pandas

numpy

Installazione dipendenze:

pip install pandas numpy

# 🧠 conceptual/

Contiene il modello concettuale alla base dello studio.

Il file (generato con draw.io) rappresenta:

Formalizzazione teorica dell’Emotional Debt

# 🔁 Replica completa dello studio

Di seguito sono riportati tutti i passaggi necessari per replicare integralmente lo studio sull’Emotional Debt.

---

## 1️⃣ Raccolta dei dati

### Strumenti utilizzati
- Qualtrics (somministrazione survey)
- Prolific (reclutamento partecipanti)

### Procedura

1. Distribuire il questionario tramite Qualtrics.
2. Reclutare sviluppatori software tramite Prolific.
3. Applicare i seguenti filtri:

   - ✔ Attention check obbligatorio  
   - ✔ Filtro sul tempo minimo di completamento  
   - ✔ Criteri di inclusione (sviluppatori attivi)  

4. Esportare i risultati in formato CSV.

Output atteso:


---

## 2️⃣ Pulizia e preparazione dei dati

La pulizia viene effettuata tramite script Python.

### Esecuzione

```bash
python Scripts/format_for_plssem.py

3️⃣ Analisi PLS-SEM
Software

SmartPLS 4

Procedura

Aprire SmartPLS.

Caricare il progetto presente in:

pls-sem/SmartPLS project/

Verificare configurazioni:

Bootstrapping: 5000 subsamples

Test a due code

Livello di significatività: α = 0.05

Eseguire:

PLS Algorithm

Bootstrapping

PLSpredict

4️⃣ Verifica dei risultati

Confrontare i risultati ottenuti con i file presenti in:

pls-sem/Exports/

In particolare verificare:

Outer Loadings

Cronbach’s Alpha

rho_A

Composite Reliability

AVE

HTMT

VIF

Path coefficients

R²

f²

Q²_predict

La replica è considerata corretta se i risultati coincidono con quelli esportati negli Excel forniti.

5️⃣ Riproducibilità completa

Per una replica completa:

Utilizzare lo stesso dataset pulito (survey_pls.csv)

Mantenere identica configurazione di bootstrapping

Non modificare la struttura riflessiva dei costrutti