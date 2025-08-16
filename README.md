# 🚀 Spaceship Titanic — Deutsch kommentiertes Notebook

Deutsch kommentiertes Notebook für den Kaggle‑Wettbewerb *Spaceship Titanic*: **Mini‑EDA**, **kompaktes Feature Engineering**, **Random‑Forest‑Pipeline (5‑Fold CV)**, **OOF‑Konfusionsmatrix** und **Submission**.

## 📘 Projektbeschreibung
Dieses Projekt sagt vorher, ob ein Passagier **transportiert** wurde (`Transported` ∈ {True, False}).  
Wir behalten die **englischen Spaltennamen** (Kompatibilität mit Kaggle), dokumentieren alle Schritte **auf Deutsch** und erzeugen eine **`submission.csv`**.

## 🗂️ Datenquelle
- **Dataset:** Kaggle – *Spaceship Titanic*  
  https://www.kaggle.com/competitions/spaceship-titanic  
- Dateien **nicht enthalten**: `train.csv`, `test.csv` (bitte über Kaggle beziehen)

## 📁 Struktur
```
.
├─ Spaceship_Titanic_DE.ipynb    # Notebook (README als erste Zelle möglich)
├─ README.md
├─ requirements.txt
├─ LICENSE                       # MIT
└─ .gitignore
```

## 🧭 Nutzung (Kaggle)
1. Neues Notebook → **Add data** → Dataset *Spaceship Titanic* anhängen  
2. Notebook ausführen (**Run all**) → `submission.csv` entsteht in */kaggle/working*

## 🔍 Mini‑EDA
- Missing Values: **missingno** (Orange/Schwarz)  
- Verteilungen: `Age` normal, Ausgaben **log1p** wegen starker Schiefe  
- Kategorik: Verteilungen & Transportiert‑Quoten  
- Korrelationen (numerisch)

## 🛠️ Feature Engineering (kurz)
- `Cabin` → **Deck / CabinNum / Side**  
- `PassengerId` → **GroupId / GroupSize / IsAlone**  
- Ausgaben: **TotalSpend**, **HasSpend**, **log1p** je Ausgabenkategorie  
- Konsistenz: **SpendWhileCryo**  
- Alters‑Buckets: **AgeBin**  
- Imputation: numerisch **Median**, kategorisch **'Unknown'**

## 🤖 Modellierung
- **Pipeline:** ColumnTransformer (One‑Hot für Kategorik, Passthrough für Numerik)  
- **Modell:** RandomForestClassifier (600 Trees, `random_state=42`)  
- **Validierung:** 5‑Fold Stratified CV (Accuracy), **OOF‑Konfusionsmatrix + Bericht**

## 📊 Ergebnisse
- CV‑Accuracy (5‑Fold): siehe Notebook‑Ausgabe  
- OOF‑Konfusionsmatrix & Klassifikationsbericht: im Notebook visualisiert

## ⚙️ Abhängigkeiten
- Python ≥ 3.8  
- `pandas`, `numpy`, `scikit‑learn`, `matplotlib`, `seaborn`  
- optional: `missingno` (für Mini‑EDA)

## 📝 Lizenz
MIT – siehe `LICENSE`.

---

**Made with ❤️ by Emr7y · Modell: Random Forest · Datenquelle: Kaggle (Spaceship Titanic)**
