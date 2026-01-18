# Statistik-
Statistik Projekt
# Zeitliche Entwicklung meines nächtlichen Ruhepulses (2025)
### Projektarbeit im Fach Statistik von Alexander Leuenberger

Dieses Repository enthält den Code und die Analyse meiner Projektarbeit. Ziel war es, anhand persönlicher Fitbit-Daten statistische Muster im Verlauf meines nächtlichen Ruhepulses über das Jahr 2025 zu identifizieren.

## 📋 Projektübersicht

Der nächtliche Ruhepuls ist ein wichtiger Indikator für körperliche Erholung und Stress. In diesem Projekt wurde eine Zeitreihe von **293 Nächten** (14. Jan – 13. Dez 2025) analysiert, um Trends, saisonale Muster und Abhängigkeiten zu untersuchen.

### Forschungsfragen & Hypothesen
* **Frage:** Gibt es einen Trend, ein Wochenmuster oder eine Autokorrelation im Ruhepuls?
* **H0 (Nullhypothese):** Der Ruhepuls ist rein zufällig verteilt; es gibt keinen Trend und keine zeitliche Abhängigkeit.
* **H1 (Alternativhypothese):** Es existieren systematische Trends (z. B. Jahreszeiten) und wiederkehrende Muster.

## 💾 Datengrundlage

* **Quelle:** Exportierte `Sleep_score.csv` von Fitbit.
* **Variable:** `resting_heart_rate` (Ruhepuls in bpm).
* **Zeitraum:** 14.01.2025 bis 13.12.2025.
* **Kennzahlen:**
    * Mittelwert: 68.8 bpm
    * Min/Max: 60 - 77 bpm
    * Standardabweichung: ~2.96 bpm

## 🛠 Technologien & Methoden

Das Projekt wurde in **Python 3** (Jupyter Notebook) umgesetzt. Folgende Bibliotheken kamen zum Einsatz:

* **Datenverarbeitung:** `pandas`, `numpy`
* **Visualisierung:** `matplotlib.pyplot`
* **Zeitreihen-Modellierung:** `prophet` (Facebook Prophet)
* **Statistische Tests:** `statsmodels` (genutzt für OLS-Regression, ACF-Plots und Seasonal Decompose)
* **System & Tools:** `pathlib`, `logging`, `warnings`

**Analyseschritte:**
1.  **Explorative Datenanalyse (EDA):** Gleitende Mittelwerte, Histogramme, Boxplots nach Wochentagen.
2.  **Dekomposition:** Zerlegung in Trend, Saisonalität (Woche) und Residuen.
3.  **Prophet-Modellierung:** Modellierung des Verlaufs und Analyse der Changepoints.
4.  **Residuen-Analyse:** Untersuchung der Autokorrelation (ACF) und Regression auf externe Events (Ferien, Prüfungen, Krankheit, Studienreise).

## 📊 Wichtigste Ergebnisse

Die Analyse widerlegt die Nullhypothese (H0) und stützt H1:

1.  **Jahrestrend:** Der Ruhepuls zeigte einen klaren Verlauf mit einem Tiefpunkt im Sommer (Aug/Sep) und einem Anstieg Richtung Winter.
2.  **Wochenmuster:** Es gibt leichte Unterschiede zwischen den Wochentagen (Wochenende tendenziell tiefer), die jedoch statistisch weniger ins Gewicht fallen als der Trend.
3.  **Autokorrelation (Lag-Effekt):** Der stärkste Einflussfaktor ist der Wert des Vortages. Abweichungen "halten" oft 2–6 Tage an (starke Autokorrelation der Residuen).
4.  **Einflussfaktoren:**
    * Die **Studienreise** zeigte einen signifikanten Erhöhungseffekt (+2.28 bpm).
    * Unterschiede zwischen **Arbeitstagen** und **Schultagen** waren statistisch nicht signifikant.

## 🚀 Installation & Ausführung

Um das Notebook lokal auszuführen:

1.  Repository klonen:
    ```bash
    git clone [https://github.com/DEIN_USERNAME/DEIN_REPO_NAME.git](https://github.com/DEIN_USERNAME/DEIN_REPO_NAME.git)
    ```

2.  Abhängigkeiten installieren:
    ```bash
    pip install pandas numpy matplotlib prophet statsmodels cmdstanpy
    ```

3.  Jupyter Notebook starten:
    ```bash
    jupyter notebook "Statistik Projekt.ipynb"
    ```

*Hinweis: Die Rohdaten (`Sleep_score.csv`) müssen im Hauptverzeichnis oder im Ordner `data/` liegen.*


## ℹ️ Hinweis zur Nutzung von KI

In diesem Projekt wurden KI-Tools (z. B. ChatGPT/Gemini) unterstützend eingesetzt für:
* Debugging und Optimierung von Python-Code.
* Erstellung von Textentwürfen und sprachliche Korrekturen.
* Strukturierung der Dokumentation (README).
Die fachliche Prüfung und Endabnahme aller Inhalte oblag mir als Autor.

Alexander Leuenberger 
