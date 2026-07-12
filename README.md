# Progetto Gruppo 12
Introduzione alla Data Science e al Pensiero Computazionale, A.A. 2025/2026 — Alma Mater Studiorum Università di Bologna

Dataset scelto: Employee Attrition
Membri del gruppo:
*   **Nicoletta Aloisi:** matricola 1216124, email nicoletta.aloisi@studio.unibo.it
*   **Erika Avdiaj:** matricola 1226030, email erika.avdiaj@studio.unibo.it
*   **Giannalisa Romeo:** matricola 1216078, email giannalisa.romeo@studio.unibo.it

**Analisi del Turnover del Personale - Previsione dell'abbandono dei dipendenti**

*Descrizione del progetto*
Il progetto analizza il fenomeno dell'employee attrition (abbandono dei dipendenti) in un contesto aziendale, con l'obiettivo di identificare i fattori associati alle dimissioni e costruire modelli predittivi in grado di riconoscere i dipendenti a rischio.

Il lavoro è strutturato in cinque fasi:
1. Setup del progetto e del repository GitHub
2. Descrizione e comprensione del dataset (statistiche descrittive, riflessioni critiche)
3. Analisi esplorativa e visualizzazione (grafici, domande/ipotesi, confronti tra gruppi)
4. Modellazione (tre classificatori con preprocessing autonomo)
5. Valutazione e interpretazione dei risultati (metriche, confusion matrix, coefficienti, feature importance)

*Descrizione del dataset*
È stato utilizzato un dataset aziendale contenente informazioni anagrafiche, professionali ed economiche dei dipendenti).
Il dataset descrive le caratteristiche di 1470 dipendenti di un'azienda, raggruppabili in:
- Dati anagrafici: Age, Gender, MaritalStatus
- Caratteristiche lavorative: Department, JobRole, JobLevel, TotalWorkingYears, YearsAtCompany
- Variabili retributive: MonthlyIncome, HourlyRate, DailyRate, PercentSalaryHike
- Indicatori di soddisfazione: JobSatisfaction, EnvironmentSatisfaction, WorkLifeBalance, JobInvolvement
- Mobilità: BusinessTravel, DistanceFromHome

Variabile target: Attrition (binaria: Yes / No)
Il dataset è sbilanciato: 83,9% No (1233) e 16,1% Yes (237). Per questa ragione le metriche principali di valutazione sono precision, recall e F1-score sulla classe Yes, non la sola accuracy.

Prima della modellazione sono state eliminate alcune variabili costanti prive di contenuto informativo e sono state codificate le variabili categoriche tramite **One-Hot Encoding**.

*Obiettivo*
Prevedere se un dipendente lascerà l'azienda (Attrition = Yes) a partire dalle sue caratteristiche lavorative, retributive e personali, e identificare le variabili più associate al rischio di abbandono.

*Modelli utilizzati*
Sono stati confrontati tre algoritmi di Machine Learning:
- Logistic Regression
- k-Nearest Neighbors (k-NN)
- Random Forest

La valutazione dei modelli è stata effettuata mediante:
- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

Poiché il dataset risulta sbilanciato (circa 84% classe "No" e 16% classe "Yes"), particolare attenzione è stata dedicata al **Recall della classe Yes**, metrica ritenuta maggiormente significativa per il problema affrontato.

La Regressione Logistica ha ottenuto le prestazioni migliori sulla classe minoritaria, producendo il minor numero di falsi negativi (31 vs 42 degli altri due modelli). È anche il modello più interpretabile grazie ai suoi coefficienti.

La Random Forest fornisce la feature importance, che individua MonthlyIncome, Age e TotalWorkingYears come le variabili più influenti.

*Istruzioni per l'esecuzione*

Requisiti: Python + Librerie: pandas, numpy, matplotlib, seaborn, scikit-learn
- Aprire il file notebooks/Progetto_Gruppo_12.ipynb su Google Colab
- Caricare i file data/Employee_Attrition.csv e data/Employee_Attrition_Description.csv nella cartella sample_data/ di Colab
- Eseguire le celle in ordine dall'alto verso il basso

Il notebook deve essere eseguito in ordine sequenziale: le fasi successive dipendono dalle variabili create nelle precedenti.
